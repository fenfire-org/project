========================
Puzzle demo walk-through
========================

On this page, we'll look at how we can create a 4x4 puzzle with
the lob system, i.e., a puzzle looking like this,

+----+----+----+----+
|  1 |  2 |  3 |  4 |
+----+----+----+----+
|  5 |  6 |  7 |  8 |
+----+----+----+----+
|  9 | 10 | 11 | 12 |
+----+----+----+----+
| 13 | 14 | 15 |    |
+----+----+----+----+

where you have a 4x4 grid filled with 15 pieces and one gap,
and you can move a piece directly next to a gap into that gap.
(The goal is to get from a random arrangement into a particular one
like the one shown above, but that's beyond the scope of this demo;
we'll just provide pieces that the user can move around.)


Preliminaries
=============

We'll use a class PuzzleBoard, which keeps the current state
of the gameboard and has the following interface:

``int getPiece(int row, int column)``
    Return the number of the piece at the given row and column.
    If the gap is at the given row and column, return
    a negative number.

``int getGapRow()``, ``int getGapColumn()``
    Return the row and column that the gap is at.

``void movePiece(int row, int column)``
    If the given row and column indicates a piece
    next to the gap, move it into the gap; else, do nothing.

The implementation of PuzzleBoard isn't important here,
it's just ordinary Java.


Simple lobs: Creating lobs for the puzzle pieces
================================================

We start by writing some code to create the lob
showing piece with number ``i``. 

As in ``PuzzleBoard.getPiece()``, a negative number indicates the gap;
in this case, we return a "null lob," meaning a lob
that simply renders nothing. ::

    if(i < 0)
	return Lobs.nullLob();

Otherwise, we first create a lob showing the given number as text,
using a static method in the Lobs class. ::
    
    Lob l = Components.label(""+i);

This lob has a more or less fixed size. We now wrap this lob
in another lob, which can be rendered in a box of arbitrary size,
and will render its child at the middle of that box (at its natural size). ::

    l = Lobs.align(l, .5f, .5f);

This method takes the lob to be wrapped (``l``), and one fraction
between zero and one for the x- and y-axes each. It will align
the child so that the point at the given fraction (here: 
the point at the center) is rendered at the corresponding point
in the given box (here, the center of the label is rendered at the center
of the given box).

However, the *size request* of the lob -- its minimum, natural,
and maximum size -- are still the same as the label's. We would like
all lobs to be rendered in a box of the same size. To do this,
we wrap the lob again to change its size request. ::

    l = Lobs.request(l, 30, 30, 30, 30, 30, 30);

The individual parameters of ``Lobs.request()`` are:
the lob to be wrapped; the minimum, natural, and maximum size
on the x-axis; and the minimum, natural, and maximum size
on the y-axis (all in pixels).

We now wrap this lob in another lob, which renders a background behind
and a border around our label. ::

    l = Components.frame(l);

Finally, we put a 10-pixel margin around the frame. ::

    l = Lobs.margin(l, 10);
    return l;

You'll notice that some of the static functions we used 
are in the ``Components`` class, while others are in the ``Lobs`` class.
The difference is that ``Lobs`` contains functions whose output
depends only on their input, whereas functions in ``Components``
may draw default values for fonts, colors, etc., from different sources.
(Currently the defaults are hard-coded, but they are meant to be
configurable.) For example, when calling ``Components.label()``,
we do not have to specify the font or color.

We now arrived at the following function::

    public static Lob piece(int i) {
	if(i < 0)
	    return Lobs.nullLob();

	Lob l = Components.label(""+i);
	l = Lobs.align(l, .5f, .5f);
	l = Lobs.request(l, 30, 30, 30, 30, 30, 30);
	l = Components.frame(l);
	l = Lobs.margin(l, 10);
	return l;
    }


Lobs and identity
=================

We'll make one more change to the above: We will associate the lob
with the *identity* of the piece. To do this, we have to provide
a Java object that represents the piece. We'll simply use
an ``Integer`` object containing the piece number (i.e., ``i``).

Our function then looks like this::

    public static Lob piece(int i) {
	if(i < 0)
	    return Lobs.nullLob();

	Lob l;

	RoleContext.enter(new Integer(i));
	try {
	    l = Components.label(""+i);
	    l = Lobs.align(l, .5f, .5f);
	    l = Lobs.request(l, 30, 30, 30, 30, 30, 30);
	    l = Components.frame(l);
	    l = Lobs.margin(l, 10);

	    l = RoleContext.lob(l);
	} finally {
	    RoleContext.exit();
	}
	
	return l;
    }

We added three things:

- ``RoleContext.enter()``, to which we pass the ``Integer`` object
  representing our piece;

- a ``try...finally`` block, with ``RoleContext.exit()`` 
  in the ``finally`` clause; and

- at the end of the ``try`` clause, the line ``l = RoleContext.lob(l)``.

Together, these tell the lob system that the lob 
created in the ``try`` clause represents on the screen
the object ``Integer(i)``. 

The most visible effect is that when the screen changes,
but there are lobs representing the same object in the old
and new screens, the system will automatically show an animation
of the lob moving to its new place. In the puzzle demo,
this means that when the puzzle pieces move to a different place,
the lob system will automatically show an animation.

This functionality is, in fact, provided by the underlying
Libvob system, which we will look at in a future lecture.

The less visible effects are:

- We can create code that adds information to independently created views,
  by looking at the identities of the lobs created by these views.
  For example, we could create a view that looks for lobs 
  representing a person, and adds a thought bubble with the person's birthday 
  to each such lob. (This, too, uses the underlying Libvob system.)

- Lobs can store state, which will be associated with the identity
  they represent. For example, a text field needs to store
  the current cursor position. This is an issue because
  we generally create a new tree of lobs each time we update the screen;
  we can therefore not store state "inside" the lob objects.

The identities of lobs form a hierarchy. Consider the following code::

    RoleContext.enter("identity A");
    try {
	RoleContext.enter("identity 1");
	try {
	    // create lob a
	
	    a = RoleContext.lob(a);
	} finally {
	    RoleContext.exit();
	}

	a = RoleContext.lob(a);
    } finally {
	RoleContext.exit();
    }

    RoleContext.enter("identity B");
    try {
	RoleContext.enter("identity 1");
	try {
	    // create lob b
	
	    b = RoleContext.lob(b);
	} finally {
	    RoleContext.exit();
	}

	b = RoleContext.lob(b);
    } finally {
	RoleContext.exit();
    }

Lobs 'a' and 'b' do not have the same identity, as far as
the lob system is concerned; for example, they would not
be animated to each other.


The puzzle
==========

Like the individual pieces, the whole puzzle is a lob.
It is created by a function called ``lob()``::

    public static Lob lob(Map params) {
	PuzzleBoard board = 
	    (PuzzleBoard)Components.getState(params, "board", null);

        // ...
    }

The first line of the function is an example of a lob
using state associated with its identity. Consider this code::

    RoleContext.enter("the first puzzle");
    try {
	puzzle1 = lob(new HashMap());
    } finally {
	RoleContext.exit();
    }

    RoleContext.enter("the second puzzle");
    try {
	puzzle2 = lob(new HashMap());
    } finally {
	RoleContext.exit();
    }

Here, 'puzzle1' and 'puzzle2' would have different PuzzleBoards
because they are associated with different identities.

The second parameter to ``Components.getState()`` is the name
of the state field to be read; the third parameter is a default value,
if this state field hasn't been set, yet; and the first parameter
is a ``Map`` that can be used to explicitly provide an object
containing state, rather than associating the state
with the lob's identity (for example, if we wanted to store
a text field's cursor in an RDF database, instead of only
keeping it in memory).

``lob()`` continues to check whether a board has actually been
created already, and creates a new one if necessary::

    if(board == null) {
        board = new PuzzleBoard();
        Components.setState(params, "board", board);
    }

Then, we proceed to create a the grid of puzzle pieces. For this,
we use ``TableLob``, a special lob for layouting things
in a grid.

``TableLob`` contains an interface we need to implement::

    public interface Table extends Realtime { 
	int getRowCount();
	int getColumnCount();

	Lob getLob(int row, int column);
    }

A simple implementation would look something like this::

    TableLob.Table table = new TableLob.Table() {
	public int getRowCount() { return 4; }
	public int getColumnCount() { return 4; }
	
	public Lob getLob(int row, int column) {
	    return piece(board.getPiece(row, column));
	}
    };
    
This ignores that ``Table`` extends the ``Realtime`` interface, though.

The actual code we use looks more like this::

    TableLob.Table table = new @realtime-i TableLob.Table(PuzzleBoard board) {
	public int getRowCount() { return 4; }
	public int getColumnCount() { return 4; }
	
	public Lob getLob(int row, int column) {
	    return piece(board.getPiece(row, column));
	}
    };

This uses the special '@realtime-i' syntax, which is transformed
into proper Java by a preprocessor we have written. Preprocessing
the above generates the following convoluted code at the end of the Java file
(you don't need to understand what it does, at this time, this is just
meant to explain why preprocessing is needed in this case)::

        private static class _TableLob_Table_2 extends RealtimeObject implements TableLob.Table {

            private _TableLob_Table_2() {}

            PuzzleBoard board;

            
	    public int getRowCount() { return 4; }
	    public int getColumnCount() { return 4; }

	    public Lob getLob(int row, int column) {
		Lob lob = piece(board.getPiece(row, column));

		lob = Lobs.clickController(lob, 1, new_Action_3(board,row,column));

		return lob;
	    }
	

            public boolean move(ObjectSpace os) {
                if(super.move(os)) {
                    if(((Object)board) instanceof Realtime) ((Realtime)((Object)board)).move(os); 
                    return true;
                }
                return false;
            }
        }

        private static final RealtimeObject.Factory _TableLob_Table_2_FACTORY =
            new RealtimeObject.Factory() {
                protected Object create() { return new _TableLob_Table_2(); }
            };

        private static _TableLob_Table_2 new_TableLob_Table_2(PuzzleBoard board) {
            _TableLob_Table_2 the_new_TableLob_Table_2 = (_TableLob_Table_2)_TableLob_Table_2_FACTORY.object();
            the_new_TableLob_Table_2.board = board;
            return the_new_TableLob_Table_2;
        }

The code in ``lob()`` gets transformed to::

    TableLob.Table table = new_TableLob_Table_2(board);

What the convoluted code does is to create a class of objects
that can be re-used by the Javolution library\ [#]_. Javolution
provides facilities for re-using Java objects in order to avoid
garbage collection overhead.

.. [#] http://javolution.org/

Let's look a bit more closely at the syntax accepted by the preprocessor. ::

    TableLob.Table table = new @realtime-i TableLob.Table(PuzzleBoard board) {
	// ...
    };

This is meant to look similar to the declaration of an anonymous
inner class. Unfortunately, however, the syntax isn't completely analogous,
because the preprocessor isn't very sophisticated.

First, there are two different tags that can be put before
the class name: @realtime for extending classes, and @realtime-i
for implementing interfaces. The difference is there because
the preprocessor needs to generate different code in each case.

Second, the preprocessor doesn't recognize variables declared 'final'
in the outer scope. To pass variables from the surrounding method
and class into the 'inner class,' they must be put in the brackets
after the class name; in this case, the variable 'board' is passed
to the inner class.

The actual ``Table`` implementation in the demo adds a handler
for interpreting mouse clicks as the command to move the clicked puzzle piece
into the gap::

	TableLob.Table table = new @realtime-i TableLob.Table(PuzzleBoard board) {
	    public int getRowCount() { return 4; }
	    public int getColumnCount() { return 4; }

	    public Lob getLob(int row, int column) {
		Lob lob = piece(board.getPiece(row, column));

		lob = Lobs.clickController(lob, 1, new @realtime-i Action(PuzzleBoard board, int row, int column) {
		    public void run() {
			board.movePiece(row, column);
		    }
		});

		return lob;
	    }
	};
