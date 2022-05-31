# Java

[Java](https://en.wikipedia.org/wiki/Java_(software_platform)) is a popular general-purpose language.

*(Page mainly written in TODO 2022)*

[*Go to parent page*](../../README.md)


## TODO

This document try to summarize best of Java to develop REST APIs or batches.

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
* Popular APIs
  * JPA
  * Bean Validation
  * Logging
  * ...
* J2EE takeaway
  * Servlet?
* Frameworks
  * SpringBoot -> Servlet based?
  * Dropwizard
  * Micronaut
  * Quarkus
  * etc.
* Other JVM languages
  * Scala
  * Kotlin
  * ...
  
* concept: [POJO](https://en.wikipedia.org/wiki/Plain_old_Java_object)
## Java SE APIs

* Collections framework
* Regexp
* I/O (way to do in 2022)
* Concurrency - [java.util.concurrent](https://docs.oracle.com/javase/1.5.0/docs/guide/concurrency/overview.html)
* JDBC (modern way)

## External APIs

* Logging
* JSON
* Lombok --> lib? extension?

https://en.wikipedia.org/wiki/List_of_Java_APIs

* [JDK Release Notes](https://www.oracle.com/java/technologies/javase/jdk-relnotes-index.html)  
* [The Java Tutorials](https://docs.oracle.com/javase/tutorial/) (based on JDK 8)

* TODO: high-overview of java
* TODO: *javalight / good parts of java* with latest versions of java
* TODO: sumary of 'java in action' ?
* TODO: summary of 'effective java' ?

*(Page mainly written in TODO)*

* good course on pluralsigh --> new from java xyz?
* check out whyzlab, certifications tools & learning path

[*Go to parent page*](../README.md)

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
* API
  * TODO link to javadocs
  * TODO link to https://docs.oracle.com/javase/tutorial/
  * jse: collections, datetime, jdbc, concurrency, regexp, java stream api, file i/o, localization
    * java.base
    * java.sql
      * collections
      * (concurrency)
      * i/o
      * math
      * jdbc
      * date and time
      * regexp
      * misc
        * properties
        * locale
        * uri
        * uuid, ulid?
  * misc: typical useful annotation (@VisibleForTesting, @Immutable, @Safe)
* ecosystems
  * libraries
    * TODO check spring boot and quarkus list of libs to find best of them
  * frameworks: [SpringBoot](./SpringBoot.md), [Quarkus](https://quarkus.io/get-started/)
  * tools: jprofiler, visualvm, mvn
* references
  * [language specifications](https://docs.oracle.com/javase/specs/index.html)
    *   * https://docs.oracle.com/javase/specs/jls/se16/html/index.html
  * books:
    TODO https://mitpress.mit.edu/books/java-precisely-third-edition ? (suggestion effective java)
    [Modern Java in Action](https://www.manning.com/books/modern-java-in-action), 
    [Effective Java 3rd ed](https://www.oreilly.com/library/view/effective-java/9780134686097/)
  * [Lambdas and Streams Master Class Part 1](https://www.youtube.com/watch?v=ePXnCezwRuw) and [Part 2](https://www.youtube.com/watch?v=2c_KNH3s2S0)
  * [exam java se 11](https://education.oracle.com/fr/upgrade-ocp-java-6-7-8-to-java-se-11-developer/pexam_1Z0-817): [learning path](https://enthuware.com/pass-java-1z0-817-certification-exam), [preparation](https://www.whizlabs.com/blog/ocp-java-11-upgrade-1z0-817-exam-preparation/)
    
*(Page not yet completed)*


## Summary Effective Java 3d Edition

* TODO


## Summary Modern Java in Action

* TODO

TODO maven

## Reactive Programming

TODO add section about reactive programming and java

* reactive programming
  * http://reactivex.io/
  * https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/Flow.html
  * https://projectreactor.io/ (Spring Reactor)
  * Spring Flux
  * https://www.nurkiewicz.com/2019/02/rxjava-vs-reactor.html
  * https://hmh.engineering/spring-web-flux-project-reactor-a645c8f50c8d?gi=e3fe9f1b41b5
  * https://www.baeldung.com/rxjava-vs-java-flow-api
  
[*Go to parent page*](../../README.md)
