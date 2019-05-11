# fiosan-overlay

Repository for implementation choices of adopters of Apereo Fiosan (formerly the Notification
Backbone).

## Installation

This project builds a self-executing `war` archive;  you may choose either to (1) run it
independently, or (2) deploy it in a standard Java Servlet Container (such as [Apache Tomcat][]).

### Running Fiosan Independently

Use `$ java -jar` from the command lind to start Fiosan as a self-executing `war` archive.

```console
$ java -jar <path.to.fiosan.war.file>
```

### Deploying Fiosan to a Java Servlet Container

Consult the documentation for your selected container.

In Tomcat, `war` archives can be deployed simply by copying them to the `$CATALINA_HOME/webapps`
directory of your Tomcat installation.

## Configuration


[Apache Tomcat]: http://tomcat.apache.org/

