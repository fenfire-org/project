=============================================================
Lecture notes for the fourth lecture of the identities course
=============================================================

:Lecture date: 2005-04-14

m:About this lecture (10 minutes)
=================================

In the previous lectures, we couldn't yet offer you a version
of Fenfire to play with, because for legal reasons we couldn't publish
the user-level application itself: there is a patent on some of the
visualizations we use. To give you something to play with,
we have written a public version of Fenfire for this lecture,
which does not use the code related to the patent. 

This is a very early version and doesn't work great -- we only
threw something together this week... We hope to improve it a lot soon.
In any case, you can use it to navigate an RDF graph already
(there isn't a good interface for changing a graph, yet).

In the following weeks, we would like to program code with you
for an `applitude`_ for Fenfire, i.e., the equivalent of an application
in a normal desktop environment, but integrated with the rest of Fenfire.
The applitude we want to create is a tool for setting up groups
of people, for example a group of students working together
on a course project. ;-) You should be able to

- list the people in your group
- create a mailing list
- list ideas and feedback about them
- make a schedule for implementing them
- publish this information as RDF and allow other people
  to download and view it, for example through Fenfire

.. _applitude: http://fenfire.org/manuscripts/2004/hyperstructure/#an-item-based-user-interface

The topic of this lecture will be to create a small view ("viewlet")
for some RDF data that can be used in Fenfire. We hope that
during the next week you will install the public version of Fenfire
and develop your own similar small view based on it.


b:The public Fenfire (10-15 minutes)
====================================

- how to install it

Get it from

    http://himalia.it.jyu.fi/~benja/fenfire-2005-04-14.zip

Unzip, change into the ``fenfire-2005-04-14`` directory, and run::

    java -jar fenfire-snapshot-2005-04-14.jar demo.turtle

- how to use it -- show FOAF/DOAP data


m:Lobs (25 minutes)
===================


Basic layoutable objects
------------------------

Text, boxes and glue
~~~~~~~~~~~~~~~~~~~~



- What are lobs? -- `intro to lobs <../issues/intro-to-lobs/>`_

Lobs, alias layoutable objects are something you layout into rectangle
area and then render it. The same idea is behind TeX -- thus it does
work pretty well. With Fenfire we add animation and interaction to the
consept. But let's start with basics::

    package org.nongnu.libvob.lob.doc;
    import org.nongnu.libvob.lob.*;

    // class is run by screenshot util.
    public class Example_Text {

        public Lob getLob() {
	    return Lobs.hbox(Components.font().text("H e l l o !"));
        }

    }

It generates the following output in (160x128 sized window):

.. image:: ../../../../../../libvob/org/nongnu/libvob/lob/doc/Example_Text.png

As you can see the spaces between letters are not exactly what you
would expect but more wider. So, what's wrong, why it show text like
that? To answer that you need to understand what's going on.

- There is text with font
- And the text is inside of box

hbox is a box or a list, a layoutable thing that is being placed
horizontally, i.e., it has width. Things inside the box are placed as
well as the system can layout them. To go back to text, text is
letters and letters are boxes that has rectangular shape. When the
layouting is done the box is told to layout to certain width. That's
why the virtual boxes inside hbox are stretched to make it look as
requested by layout.

You might think that why to brother with badly rendered text but let's
fix the example easily::


    package org.nongnu.libvob.lob.doc;
    import org.nongnu.libvob.lob.*;

    // class is run from printter util to 
    // generate visual printout.
    public class Example_TextWithGlue {

        public Lob getLob() {
	    return Lobs.hbox(Components.font().textLn("Hello world!"));
        }

    }

The following output is seen in screen:

.. image:: ../../../../../../libvob/org/nongnu/libvob/lob/doc/Example_TextWithGlue.png

As you can see it looks different than the previous example. But why?
First, a new method is used to construct the text, i.e., textLn(String
text). It adds *glue* at the end of the list of boxes that represent
letters. Glue is something that you don't render at all, but has an
affect to layouting, e.g., in the example it is infitely stretchable
but at least zero sized "hole" in the screen. A better name for the
glue might be spring but of course as the term is already used with
TeX it is easier to use the same name for same functionality.

Next you will see more glue in use vertical box and more glue:: 

    package org.nongnu.libvob.lob.doc;
    import org.nongnu.libvob.lob.*;
    import java.util.*;

    // class is run from printter util to 
    // generate visual screenshot.
    public class Example_TextBoxesAndGlue {

        public Lob getLob() {
	
	    LobFont font = Components.font();
	
            // vertical box or list
            Lob vbox = Lobs.vbox();
	
            vbox.add(Lobs.hbox(font.textLn("Hello world!")));
            vbox.add(Lobs.hbox(font.text("Hello world!")));

            List l1 = font.text("Hello");
            List l2 = Lists.list(Lobs.glue(Axis.X, 1));
            List l3 = font.text("world!");
            List l4 = Lists.list(Lobs.hglue());
            vbox.add(Lobs.hbox(Lists.concat(l1,l2,l3,l4)));
	
            l1 = Lists.list(Lobs.hglue());
            l2 = font.text("Hello");
            l3 = font.text("world!");
            l4 = Lists.list(Lobs.hglue());
            vbox.add(Lobs.hbox(Lists.concat(l1,l2,l3,l4)));

            l1 = Lists.list(Lobs.hglue());
            l2 = font.text("Hello world");
            l3 = Lists.list(Lobs.hglue());
            vbox.add(Lobs.hbox(Lists.concat(l1,l2,l3)));
		 
            l1 = Lists.list(Lobs.hglue());
            l2 = font.text("Hello");
            l3 = font.text(" ");
            l4 = font.text("world!");
            vbox.add(Lobs.hbox(Lists.concat(l1,l2,l3,l4)));

            return vbox;
        }
    }

Which provides the following output in screen:

.. image:: ../../../../../../libvob/org/nongnu/libvob/lob/doc/Example_TextBoxesAndGlue.png

The new thing was to use also vertical box for layouting.
Another points are:

- The space letter in the first and second line are actually replaced
  with glue. That's why the second line has such a wide space; that was
  the only place where stretching can be done (there's no glue between
  lettesrs).

- The space can be replaced with smaller glue as within third line, though
  this is not encouragable.

- Centering can be easily made with two glues and a lob between them. 
  It shall be mentioned that the space glue between two words is
  different than the "fill the hole" glue before and after text.

- Align to right can be done as easily as centering (well, there's no
  shortcut for brText(String text), as in textLn(String text) =)


Linebreaked lob and text handling
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To make text handling easier, we have linebreaking as TeX has too. The
linebreaker eats given list of breakable objects and constructs
h(orizontal)boxes as lines which are added to one v(ertical)box. The
given text should contain the trailing glue or the last line may look
too stretched as expressed in the first example in current chapter.

There's an example code::

    package org.nongnu.libvob.lob.doc;
    import org.nongnu.libvob.lob.*;
    import java.util.*;

    public class Example_LineBreakedText {

        public Lob getLob() {
	    String [] texts = {
	        "Abc", "cat", "walks", "to", "some", "tree", "which",
	        "has", "ugly", "green", "tea", "next", "to", "see.", 
	    };

	    Random r = new Random(0);
	    LobFont[] fonts = new LobFont[texts.length];
	    for (int i=0; i<texts.length; i++)
	        fonts[i] = Components.font(new Color(r.nextInt(255),
						     r.nextInt(255),
						     r.nextInt(255)));

 	    List textList = Lists.list();
	    for (int i=0; i<texts.length; i++) {
	         textList = Lists.concat(textList, 
		  		        fonts[i%fonts.length].text(texts[i]+" "));
	    }
	    Lob l = Lobs.linebreaker(textList);
	    l = Lobs.margin(l, 10);
	    return l;
        }
    }

Will produce the screenshot available as here:

.. image:: ../../../../../../libvob/org/nongnu/libvob/lob/doc/Example_LineBreakedText.png

New thing with the linebreaking is the margin used in the example.


Coordinate lobs
~~~~~~~~~~~~~~~

Because lobs are build on top of Libvob, which has a powerful
coordinating system, there exists also following lob methods:
translate and scale.

We get into example and stop talking now::

    package org.nongnu.libvob.lob.doc;
    import org.nongnu.libvob.lob.*;

    public class Example_Translate {

        public Lob getLob() {
	
	    Lob l = Lobs.filledRect(java.awt.Color.red);
            float 
	        minWidth = 20,
	        naturalWidth = 20,
	        maxWidth = 20;
            float 
	        minHeight = 50,
	        naturalHeight = 50,
	        maxHeight = 50;

            l = Lobs.request(l,
		 	     minWidth, naturalWidth, maxWidth,
			     minHeight, naturalHeight, maxHeight);

	
	    l = Lobs.translate(l, 34, 56); // x=34, y=56

	    return l;
        }
    }

We get the output as:

.. image:: ../../../../../../libvob/org/nongnu/libvob/lob/doc/Example_Translate.png

New thing in this example is request lob which requests a certain size
for the child lob, that is a filled rectangle. The translation itself
is quite a simple.

Next is scaling::

    package org.nongnu.libvob.lob.doc;
    import org.nongnu.libvob.lob.*;

    public class Example_Scale {

        public Lob getLob() {
	    LobFont font = Components.font();
	    Lob vbox = Lobs.vbox();
	
	    int N = 5;
	    float scale = 1;
	    for (int i=0; i<N; i++) {
	        Lob l = Lobs.hbox(font.textLn("Hello!"));
	        l = Lobs.scale(l, scale, scale); // scaleX, scaleY
	        scale *= 1.2;
	        vbox.add(l);
	        if ((i+1) != N)
		    vbox.add(Lobs.vglue());
  	    }
	    return vbox;
        }
    }

Which has a screenshot like below:

.. image:: ../../../../../../libvob/org/nongnu/libvob/lob/doc/Example_Scale.png


Image lob
~~~~~~~~~

Images with awt is a bit pain in a neck. I try to come up with good
solution in anytime soon or you can propose your ideas acording to
subject.  The problem with images is that you may often run out of
memory and storing the images in pool of memory would lead us to
converting many images for different LODs perhaps.


Lobs composed to full components
--------------------------------

Look and feel
~~~~~~~~~~~~~


The org.nongnu.libvob.lob.Components class has static methods for
different components, which are lobs that are composed together with
basic lobs that do only one thing. For example a button component has
controller for click events, lob that is used to present the button
thing, a label with text for instance, and is put inside a margin.

As an example we can use Components.label(String text) which composes
a new hbox containing the text and ending glue.


Interactions
~~~~~~~~~~~~

The interaction with layoutable objects, that is, handling events and
such is not fun thanks to small memory print. Lobs are themselv *kind
of* immutable but to decrease creating a lot of objects, caching
library called javolution is used. But isn't immutable something to do
with final attributes and thus if something is immutable it can not be
mutable? Not really, but there's no public attributes or methods with
lobs that would change the state of a lob. So what this mean we can
have an example of constructing 1000x1000 sized table filled with
glue. Only one glue instance is used in the whole operation -- that's
really nice. 

The problem comes when there are objects that needs to be binded but
not reused. For such a object there might be actions for different
keys. Ok, if this kind of action object would be reused, only the last
used binding would survive but that's not exactly what we want.

With javolution we need a special way to keep something to not being
reused. An example code of such is coded below::

   



.. :

  - Lob text handling as needed in 'viewlets': Labels, formatted text,
    hbox, glue, linebreaker-lob 
  - Mention image lob




b:The Javolution preprocessor (10 minutes)
==========================================

    - where you need it
    - how to use it (no time to explain the concepts in Javolution itself)


b:Programming a representation view (30 minutes)
================================================

    - what is a representation view
    - example ReprView we're going to do: person with nickname
    - (explain how it is done in FOAF)
    - skeleton of the repr view java file
    - getting the data we need through Swamp
    - display it with lobs
    - add to Main.rj
    - compile, run
