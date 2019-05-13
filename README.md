# fiosan-overlay

Repository for the implementation choices made by adopters of Apereo Fiosan (formerly the
Notification Backbone).

## Installation

This project builds a self-executing `war` archive;  you may choose either to (1) run it
independently, or (2) deploy it in a standard Java Servlet Container (such as [Apache Tomcat][]).

### Building Fiosan

The build system for this project is based on [Apache Maven][].  Use the following Maven command to
build Fiosan together with your configuration settings.

```console
$ mvn [clean] package
```

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

As it's name implies, you can configure Fiosan using `fiosan-overlay` by _overlaying_ source files.
You can obtain source files by visiting the [notification-ui repository][].  Copy the file(s) you
wish to cusomize from the `src/mail/resources` directory in `notification-ui` and place them in the
same location within `fiosan-overlay`.

Once you have the necessary files in `fiosan-overlay`, you can make your changes and build the
project (_e.g._ with `$ mvn clean package`).

### Files to Customize

The following illustration shows the files within `notification-ui` you are most likely to want to
customize and their locations.

```
  - src/
    - main/
      - resources/
        - static/
          - index.html
        - application.properties
        - quartz.properties
```

#### `index.html`

Customize this file to add your logo and CSS.

#### `application.properties`

Most application settings can be controlled here, including database connection & initialization
settings, server hostname, logging configuration, and where and how to access `notification-ms`.

#### `quartz.properties`

Choose a `org.quartz.jobStore.driverDelegateClass` setting that is appropriate for your RDBMS
platform (Oracle or MS SQL Server).


[Apache Tomcat]: http://tomcat.apache.org/
[Apache Maven]: https://maven.apache.org/
[notification-ui repository]: https://github.com/uoe-is-apps/notification-ui
