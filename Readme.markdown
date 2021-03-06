[DRAFT]

YaScalaDT
==========

YaScalaDT is a Eclipse plugin to help coding in scala under Eclipse.
But something that could be strange, is that I currently doesn't expect the plugin to compile my scala code. The first goal is to have a editor better than what I currently configure in emacs/jedit.
I currently delegate the compilation to maven (through external tool or m2eclipse, same configuration could be done for SBT, buildr, ant,...).

The purpose of this github project is to "centralize"/expose information about the plugin :

* about
  * installation/configuration of the plugin
  * integration with external builder
  * tips & tricks
  * bug
  * work in progress
  * ...
* into
  * the formal documentation as text-file / image
  * the wiki
  * the issue tracker


But not to share the source code of YaScalaDT

Other Eclipse Plugin :
----------------------

* [Scala IDE for Eclipse](http://www.scala-lang.org/node/94) the official plugin provide/supported by EPFL
* [lightscalaplugin] (http://code.google.com/p/lightscalaplugin/) syntax-highlighting only
* [scaliptor](http://scaliptor.sourceforge.net/) DEAD


Motivations :
-------------

Or why I not contribute to ScalaDT ?

* I need an editor that could be released (bug fix, improvements, new features,...) independently from scala (scala-library and scala-compiler)
* I need an editor that work with project using "any" released version of scala, I'm daily work with stable released scala not 2.8+ (aka the next scala version)
* Two years ago, I took a look a the ScalaDT code to provide patch (toggle comments). Hard to read, to extend, to patch (like scaladoc, thanks to Sean and the Cake Pattern (ironic)). Miles did a big work since 2 years
* I need an editor that doesn't freeze (I switch to emacs 6+ month ago to avoid freeze when I typing)
* non conflicting integration with maven

Or why I not contribute to Netbeans ?
[TODO]

Or why I not enhance emacs or jedit ?
I like both, used both (ScalaMiniIDE for jedit was my first "real" project in scala)

* I don't have time to learn elisp to enhance/create extension (I tried to add scala to CEDET,...)
* Debugging/Profiling with editor

Others :

* As you understand, I tried (IDEA) and used several environments (at least 3 month each full time) and was satisfy by none for daily job (with released scala version). 2 years ago I create ScalaMiniIDE as a temporary solution, waiting the "Work In Progress" on the eclipse and netbeans. So I start create my own (in eclipse, because I prefer eclipse for java mater of taste) => I start learning how to create eclipse plugins
* May be part of the plugin will become "commercial" (=> current code is closed).
* having a visual client for sts (scala-tools-server, an other experimental project)

Notes :
-------

* The editor is written in java, because
  * no coupling to scala-library
  * it's easier/quicker (Eclipse PDE, copy/paste from existing without need to translate (I already did it when I coded a Netbeans RCP application in Scala, or when I create the ScalaMiniIDE in scala for Jedit))
  * allow contribution/review for eclipse plugin developper that don't know scala
  * avoid mixed project java/scala (if I integrate code generated by parser,...)

ChangeLog/RoadMap 
-----------------

(sorted with a balance between usefull priority and ease/time to implement).

Something that could be strange, is that I currently doesn't expect the plugin to compile my scala code. I first goal is to have a editor better than what I currently configure in emacs/jedit.
I currently delegate the compilation to maven (through external tool or m2eclipse).

version 0.1.0 :

* basic syntax highlighting (keyword, comments, strings) using java color configuration
* use java preference (color)
* integration with maven (m2eclipse) (markers should work with EPFL Scala PLugin)
  * maven-scala-plugin generate feedback to output (with reset indicator)
  * read maven-scala-plugin output to add/remove marker in code
  * add hyperlink/jumper in eclipse console to jump to error/warning

version 0.2.x :

* toggle-comment region
* completion by templates (like for yasnippet in emacs)
* configure indentation size (in space)
* configure templates
* autoedit
  * insert couple : "", (), {}, [], /* */
  * insert * at the begin of comment line (like java)
* integration with sbt
  * read sbt output to add/remove markers in code
  * add hyperlink/jumper in eclipse console to jump to error/warning

todo :

* hihghlight matching braces,...
* syntax error marker (result of antlr parsing) : run in background "as reconcilier"
* completion by name (variable/method/Class) already in the file
* Open Type (under cursor) (evaluate AnyEdit)
* auto-indent
  * configure indentation
    * tab or space
  * Re-indent code
* check undo/redo works
* autoedit
  * copy/paste code (with import)
* code navigation
  * find Type/method by simple name (context free like ctags) (fuzzy support like Anything in emacs, ...)
  * outline view ?
* syntax-highlithing support xml
* auto-import
  * at the begin of the file 
  * at the lowest to level ?
  * at configurable place
* run application
* run test
  * junit
  * specs, scalatest
* compiler integration
  * use work done for Groovy v2 ?
  * use sts + markers (like for maven)
* debugger
  * use work done for Groovy v2 ?
* java to scala conversion action
* refactor (may via the work of Mirko Stocker)
  * rename method
  * rename class/trait/object
  * rename package
* display deprecated code
* display javadoc/scaladoc

Thanks :
--------
* Janek for the idea of "commercial" scala plugin (a way for me to earn money with what I like creating tools for developer (like me))
* Prashant Deva for the tutorials : Create a commercial-quality Eclipse IDE (http://www.ibm.com/developerworks/views/opensource/libraryview.jsp?search_by=Create+commercial-quality+eclipse+ide)
* Matthew Scarpino for the tutorials : Building a CDT-based editor (http://www.ibm.com/developerworks/opensource/library/os-ecl-cdt1/)
* for YEdit use as sample code http://code.google.com/p/yedit
