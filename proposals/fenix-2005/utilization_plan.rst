=================================================
Fenfire Fenix project research & utilization plan
=================================================

Introduction
============

In today's mainstream computing environments, knowledge workers
are limited in their work to the schemas of information supported
by applications designed by others, and with information being scattered
across these applications.

For example, the same person may exist as six different "objects" 
in six different applications, such as address books, e-mail clients,
and project managers, and additionally appear in countless 
text documents, without any connections between these instances.

When the information schemas provided by the applications do not suffice,
the user cannot extend them. For example, when they need to remember 
who commented how on a particular presentation, they can not store this 
new type of information in either their address book or their e-mail client;
rather, they may create a new text document that is connected to neither.

The Semantic Web technologies promise to provide a solution to this problem.
Unlike previous technologies for data representation, such as 
relational databases, XML, or object-oriented programming, the Semantic Web
technologies have a built-in concept of the identity of real-world things,
such as people; they naturally allow the fact to be expressed that
the Liisa Mattilainen in Alice's Outlook database is the same entity
as the Liisa Mattilainen in Bob's Mozilla Thunderbird contact list.
They also allow the computer to detect this automatically, for example
by noting that the two Liisas have the same homepage and e-mail address.

Additionally, they are easy to extend; on the level of the data model,
it would be trivial to add a "comment" relationship between a presentation
and an e-mail commenting on it, which would itself automatically be linked
to the person who sent the e-mail. 

Thus, instead of creating an unstructured text document, 
our hypothetical knowledge worker would merely add a single new
type of relationship, and proceed to connect entities already present
in the system. Instead of having, without connections, the information
that Liisa Mattilainen sent a particular comment on the presentation,
they have at their fingertips all replies to the e-mail containing the comment,
and all other information about Liisa Mattilainen that is available 
in the system.


Fenfire
=======

A system based on Semantic Web technologies could provide a much more powerful 
and flexible environment for knowledge workers, in many cases allowing them
to model the information they deal with closer to the way they think about it,
closer to the structure of their work, than applications with fixed data models
ever could. The unstructured spreadsheet or text document as a surrogate
for an application meeting the user's needs would no longer be necessary.

It is thus natural that there are efforts to use Semantic Web technologies
on the client, to create a "semantic desktop." The Fenfire project
is such an effort. Besides Fenfire, we are aware of two other projects
working on this problem.

- *Gnowsis*, an open-source project developed by a German research institute
  that we collaborate with, takes the approach of integrating existing
  desktop applications by exposing the data contained in their databases
  in a Semantic Web format, and allowing the user to create relationships
  between items from different applications and follow these relationships.

  Gnowsis takes a conservative approach to the user interface, adding only
  two toolbar buttons to compliant applications ("browse," which opens
  the selected item in Gnowsis to explore its relationships, and "link,"
  to create a new relationship).

- *Haystack*, also an open-source project, is developed by a research project
  at the Massachusetts Institute of Technology. Haystack provides an interface
  reminiscent of a Web browser, with an extensible set of views 
  for different kinds of data. Haystack views are similar to Web forms
  and forms-based desktop applications, and are created by programmers
  or experienced users, using a specialized description language.
  Unlike conventional forms, different Haystack views of the same "object"
  can be shown at the same time.

However, to our knowledge, neither of these projects make it a goal
to allow the user to create their own integrated "applications" by
using pieces of third-party applications and extending them with
new relationships and item types. This goal, which we see as fully reflecting
the extensibility of the Semantic Web at the user interface, thus
bringing it to the *user* rather than only the *programmer*,
is what makes the Fenfire project unique. (We put "application"
in quotation marks because in the system we envision, they will be nothing
like the walled-off zones of functionality that applications are today.)

In order to achieve this, Fenfire visualizes the connections between items
and makes this a fundamental part of the user interface. When looking
at a particular item, Fenfire will show around it the other items
related to it, connected through lines to the item in the center.

Whenever a Fenfire "application" needs to relate two items -- for example,
an e-mail and its sender -- or show an annotation to an item -- for example,
the priority of an e-mail -- the simplest way to do so will be
simply to make the Fenfire framework show it as a connection.

As relationship types created by the user will be shown the same way,
unless specified otherwise, they will not appear as out-of-place,
external additions to the "application," but will look exactly the same way
as any relationship that is an integral part of the application.
Even a link between two items from different "applications" will be 
in no way different than a link between two items from the same "app."

Therefore, there will be ideally no border between different "applications,"
and little limits to users to create "applications" of their own.

For details on how Fenfire works, as well as mock-ups and screenshots, 
please refer to the attached articles.


What are the goals and intended results?
========================================

The ultimate goal of the Fenfire project is to create a desktop environment
for knowledge workers in which 

1. information is structured as relationships between real-world things
   such as people and projects, rather than through artificial concepts 
   like applications and folders;

2. the user can easily extend the available relationships and views, 
   creating their own "applications";

3. information is easily exchanged between different users with support
   for versioning and collaborative work.

The goals of the proposed Fenix project are

- to complete a first version of a single-user Fenfire system implementing
  points 1 and 2, above;
- to publish this software as open source, build a community around it
  and evaluate the results of real-world use of the software.

The single-user Fenfire system will also act as a general, extensible
browser and editor for Semantic Web data.

As part of the goal of finishing and releasing a single-user version
of Fenfire, we will continue our research into implementation methods
for Semantic Web-based user interfaces.


What is the demand for such goals and results?
==============================================

Information management is an important concern in many organizations today.

The need for higher integration between desktop applications is underscored
by the investment of a large company like Microsoft in a technology like
WinFS, which provides a common, extensible data store to be used by
applications running on the next generation of Windows. (While not directly
compatible with RDF, WinFS is based on a very similar data structure.)

Allowing the *user* to arbitrarily extend the data schemas and applications,
and making this a normal part of the user's activity, is an unusual approach.
However, users do this already, only without tool support; a user
creating a list of club members in a word processor is creating 
a data structure, only without tool support. We believe that allowing users
to extend and relate information from different applications will be
an important improvement in information management for knowledge workers.

Additionally, the Semantic Web, still in a research and development phase,
is growing in importance. On the Semantic Web, semantic information
forms a big network of interlinked graphs. Enough early adopters publish
information in Semantic Web formats today for it to be of interest,
but while there are many tools that make use of data in specific schemas,
only few tools allow the user to browse Semantic Web data in general.
Such tools are, however, needed to make use of the core advantage
of the semantic representation of data: the extensibility with new types
of items and relationships.

Fenfire, providing a way to browse any Semantic Web data, can help users
and developers to start taking advantage of the interlinked structured data
already published on the Semantic Web, and show the usefulness of
providing all sorts of data and extensions in semantic graphs. This can
help to show users the usefulness of Semantic Web data already on-line,
provide an incentive to users to put more data on-line (as they can see
an actual use for it), and help researchers in their use of the Semantic Web.

We have demonstrated components of Fenfire at international workshops
and conferences, and there has been substantial interest from members
of the hypertext and Semantic Web communities in our tools.


What are the potential applications? How the results can be utilized?
=====================================================================

We believe that in the future, Fenfire or a similar system may become
the desktop environment for any computer user dealing with information.
Engineers may use it to keep track of ideas they have explored,
experiments they have conducted, and regulations they must follow;
analysts may use it to categorize and rate information they have gathered,
and to relate it to reports they are writing; artists may use it
to keep track of ideas and relate them to digital works exploring them.


Which level of developement the project aims to? What is the time-scale?
========================================================================

The software we will release as part of this project will be usable
in these ways. However, as a first version, it will be aimed at
expert users. We believe that technically versatile early adopters
will be able to make use of this software. Following the first release,
we will improve the software in an open-source process to make
it easier for non-experts to learn.

As the first target group for the software released in this project, we see

- Semantic Web researchers and developers, who will make use of the
  Semantic Web browsing and RDF editing functionality we provide; and

- Technically experienced knowledge workers who need better tools
  for information management badly enough to use early versions of Fenfire
  for their work.

We believe that our tool will be immediately useful for enough
Semantic Web developers to quickly build a user community around it.
As they become more familiar with Fenfire, we believe that some users
from this community will want to start using it for information management
in general, providing the core of an open source community for this use
of Fenfire.

The second user community may use Fenfire in conjunction with
Gnowsis, which provides interoperability with existing desktop applications
by making data from these applications available in a Semantic Web format.
For example, using Gnowsis, users will be able to continue using 
their existing Outlook database and e-mail client, and make use
of the data in these applications through Fenfire.

Further development depends on the formation of an open-source community
around Fenfire. It is very hard to estimate how soon an end-user version 
of Fenfire can be produced; this depends very much on the level of involvement
we can obtain from the community, and on the needs of individual contributors.


Which are the aims of project parties to utilize the results? Who owns IPR?
===========================================================================

The results of the project will be published as open-source code.
We believe that we will be able to build a community that will use
the product and continue its development.

The only IPR created in this project are the copyrights to the
Fenfire code. These are currently held by the individual authors.

We are in the process of founding a non-profit association which,
in the future, will hold the Fenfire copyrights and publish the software.

All Fenfire code is and will continue to be licensed under the
open-source GNU General Public License. Both companies and private users
will thus be able to use Fenfire without charge. The license allows for
arbitrary modification and redistribution of the source code,
but does not allow for proprietary derivative works.

Similar to successful open-source companies like Trolltech and
MySQL AB, the association will sell licenses to vendors wishing
to use Fenfire in proprietary systems. As the association is not for profit,
all revenue will be used to fund further development of Fenfire.


What are the duties in utilizing for projects parties? 
======================================================

The non-profit association being set up will distribute the software,
license it to proprietary software vendors, and, if it is able
to collect sufficient funds, employ programmers 
to continue software development. It may also offer support
and other services related to the product.

If the release of a single-user version of Fenfire is successful,
the university research group is planning to continue research
into multi-user environments, addressing issues of versioning
and collaborative work in the Fenfire environment. While
the single-user version will be helpful for individual early adopters,
useful deployment of Fenfire across a larger organization will likely
require more advanced collaboration support. We believe this effort
may take approximately one to two years.


Does the utilizing need support from outside of the project?
============================================================

Creating the first public release of Fenfire, as outlined above,
will not need support from outside the project. However, continued development
of Fenfire into a stable end-user product crucially depends on our ability
to create an open-source community around the software.
