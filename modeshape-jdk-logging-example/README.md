# ModeShape Custom Logging Example

This is a simple self-contained Maven project that shows how to make 
ModeShape send log messages to the JDK's logging system.

Out of the box, ModeShape is able to discover and use several common 
logging frameworks:

1. [SLF4J](http://slf4j.org)
1. [Log4J](http://logging.apache.org/log4j)
1. A custom logging framework
1. [Java Util Logging](http://docs.oracle.com/javase/8/docs/technotes/guides/logging/index.html)

ModeShape first looks on the classpath to find the SLF4J API, and if 
so uses that. If it is not available, ModeShape then looks
on the classpath for the Log4J library, and if found ModeShape uses 
that. If neither SLF4J nor Log4J are found, then ModeShape will look 
on the classpath for the `org.modeshape.common.logging.CustomLoggerFactory` 
class (see below), and if found uses this. If none of these are found, 
the ModeShape falls back to the using the JDK logging facility.

To use the JDK's logging, simply make sure that no other logging 
framework is available.

## About this example

The example provides no logging framework out of the box, and then sets up 
ModeShape as normal to run embedded within a simple J2SE application. The 
[ModeShapeExample](modeshape-jdk-logging-example/src/main/java/org/modeshape/example/logging/jdk/ModeShapeExample.java) 
class has a 'main(...)' method that loads a ModeShape configuration 
as a resource on the classpath, uses that configuration to build a 
ModeShapeEngine instance, starts the engine, and obtains a JCR Session 
to the repository.

This project is self-contained and can be built at the top level of 
your local clone of the Git repository, or by simply building this 
project using Maven 3:

    $ mvn clean install

See [this ModeShape community article](http://community.jboss.org/wiki/ModeShapeandMaven) 
for help on how to install Maven 3.

# The ModeShape project

This project is self-contained and can be built at the top level of your 
local clone of the Git repository, or by simply building this project 
using Maven 3:

    $ mvn clean install

See [this ModeShape community article](http://community.jboss.org/wiki/ModeShapeandMaven) 
for help on how to install Maven 3.

# The ModeShape project

ModeShape is an open source implementation of the JCR 2.0 
([JSR-283](http://www.jcp.org/en/jsr/detail?id=283])) specification and 
standard API. To your applications, ModeShape looks and behaves like a 
regular JCR repository. Applications can search, query, navigate, change, 
version, listen for changes, etc. But ModeShape can store that content 
in a variety of back-end stores or it can access and update existing content 
from *other* kinds of systems (including file systems, SVN repositories, 
JDBC database metadata, and other JCR repositories). ModeShape's connector 
architecture means that you can write custom connectors to access any 
kind of system. And ModeShape can even federate multiple back-end systems 
into a single, unified virtual repository.

For more information on ModeShape, including getting started guides, 
reference guides, and downloadable binaries, visit the project's website 
at [http://www.modeshape.org]() or follow us on our [blog](http://modeshape.wordpress.org) 
or on [Twitter](http://twitter.com/modeshape). Or hop into our 
[IRC chat room](http://www.jboss.org/modeshape/chat) and talk our community 
of contributors and users.

The official Git repository for the project is also on GitHub at 
[http://github.com/ModeShape/modeshape]().

# Need help?

ModeShape is open source software with a dedicated community. If you have 
any questions or problems, post a question in our 
[user forum](http://community.jboss.org/en/modeshape) or hop into our 
[IRC chat room](http://www.jboss.org/modeshape/chat) and talk our 
community of contributors and users.
