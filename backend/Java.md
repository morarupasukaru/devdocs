# Java

[Java](https://en.wikipedia.org/wiki/Java_(software_platform)) is a popular general-purpose language.

This document try to summarize best of Java to develop REST APIs (or batches).

* [Language features](#Language-features)
* [Standard APIs](#Standard-APIs)
* [Third-party APIs](#Third-party-APIs)
* [Tools](#Tools)
* [Web frameworks](#Web-frameworks)
* [Design patterns](#Design-patterns)
* [Reactive programming](#Reactive-programming)
* [Alternatives](#Alternatives)
* [Links](#Links)
  TODO clean-up TOC

*(Page mainly written in spring 2022; in progress)*

[*Go to parent page*](../README.md)


## Language features
TODO

* TODO: *javalight / good parts of java* with latest versions of java

* [JDK Release Notes](https://www.oracle.com/java/technologies/javase/jdk-relnotes-index.html)
* Versions of java language and Java SE are coupled together
* [History of Java SE and major updates for the stack](https://en.wikipedia.org/wiki/Java_version_history)
  * 1996/1997 - JDK 1.0 / JDK 1.1: JDBC
  * 1998 - J2SE 1.2: [Collections framework](https://en.wikipedia.org/wiki/Java_collections_framework) --> TODO add sections
  * 2000 - J2SE 1.3: nothing interesting
  * 2002 - J2SE 1.4: [Regular Expression](https://en.wikipedia.org/wiki/Regular_expression)
  * 2004 - Java SE 5
    * [Generics](https://en.wikipedia.org/wiki/Generics_in_Java)
    * [Annotation](https://en.wikipedia.org/wiki/Java_annotation)
    * `enum`
    * [varargs](https://en.wikipedia.org/wiki/Java_syntax#Varargs)
    * [for each loop](https://en.wikipedia.org/wiki/Foreach_loop#Java)
    * [static import](https://en.wikipedia.org/wiki/Static_import)
    * [java.util.concurrent](https://docs.oracle.com/javase/1.5.0/docs/guide/concurrency/overview.html)
  * 2006 - Java SE 6 : nothing interesting
  * 2011 - Java SE 7
    * switch support String
    * try-with-resources
    * diamond operator `<>`
  * 2014 - Java SE 8
    * [lambda expression](https://en.wikipedia.org/wiki/Anonymous_function#Java)
    * stream API / optional
    * [date and time API](https://openjdk.java.net/jeps/150)
  * 2017 - Java SE 9
    * [Java platform module system](https://en.wikipedia.org/wiki/Java_Platform_Module_System) / Jigsaw
  * 2018 - Java SE 10 : nothing interesting
  * 2018 - Java SE 11 : nothing interesting
    * [HTTP Client](https://openjdk.java.net/jeps/321) - https://openjdk.java.net/groups/net/httpclient/intro.html
  * 2019 - Java SE 12 : nothing interesting
  * 2019 - Java SE 13 : nothing interesting
  * 2020 - Java SE 14 : nothing interesting
  * 2020 - Java SE 15 : nothing interesting
  * 2021 - Java SE 16 : [records](https://openjdk.java.net/jeps/395) as immutable Tuple -> checkout if really usefull in contrast to lombok
  * 2022 - Java SE 17 : nothing interesting
  * [Java language updates from 9](https://docs.oracle.com/en/java/javase/17/language/java-language-changes.html) from Java 9

* Platforms
  * [Java SE](https://en.wikipedia.org/wiki/Java_Platform,_Standard_Edition) (Standard Edition)
  * [Java EE or Jakarta EE](https://en.wikipedia.org/wiki/Jakarta_EE) (Enterprise Edition) extends Java SE with some entreprise feature
    * most features are no usefull with modern frameworks
    * important features: [Bean Validation](https://en.wikipedia.org/wiki/Bean_Validation),
      [JPA](https://en.wikipedia.org/wiki/Jakarta_Persistence)
      [Servlet](https://en.wikipedia.org/wiki/Jakarta_Servlet)
    * package renaming happens with transfer of Java EE from Orace to Eclipse Foundation
  * out of scope:
    [Java ME](https://en.wikipedia.org/wiki/Java_Platform,_Micro_Edition),
    [Java Card](https://en.wikipedia.org/wiki/JavaFX),
    [JavaFX](https://en.wikipedia.org/wiki/Java_Card)
* Java Virtual Machine
  * ...

language
* TODO summary of [language specifications](https://docs.oracle.com/javase/specs/index.html) or a book
  * maybe https://mitpress.mit.edu/books/java-precisely-third-edition TODO
* quick history of change in java version, feature and APIs
* types, structures, enum, interfaces, classes, package, exception
* annotations, generics
* lambda
* tools: java, javac, jar
* java 12, 13, 14: TODO
  * TODO complete with https://www.manning.com/books/modern-java-in-action


* TODO link to java tutorial with java feature? e.g. new "for loop"
** like JavaScript.md?

https://jenkov.com/tutorials/java/index.html#new-in-java-9

https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html

[*Go to top*](#Java)


## Standard APIs

https://docs.oracle.com/en/java/javase/17/docs/api/java.base/module-summary.html#packages-summary
  
* Overview
  * [java.base](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/module-summary.html#packages-summary) module
    * [java.nio.file](https://docs.oracle.com/javase/tutorial/essential/io/fileio.html)
      for file i/o 
    * [java.util.regex](https://docs.oracle.com/javase/tutorial/essential/regex/index.html)
      for regular expressions
    * [java.util.concurrent](https://docs.oracle.com/javase/tutorial/essential/concurrency/highlevel.html)
      for high-level concurrency features
    * [java.util | java.util.concurrent - java collection frameworks](https://docs.oracle.com/javase/8/docs/technotes/guides/collections/overview.html)
      for common data structures (list, map, etc.)
      ; see [tutorial](https://docs.oracle.com/javase/tutorial/collections/index.html)
    * [java.time](https://docs.oracle.com/javase/tutorial/datetime/index.html)
      for date/time
    * [java.net](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/net/package-summary.html)
      for networking
  * [java.net.http](https://docs.oracle.com/en/java/javase/17/docs/api/java.net.http/module-summary.html)
    module  
    * [java.net.http](https://docs.oracle.com/en/java/javase/17/docs/api/java.net.http/java/net/http/package-summary.html)
      for new HTTP client API
  * [java.sql](https://docs.oracle.com/en/java/javase/17/docs/api/java.sql/module-summary.html),
    [java.sql.rowset](https://docs.oracle.com/en/java/javase/17/docs/api/java.sql.rowset/module-summary.html)
    modules
    * [java.sql | javax.sql](https://docs.oracle.com/javase/tutorial/jdbc/basics/index.html)
      for database access (jdbc) 
* Packages & Classes
  * [java.io](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/io/package-summary.html)
    * TODO
    * [java.io.Closeable](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/io/Closeable.html)
  * [java.lang](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/package-summary.html)
    * TODO
    * [java.lang.AutoCloseable](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/AutoCloseable.html)
    * [java.lang.String](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/String.html)
      * [matches(regex)](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/String.html#matches(java.lang.String))
      * [split(regex)](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/String.html#split(java.lang.String))
    * [java.lang.Math](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Math.html): [random()](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Math.html#random())
  * [java.math](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/math/package-summary.html)
    * TODO
  * [java.net](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/net/package-summary.html)
    * TODO
    * [java.net.URL](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/net/URL.html)
    * [java.net.URI](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/net/URI.html)
    * java.net.http
      * TODO
  * [java.nio.file](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/nio/package-summary.html)
    * TODO
    * [java.nio.file.Files](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/nio/file/Files.html)
    * [java.nio.file.Path](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/nio/file/Path.html)
    * [java.nio.file.Paths](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/nio/file/Paths.html)
  * [java.text](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/text/package-summary.html)
    * TODO
  * [java.time](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/time/package-summary.html)  
    * TODO
  * [java.sql](https://docs.oracle.com/en/java/javase/17/docs/api/java.sql/java/sql/package-summary.html) for DB API
    * [java.sql.Connection](https://docs.oracle.com/en/java/javase/17/docs/api/java.sql/java/sql/Connection.html)
    * [java.sql.ResultSet](https://docs.oracle.com/en/java/javase/17/docs/api/java.sql/java/sql/ResultSet.html)
    * [java.sql.Statement](https://docs.oracle.com/en/java/javase/17/docs/api/java.sql/java/sql/Statement.html)
    * [java.sql.PreparedStatement](https://docs.oracle.com/en/java/javase/17/docs/api/java.sql/java/sql/PreparedStatement.html)
    * [java.sql.CallableStatement](https://docs.oracle.com/en/java/javase/17/docs/api/java.sql/java/sql/CallableStatement.html)
  * [javax.sql](https://docs.oracle.com/en/java/javase/17/docs/api/java.sql/javax/sql/package-summary.html) to supplements java.sql
    * [javax.sql.DataSource](https://docs.oracle.com/en/java/javase/17/docs/api/java.sql/javax/sql/DataSource.html) for factory for db connections factory (better alternative than
      [java.sql.DriverManager](https://docs.oracle.com/en/java/javase/17/docs/api/java.sql/java/sql/DriverManager.html))
    * [javax.sql.RowSet](https://docs.oracle.com/en/java/javase/17/docs/api/java.sql/javax/sql/RowSet.html)
      (and subinterfaces in [javax.sql.rowset](https://docs.oracle.com/en/java/javase/17/docs/api/java.sql.rowset/javax/sql/rowset/package-summary.html))
      as a wrapper around a
      [ResultSet](https://docs.oracle.com/en/java/javase/17/docs/api/java.sql/java/sql/ResultSet.html)
        that can be disconnected and serializable
  * [java.util](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/package-summary.html)
    * TODO
    * [java.util.Locale](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Locale.html)
    * [java.util.Properties](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Properties.html)
    * [java.util.Random](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Random.html)
    * [java.util.UUID](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/UUID.html)
  * [java.util.concurrent](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/concurrent/package-summary.html)
    for high-level concurrency features like
    * [java.util.concurrent.Executor](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/concurrent/Executor.html) for launching and managing threads
    * [java.util.concurrent.ConcurrentLinkedQueue](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/concurrent/ConcurrentLinkedQueue.html)
    * [java.util.concurrent.ConcurrentHashMap](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/concurrent/ConcurrentHashMap.html)
  * [java.util.concurrent.atomic](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/concurrent/atomic/package-summary.html)
    for thread-safe classes to managed single variable like
    * [java.util.concurrent.atomic.AtomicBoolean](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/concurrent/atomic/AtomicBoolean.html)
    * [java.util.concurrent.atomic.AtomicInteger](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/concurrent/atomic/AtomicInteger.html)
    * [java.util.concurrent.atomic.AtomicLong](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/concurrent/atomic/AtomicLong.html)
  * [java.util.fonction](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/function/package-summary.html):
    for functional interfaces to be used in lambda expressions and method references; e.g.
    * [java.util.function.Consumer](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/function/Consumer.html)
    * [java.util.function.Function](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/function/Function.html)
    * [java.util.function.Predicate](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/function/Predicate.html)
    * [java.util.function.Supplier](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/function/Supplier.html)
  * [java.util.jar](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/jar/package-summary.html) 
    to package/unpack java libs
    * [java.util.jar.Manifest](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/jar/Manifest.html)
  * [java.util.random](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/random/package-summary.html) 
    for stream based random number generation
  * [java.util.regex](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/regex/package-summary.html)
    for matching character sequences against regular expressions
    * [java.util.regex.Pattern](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/regex/Pattern.html) as regular expression
    * [java.util.regex.Matcher](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/regex/Matcher.html) as regex engine
  * [java.util.zip](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/zip/package-summary.html) 
    for zipping/unzipping; see [tutorial](https://www.baeldung.com/java-compress-and-uncompress)
* see also [New API since JDK 11](https://docs.oracle.com/en/java/javase/17/docs/api/new-list.html)

[*Go to top*](#Java)


## Third-party APIs

* [commons-lang](https://commons.apache.org/proper/commons-lang/)
  * [RandomUtils](https://commons.apache.org/proper/commons-lang/javadocs/api-release/org/apache/commons/lang3/RandomUtils.html) and [RandomStringUtils](https://commons.apache.org/proper/commons-lang/javadocs/api-release/org/apache/commons/lang3/RandomStringUtils.html) for random values
  * [StringUtils](https://commons.apache.org/proper/commons-lang/javadocs/api-release/org/apache/commons/lang3/StringUtils.html) for [isBlank(...)](https://commons.apache.org/proper/commons-lang/javadocs/api-release/org/apache/commons/lang3/StringUtils.html#isBlank-java.lang.CharSequence-), etc.
  * [ToStringBuilder](https://commons.apache.org/proper/commons-lang/javadocs/api-release/org/apache/commons/lang3/builder/ToStringBuilder.html),
    [EqualsBuilder](https://commons.apache.org/proper/commons-lang/javadocs/api-release/org/apache/commons/lang3/builder/EqualsBuilder.html), 
    [HashCodeBuilder](https://commons.apache.org/proper/commons-lang/javadocs/api-release/org/apache/commons/lang3/builder/HashCodeBuilder.html) for simplier toString(), equals(), hashCode() implementation
  * [Pair](https://commons.apache.org/proper/commons-lang/javadocs/api-release/org/apache/commons/lang3/tuple/Pair.html) tuple
* [guava](https://github.com/google/guava) provide core Java libraries from Google
* [JPA](https://jakarta.ee/specifications/persistence/) and [JPQL](https://en.wikipedia.org/wiki/Jakarta_Persistence_Query_Language) to persist and query data with [EclipseLink](https://www.eclipse.org/eclipselink/) or [hibernate](https://hibernate.org/) as JPA implementation
* [Jakarta Bean Validation](https://beanvalidation.org/) to validate objects
* [SLF4J](https://www.slf4j.org/) and [logback](https://logback.qos.ch/index.html) to logs
* JSON support with [Jakson](https://github.com/FasterXML/jackson),
  [Gson](https://github.com/google/gson), 
  [JSON](https://github.com/stleary/JSON-java)
  ; see also [article on compare of libs](https://www.innoq.com/en/articles/2022/02/java-json/)
* caching with [ehcache](https://www.ehcache.org/), [cache2k](https://cache2k.org/) or [guava](https://github.com/google/guava/wiki/CachesExplained); see [comparisons](https://blog.actorsfit.com/a?ID=01250-d3d1718a-1629-447f-ac7b-d9afc18ef2c1)
* testing with [junit5](https://junit.org/junit5/),
  * [Java Hamcrest](http://hamcrest.org/JavaHamcrest/) to have better matchers
  * [mockito](https://site.mockito.org/) to have mocks; see also [Mockito vs EasyMock vs JMockit](https://www.baeldung.com/mockito-vs-easymock-vs-jmockit)
* [Jakarta Servlet](https://en.wikipedia.org/wiki/Jakarta_Servlet) to provide web applications (usually hidden behind a framework)
* dependency injection with [Guice](https://github.com/google/guice) or [spring-context](https://www.baeldung.com/inversion-control-and-dependency-injection-in-spring)
  ; see also [comparison](https://www.baeldung.com/guice-spring-dependency-injection)
* [Thymeleaf](https://www.thymeleaf.org/) :
  HTML template engine for web/non-web environments as substitute for JSP
  * see `spring-boot-starter-thymeleaf` for Spring Framework integration

### Out of scope

Libraries that should be avoided because adding extra complexity:
  * [lombok](https://projectlombok.org/) 
  * [aspectj](https://www.eclipse.org/aspectj/) ([aspect-oriented programming](https://en.wikipedia.org/wiki/Aspect-oriented_programming))

[*Go to top*](#Java)


## Tools

* [java](https://docs.oracle.com/en/java/javase/17/docs/specs/man/java.html) to launch a Java application
* [jar](https://docs.oracle.com/en/java/javase/17/docs/specs/man/jar.html) to package programs/libs; see [tutorial](https://docs.oracle.com/javase/tutorial/deployment/jar/index.html)
* [javac](https://docs.oracle.com/en/java/javase/17/docs/specs/man/javac.html) to compile java into class files / bytecode
* [javadoc](https://docs.oracle.com/en/java/javase/17/docs/specs/man/javadoc.html)
  to generate API documentation as HTML pages; see
  [standard doclet specifications](https://docs.oracle.com/en/java/javase/17/docs/specs/javadoc/doc-comment-spec.html)
* [maven](https://maven.apache.org/),
  [gradle](https://gradle.org/) as build process and dependencies management
* [hsql](http://hsqldb.org/), 
  [H2](https://www.h2database.com/html/main.html),
  [Apache Derby](https://db.apache.org/derby/) as in-memory databases
* [flyway](https://flywaydb.org/) as database version control
* [tomcat](https://tomcat.apache.org/),
  [jetty](https://www.eclipse.org/jetty/),
  [undertow](https://undertow.io/) as web containers
* [visualvm](https://visualvm.github.io/) as java profiler
* [jmeter](https://jmeter.apache.org/) to test performance of web apps
* [selenium](https://www.selenium.dev/) to automate testing of web apps
* [jenkins](https://www.jenkins.io/) for continuous integration

[*Go to top*](#Java)


## Web frameworks

* [Spring Boot](SpringBoot.md) :
  framework ease writing of web applications in Java
* [Dropwizard](https://www.dropwizard.io/en/latest/) :
  Java framework for rapid development of RESTful web services
* [Quarkus](https://quarkus.io/) : 
  Cloudnative microservices oriented Java stack 
* [Micronaut](https://micronaut.io/)  
  Cloudnative microservice/serverless full-stack framework
* [JHipster](https://www.jhipster.tech/) :
  microservice web application generator using Angular or React and the Spring Framework
* see [Spring vs. the World: Comparing Spring Boot Alternatives](https://www.jrebel.com/blog/spring-boot-alternatives)
  * Cloudnative solutions requires a cloud container (docker), SpringBoot/Dropwizard provide embedded server

[*Go to top*](#Java)


## Design patterns

* TODO: summary of 'effective java' ?

[*Go to top*](#Java)


## Reactive programming

TODO part of Third-party APIs ?

TODO add section about reactive programming and java
https://github.com/ReactiveX/RxJava

* reactive programming
  * http://reactivex.io/
  * https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/Flow.html
  * https://projectreactor.io/ (Spring Reactor)
  * Spring Flux
  * https://www.nurkiewicz.com/2019/02/rxjava-vs-reactor.html
  * https://hmh.engineering/spring-web-flux-project-reactor-a645c8f50c8d?gi=e3fe9f1b41b5
  * https://www.baeldung.com/rxjava-vs-java-flow-api

[*Go to top*](#Java)


## Alternatives

Other popular JVM languages:
* [Kotlin](https://kotlinlang.org/),
* [Scala](https://www.scala-lang.org/),
* [Groovy](https://groovy-lang.org/),
* [Clojure](https://clojure.org/)

[*Go to top*](#Java)


## Links

TODO
* [JDK 17 Documentation](https://docs.oracle.com/en/java/javase/17/)
* [JDK 17 Tool Specifications](https://docs.oracle.com/en/java/javase/17/docs/specs/man/index.html)  
* [Specification for the Standard Doclet (for javadoc)](https://docs.oracle.com/en/java/javase/17/docs/specs/javadoc/doc-comment-spec.html)  
* [JDK Release Notes](https://www.oracle.com/java/technologies/javase/jdk-relnotes-index.html)
* [The Java Tutorials](https://docs.oracle.com/javase/tutorial/) (based on JDK 8)
* good course on pluralsigh --> new from java xyz?
* check out whyzlab, certifications tools & learning path
* references
  * [language specifications](https://docs.oracle.com/javase/specs/index.html)
    * https://docs.oracle.com/javase/specs/jls/se17/html
  * books:
    TODO https://mitpress.mit.edu/books/java-precisely-third-edition ? (suggestion effective java)
    [Modern Java in Action](https://www.manning.com/books/modern-java-in-action),
    [Effective Java 3rd ed](https://www.oreilly.com/library/view/effective-java/9780134686097/)
  * [Lambdas and Streams Master Class Part 1](https://www.youtube.com/watch?v=ePXnCezwRuw) and [Part 2](https://www.youtube.com/watch?v=2c_KNH3s2S0)
  * [exam java se 11](https://education.oracle.com/fr/upgrade-ocp-java-6-7-8-to-java-se-11-developer/pexam_1Z0-817): [learning path](https://enthuware.com/pass-java-1z0-817-certification-exam), [preparation](https://www.whizlabs.com/blog/ocp-java-11-upgrade-1z0-817-exam-preparation/)

[*Go to top*](#Java)
