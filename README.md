# Elko

### A server framework for stateful, sessionful applications in the web

Elko is a Java-based server framework for building stateful, sessionful
applications in the web.  It is especially suited to applications that require
realtime interaction among multiple clients, such as realtime text chat or
multiplayer games, or that have a strong "push" component wherein the server
needs to initiate much of the interaction, such as service monitors or realtime
auctions.

Much of the scalability of the web derives from the statelessness of the HTTP
protocol and the consequent ease with which load may be distributed by simply
replicating web servers. However, there remain a core of interesting and
valuable interactive network applications that are fundamentally stateful, and
trying to shoehorn these into the web paradigm can be awkward and frustrating.

Elko is an application server framework designed to address this, enabling you
to quickly and easily create applications that require a live, truly
bidirectional dialog between client and server. 

Elko is highly scalable and very performant.  We have successfully run
configurations supporting upwards of 150,000 concurrently connected real-time
users on a single AWS "large" server instance.

## General Information

This README describes Elko release 2.0.1, dated 23-February-2016.

The authoritative source and documentation for Elko is maintained at:

https://github.com/FUDCo/Elko (i.e., here)

or

http://elkoserver.org (which currently redirects to here)


Background and theory are discussed in a series of three [Habitat
Chronicles](http://habitatchronicles.com/) blog posts:

* [Part I: The Life, Death, Life, Death, Life, Death, and Resurrection of The
Elko Session
Server](http://habitatchronicles.com/2009/09/elko-i-the-life-death-life-death-life-death-and-resurrection-of-the-elko-session-sever/)

* [Part II: Against Statelessness (or, Everything Old Is New
Again)](http://habitatchronicles.com/2009/09/elko-ii-against-statelessness-or-everything-old-is-new-again/)

* [Part III: Scale
Differently](http://habitatchronicles.com/2009/09/elko-iii-scale-differently/)

Elko is open source software, under the MIT license.  See the file LICENSE.md

## What's Here

* ServerCore -- contains the Elko server framework itself, along with its
  documentation.

* Web -- contains client side JavaScript and HTML for interacting with Elko
  applications from a web browser.

* Run -- contains a variety of shell scripts for running and managing various
  server farm configurations, as well as the beginnings of a web-based
  adminstration console (written in PHP).

* ZeroMQ -- contains a pluggable extension that lets Elko servers talk to
  things using the [ZeroMQ](http://zeromq.org) distributed messaging framework.

#### Building

To build the Java code from the sources directly as is, you will also need the
[jdep](http://www.fudco.com/software/jdep.html) utility and GNU Make.  Jdep is
currently hosted on my own website, but I hope to have it moved to GitHub
shortly.  I'll update this page when that happens.

Note that most people doing Java development these days use one of the several
popular Java IDEs and/or [Maven](https://maven.apache.org), but at the moment
there's no support here for these; I'm an old time Unix/emacs guy and never had
much use for such newfangled contraptions (especially Maven, yuck). However,
the Java source tree is structured in the conventional way and the classes have
few external dependencies outside the normal class libraries that are part of
the standard JDK, so you should just be able to import the source tree into
your favorite IDE and press the build button.

Much more detail on building will be presented in an accompanying BUILD.md file
when I get done writing it.

All the Java code works on any standard, reasonably current JVM. The various
shell scripts do assume a Unix shell environment, but Cygwin will suffice and
they are not deeply essential anyway.

#### Documentation

Currently, documentation is in the ServerCore/doc directory.  While extensive,
it badly needs to be updated to be friendlier with the new GitHub environment.
I also need to run JavaDoc on the code and find a home for the resulting web
pages.  However, if you run JavaDoc on the sources yourself, the resulting
output is very usable -- the code is well documented in this regard.

#### Binaries

My goal is to eventually make precompiled .jar files available for this stuff.
The appropriate manner for this to be hosted in the GitHub world is still
something I haven't researched (I could just commit the .jar files to the repo,
but that feels wrong).  Once this gets resolved, this README will be updated
accordingly.