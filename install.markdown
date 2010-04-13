*******************************
  Installation/Configuration  
*******************************

Required Steps
==============

1. remove previous version from eclipse/dropins (if installed version 0.1.0 or 0.2.0)
2. register the update site http://alchim31.net/eclipse and follow the wizard to install the plugin YaScalaDT

Optional Plugins
================

* [AnyEdit](http://andrei.gmxhome.de/anyedit/) : AnyEdit plugin adds several new tools to the context menu of text- based Eclipse editors, to output consoles, to Eclipse main menu and editor toolbar.
* [M2Eclipse](http://m2eclipse.sonatype.org/) : Maven Integration for Eclipse provides tight integration for Maven into the IDE
* [Emacs+](http://www.mulgasoft.com/emacsplus/) : Eclipse Extensions for Emacs Expatriates, designed to provide a more Emacs-like experience in the Eclipse text editors.
* [MouseFeed](http://www.mousefeed.com/home) : a Key Promoter for Eclipse.

Optional Steps
==============

For maven
---------

Configure your pom.xml to use the maven-scala-plugin 2.13.1 +.
Create external tools to call

* mvn scala:cc -o
* mvn scala:test-compile -o

then launch the tool scala_cc, edit save, fixe,...
(Or create as builder for your project.)

For sbt (not tested)
--------------------

Add a task to tell to YaScalaDT whish markers to reset at the start of a compilation :

    override def compileAction = {
      log.info(mainScalaSourcePath.absolutePath + ":-1: info: compiling")
      super.compileAction
    }


Then like for maven, create an external tool or a builder to run

* sbt cc
* sbt compile


Environment tested :
====================

* v0.1.0 : Linux (Ubuntu 9.10) + Eclipse 3.5.1 + Java 1.6 + m2eclipse
* v0.1.0 : Windows XP/Windows 7 + Eclipse 3.5.1 + Java 1.6 + EPFL Scala Plugin
* v0.2.0 : Linux (Ubuntu 9.10) + Eclipse 3.5.1 + Java 1.6 + m2eclipse
* v0.2.1 : Linux (Ubuntu 9.10) + Eclipse 3.5.1 + Java 1.6
