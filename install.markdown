Installation/Configuration
==========================

Required Steps
--------------

1. download the jar https://sourceforge.net/projects/alchim/files/YaScalaDT/0.1.0/net_alchim31_eclipse_yascaladt_0.1.0.200911202226.jar/download
2. copy the jar into eclipse/dropins
3. (re)start eclipse

Optional Steps
--------------

For maven
.........

Configure your pom.xml to use the maven-scala-plugin 2.13.1 +.
Create external tools to call
* mvn scala:cc -o
* mvn scala:test-compile -o
then launch the tool scala_cc, edit save, fixe,...
(Or create as builder for your project.)

For sbt (not tested)
....................

Add a task to tell to YaScalaDT whish marker to reset like :

  override def compileAction = {
    //mainSources.getPaths.foreach { srcpath => log.info("This is a test." + srcpath) }
    log.info(mainScalaSourcePath.absolutePath + ":-1: info: compiling")
    super.compileAction
  }

Then like for maven, create an external tool or a builder to run
* sbt cc
* sbt compile


Environment tested :
--------------------
* v0.1.0 : Linux (Ubuntu 9.10) + Eclipse 3.5.1 + Java 1.6 + m2eclipse
* v0.1.0 : Windows XP/Windows 7 + Eclipse 3.5.1 + Java 1.6 + EPFL Scala Plugin
