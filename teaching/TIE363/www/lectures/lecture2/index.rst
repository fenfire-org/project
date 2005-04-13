=============================================================
Lecture notes for the second lecture of the identities course
=============================================================

:Lecture date: 2005-03-31
:Written by: Benja Fallenstein

First, these's a thesis of one `idea <../issues/one-idea-is/>`_ .
That's why we didn't get all done for this lecture.

There are two main topics in this lecture. First, we want to
talk about our vision for the Fenfire project. Second, we want
to get more practical and introduce you to a user interface framework
that is part of Fenfire.


The Fenfire vision
==================

Here's the plan that keeps us going:

- Store all of a user's information in a *single, structured data store*.

- In this data store, have references to *real-world things*
  (people, projects, ...) and relationships between these.

- *Don't have a fixed schema* of information. Allow the user to *extend*
  the kinds of information stored in the system.

- Allow programmers to *create views* for this information and *commands*
  to act on it. Encourage them to be general enough to be usable
  for different kinds of information.

- Instead of having applications, allow the user to combine arbitrary views
  and bindings suited for their current task.

- Provide a generic view showing the graph of relationships.
  Use this view [XXX to connect arbitrary other views and as the basic way
  for the user to interact with the system.]

  `More about these points. <plan.html>`_


XXX where to say the overlapping thing: information that would
today be stored unconnected in different applications can now
overlap freely, and so can the user's use of it -- this is important,
has to be in here


Then, we get a system XXX

The data structure we use in Fenfire is `RDF <rdf.html>`_,
developed by the World Wide Web Consortium\ [#]_ as a part of its
Semantic Web effort\ [#]_ to create a Web of machine-readable data.

.. [#] http://www.w3.org/
.. [#] http://www.w3.org/2001/sw/



Lobs
====

One thing needed in order to realize this plan is a flexible view architecture
that allows us to use use views together that were created independently
by different programmers.

`XXX intro to lobs <../issues/intro-to-lobs/>`_

- will give `example demo <puzzle-waltrough.html>`_
