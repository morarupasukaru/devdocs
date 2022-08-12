# Java

[Java](https://en.wikipedia.org/wiki/Java_(software_platform)) is a popular general-purpose language.

This document try to summarize best of Java to develop REST APIs (or batches).

* [Language features](#Language-features)
* [Standard APIs](#Standard-APIs)
* [Third-party APIs](#Third-party-APIs)
* [Tools](#Tools)
* [Web frameworks](#Web-frameworks)
* [Design patterns](#Design-patterns)
* [Alternatives](#Alternatives)
* [Links](#Links)

*(Page mainly written in spring 2022; in progress)*

[*Go to parent page*](../README.md)


## Language features

* [Java history](https://en.wikipedia.org/wiki/Java_version_history)
  and [updates](https://docs.oracle.com/en/java/javase/17/language/java-language-changes.html):
  * 2022 - Java SE 17 :
    [sealed classes](https://docs.oracle.com/en/java/javase/16/language/sealed-classes-and-interfaces.html)
    to restrict classes/interfaces inheritance
  * 2021 - Java SE 16 :
    [records](https://docs.oracle.com/en/java/javase/16/language/records.html) as immutable tuple
  * 2019-2020 - Java SE 13-15 : nothing interesting
  * 2019 - Java SE 12 : 
    [switch expressions](https://docs.oracle.com/en/java/javase/14/language/switch-expressions.html)
  * 2018 - Java SE 11 :
      [java.net.http.HttpClient](https://docs.oracle.com/en/java/javase/17/docs/api/java.net.http/java/net/http/HttpClient.html)
      as new HTTP client API
  * 2018 - Java SE 10 : 
    [local variable type inference](https://docs.oracle.com/en/java/javase/17/language/local-variable-type-inference.html)
    (not to overused!)
  * 2017 - Java SE 9:
    [Java platform module system](https://www.oracle.com/ch-de/corporate/features/understanding-java-9-modules.html)
    ([Project Jigsaw](https://openjdk.org/projects/jigsaw/))
  * 2014 - Java SE 8
    [lambda expression](https://docs.oracle.com/javase/tutorial/java/javaOO/lambdaexpressions.html),
    [java.util.stream.Stream](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/stream/Stream.html),
    [java.util.Optional](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Optional.html)
    [date and time API](https://docs.oracle.com/javase/tutorial/datetime/index.html)
  * 2011 - Java SE 7
    [Strings in switch](https://docs.oracle.com/javase/8/docs/technotes/guides/language/strings-switch.html),
    [try-with-resources](https://docs.oracle.com/javase/tutorial/essential/exceptions/tryResourceClose.html),
    [diamond operator <> in generics](https://docs.oracle.com/javase/tutorial/java/generics/types.html#diamond),
  * 2006 - Java SE 6 : nothing interesting
  * 2004 - Java SE 5
    [Generics](https://docs.oracle.com/javase/tutorial/java/generics/index.html),
    [Annotation](https://docs.oracle.com/javase/tutorial/java/annotations/index.html),
    [enum](https://docs.oracle.com/javase/tutorial/java/javaOO/enum.html),
    [varargs](https://docs.oracle.com/javase/8/docs/technotes/guides/language/varargs.html),
    [for each loop](https://docs.oracle.com/javase/8/docs/technotes/guides/language/foreach.html),
    [static import](https://docs.oracle.com/javase/8/docs/technotes/guides/language/static-import.html),
    [java.util.concurrent](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/concurrent/package-summary.html)
  * 2002 - J2SE 1.4: 
    [Regular expressions](https://docs.oracle.com/javase/tutorial/essential/regex/index.html)
    and [Chained exceptions](https://docs.oracle.com/javase/tutorial/essential/exceptions/chained.html)
  * 2000 - J2SE 1.3: nothing interesting
  * 1998 - J2SE 1.2: 
   [Collections framework](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/doc-files/coll-overview.html)
  * 1996/1997 - JDK 1.0 / JDK 1.1: JDBC

TODO continue here
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
* quick history of change in java version, feature and APIs
* types, structures, enum, interfaces, classes, package, exception
* annotations, generics
* lambda
* java 12, 13, 14: TODO
* TODO link to java tutorial with java feature? e.g. new "for loop"
  * like JavaScript.md?

https://jenkov.com/tutorials/java/index.html#new-in-java-9

https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html

[*Go to top*](#Java)


## Standard APIs

* [Overview](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/module-summary.html#packages-summary)
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
    * [java.io.Closeable](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/io/Closeable.html)
    * [java.io.Console](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/io/Console.html)
    * [java.io.File](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/io/File.html)
    * [java.io.InputStream](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/io/InputStream.html)
    * [java.io.OutputStream](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/io/OutputStream.html)
    * [java.io.Reader](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/io/Reader.html)
    * [java.io.Writer](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/io/Writer.html)
  * [java.lang](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/package-summary.html)
    * [java.lang.AutoCloseable](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/AutoCloseable.html)
    * [java.lang.Boolean](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Boolean.html)
    * [java.lang.Class](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Class.html)
    * [java.lang.Comparable](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Comparable.html)
    * [java.lang.Enum](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Enum.html)
    * [java.lang.Float](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Float.html)
    * [java.lang.FunctionalInterface](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/FunctionalInterface.html)
    * [java.lang.IllegalArgumentException](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/IllegalArgumentException.html)
    * [java.lang.IllegalStateException](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/IllegalStateException.html)
    * [java.lang.Integer](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Integer.html)
    * [java.lang.Iterable](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Iterable.html)
    * [java.lang.Long](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Long.html)
    * [java.lang.Math](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Math.html): [random()](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Math.html#random())
    * [java.lang.NullPointerException](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/NullPointerException.html)
    * [java.lang.NumberFormatException](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/NumberFormatException.html)
    * [java.lang.OutOfMemoryError](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/OutOfMemoryError.html)
    * [java.lang.Process](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Process.html)
    * [java.lang.ProcessBuilder](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/ProcessBuilder.html)
    * [java.lang.Runnable](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Runnable.html)
    * [java.lang.RuntimeException](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/RuntimeException.html)
    * [java.lang.String](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/String.html)
      * [matches(regex)](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/String.html#matches(java.lang.String))
      * [split(regex)](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/String.html#split(java.lang.String))
    * [java.lang.StringBuilder](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/StringBuilder.html)
    * [java.lang.System](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/System.html)
    * [java.lang.Thread](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Thread.html)
    * [java.lang.ThreadLocal](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/ThreadLocal.html)
    * [java.lang.UnsupportedOperationException](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/UnsupportedOperationException.html)
    * [java.lang.Void](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Void.html)
  * [java.math](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/math/package-summary.html)
    * [java.math.BigDecimal](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/math/BigDecimal.html)
    * [java.math.BigInteger](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/math/BigInteger.html)
  * [java.net](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/net/package-summary.html)
    * [java.net.URL](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/net/URL.html)
    * [java.net.URLDecoder](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/net/URLDecoder.html)
    * [java.net.URLEncoder](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/net/URLEncoder.html) 
    * [java.net.URI](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/net/URI.html)
    * [java.net.http.HttpClient](https://docs.oracle.com/en/java/javase/17/docs/api/java.net.http/java/net/http/HttpClient.html)
    * [java.net.http.HttpClient.Builder](https://docs.oracle.com/en/java/javase/17/docs/api/java.net.http/java/net/http/HttpClient.Builder.html)
    * [java.net.http.HttpResponse](https://docs.oracle.com/en/java/javase/17/docs/api/java.net.http/java/net/http/HttpResponse.html)
    * [java.net.http.HttpRequest](https://docs.oracle.com/en/java/javase/17/docs/api/java.net.http/java/net/http/HttpRequest.html)
  * [java.nio](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/nio/package-summary.html)
    * [java.nio.charset.StandardCharsets](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/nio/charset/StandardCharsets.html)  
    * [java.nio.file.FileStore](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/nio/file/FileStore.html)
    * [java.nio.file.FileSystem](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/nio/file/FileSystem.html)
    * [java.nio.file.Files](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/nio/file/Files.html)
    * [java.nio.file.Path](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/nio/file/Path.html)
    * [java.nio.file.Paths](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/nio/file/Paths.html)
    * [java.nio.file.StandardOpenOption](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/nio/file/StandardOpenOption.html)
  * [java.text](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/text/package-summary.html)
    * [java.text.DecimalFormat](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/text/DecimalFormat.html)
    * [java.text.NumberFormat](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/text/NumberFormat.html)
  * [java.time](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/time/package-summary.html)  
    * [java.time.Duration](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/time/Duration.html)
    * [java.time.LocalDate](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/time/LocalDate.html)
    * [java.time.LocalDateTime](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/time/LocalDateTime.html)
    * [java.time.LocalTime](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/time/LocalTime.html)
    * [java.time.ZonedDateTime](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/time/ZonedDateTime.html)
    * [java.time.format.DateTimeFormatter](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/time/format/DateTimeFormatter.html)
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
    * [java.util.ArrayList](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/ArrayList.html)
    * [java.util.Arrays](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Arrays.html)
    * [java.util.Base64](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Base64.html)
    * [java.util.Collection](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Collection.html)
    * [java.util.Collections](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Collections.html)
    * [java.util.Currency](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Currency.html)
    * [java.util.EnumMap](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/EnumMap.html)
    * [java.util.EnumSet](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/EnumSet.html)
    * [java.util.Formatter](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Formatter.html)
    * [java.util.HashMap](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/HashMap.html)
    * [java.util.HashSet](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/HashSet.html)
    * [java.util.Iterator](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Iterator.html)
    * [java.util.LinkedHashMap](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/LinkedHashMap.html)
    * [java.util.LinkedHashSet](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/LinkedHashSet.html)
    * [java.util.LinkedList](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/LinkedList.html)
    * [java.util.List](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/List.html)
    * [java.util.Locale](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Locale.html)
    * [java.util.Map](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Map.html)
    * [java.util.Objects](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Objects.html)
    * [java.util.Optional](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Optional.html)
    * [java.util.Properties](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Properties.html)
    * [java.util.Random](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Random.html)
    * [java.util.Set](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Set.html)
    * [java.util.TreeMap](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/TreeMap.html)
    * [java.util.TreeSet](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/TreeSet.html)
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
  * [java.util.stream.Stream](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/stream/Stream.html)
    for streams API based on lambda expressions
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
* reactive programming
  * [ReactiveX](https://reactivex.io/)
  * [Project Reactor](https://projectreactor.io/) internally used by
    [Spring WebFlux](https://docs.spring.io/spring-framework/docs/current/reference/html/web-reactive.html)
  * ([java.util.concurrent.Flow](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/concurrent/Flow.html)
    API is used by JDK internally to have reactive-streams without external dependency like ReactiveX or Project Reactor)
  * see [RxJava vs Reactor](https://www.nurkiewicz.com/2019/02/rxjava-vs-reactor.html)

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


## Alternatives

Other popular JVM languages:
* [Kotlin](https://kotlinlang.org/)
* [Scala](https://www.scala-lang.org/)
* [Groovy](https://groovy-lang.org/)
* [Clojure](https://clojure.org/)

[*Go to top*](#Java)


## Links

* [Java language updates](https://docs.oracle.com/en/java/javase/17/language/java-language-changes.html) (from Java SE 9)
* [JDK 17 Documentation](https://docs.oracle.com/en/java/javase/17/)
* [JDK 17 Tool Specifications](https://docs.oracle.com/en/java/javase/17/docs/specs/man/index.html)  
* [Specification for the Standard Doclet](https://docs.oracle.com/en/java/javase/17/docs/specs/javadoc/doc-comment-spec.html) (javadoc)
* [The Java Tutorials](https://docs.oracle.com/javase/tutorial/) (based on JDK 8)
* [Effective Java 3rd ed](https://www.oreilly.com/library/view/effective-java/9780134686097/) (book)

[*Go to top*](#Java)
