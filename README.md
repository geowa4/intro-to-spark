Intro to Spark
==============

This is based on Spark's [Quick Start guide](https://spark.apache.org/docs/latest/quick-start.html),
but it assumes OS X with Homebrew installed.

Before we can do anything, we need to install a few things.

```
$ brew install scala sbt apace-spark
$ brew cask install scala-ide
```

When I did this, I had these commands available (version in comments):

 - sbt  # 0.13
 - scala  # 2.11.6
 - scalac
 - scaladoc
 - scalap
 - spark-class
 - spark-shell
 - spark-sql
 - spark-submit  # 1.3.1

Assuming you've cloned this and are in this directory, you can run this.

```
$ sbt package
$ spark-submit --class SimpleApp --master local[4] target/scala-2.11/simple-project_2.11-1.0.jar 
```

To hack on this you'll need to add a line to `~/.sbt/0.13/plugins/build.sbt`.
Make that file if it doesn't exist.

```
addSbtPlugin("com.typesafe.sbteclipse" % "sbteclipse-plugin" % "4.0.0-RC1")
```

The current version of the Eclipse plugin for sbt was 4.0.0-RC1 at the time of writing.
That will likely be updated soon.
Be sure to find the latest.

Generate the files to configure Scala IDE (Eclipse).

```
sbt eclipse
```

Now, you can run that application with Spotlight (or Alfred) and open this project.
For the workspace, I chose `~/Development/learn-spark` as I had the `intro-to-spark` folder inside that.
