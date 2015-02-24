# Scalding Wordcount Example 

## Introduction

This is Twitter's [`WordCountJob`] [wordcount] example for [Scalding] [scalding] adapted to run on Hadoop. It also includes ScalaTest tests. This project is ported directly from Snowplow Analytics's [Scalding Example Project](https://github.com/snowplow/scalding-example-project).

## Building

Assuming you already have SBT installed(if not, on MacOs, use $brew install sbt@1):

    $ git clone git://github.com/soulmachine/scalding-example-project.git
    $ cd scalding-example-project
    $ sbt assembly

The 'fat jar' is now available as:

    target/scalding-example_2.11-1.0.0-SNAPSHOT.jar

## Unit testing

The `assembly` command above runs the test suite - but you can also run this manually with:

    $ sbt test
    <snip>
    [info] + A WordCount job should
	[info]   + count words correctly
	[info] Passed: : Total 2, Failed 0, Errors 0, Passed 2, Skipped 0

## Submit the job to Hadoop

    yarn jar scalding-example_2.11-1.0.0-SNAPSHOT.jar com.github.pkuwm.scalding.WordCountJob --hdfs --input wordcount-test/input --output wordcount-test/output
