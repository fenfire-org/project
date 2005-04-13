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
    - how to use it -- show FOAF/DOAP data


m:Lobs (25 minutes)
===================

    - What are lobs -- `intro to lobs <../issues/intro-to-lobs/>`_
    - Lob text handling as needed in 'viewlets': Labels, formatted text,
      hbox, glue, linebreaker-lob
    - Mention image lob


b:The Javolution preprocessor (10 minutes)
==========================================

    - where you need it
    - how to use it (no time to explain the concepts in Javolution itself)


b:Programming a representation view (30 minutes)
================================================

    - what are representation view
    - example ReprView we're going to do: person with nickname
    - (explain how it is done in FOAF)
    - skeleton of the repr view java file
    - getting the data we need through Swamp
    - display it with lobs
    - add to Main.rj
    - compile, run
