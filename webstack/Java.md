# Java

[Java](https://en.wikipedia.org/wiki/Java_(software_platform)) is a popular general-purpose language.

This document try to summarize best of Java to develop REST APIs (or batches).

* [Language](#Language)
* [History](#History)
* [Standard APIs](#Standard-APIs)
* [Third-party APIs](#Third-party-APIs)
* [Tools](#Tools)
* [Web frameworks](#Web-frameworks)
* [Effective java](#Effective-java)
* Alternative JVM languages:
  [Kotlin](https://kotlinlang.org/),
  [Scala](https://www.scala-lang.org/),
  [Groovy](https://groovy-lang.org/),
  [Clojure](https://clojure.org/)
* Links
  * [OpenJDK on adoptium.net](https://adoptium.net/)
  * [Java SE javadoc](https://docs.oracle.com/en/java/javase/21/docs/api/new-list.html)
  * [Java language updates](https://docs.oracle.com/en/java/javase/21/language/java-language-changes.html) (from Java SE 9)
  * [JDK 21 Documentation](https://docs.oracle.com/en/java/javase/21/)
  * [JDK 21 Tool Specifications](https://docs.oracle.com/en/java/javase/21/docs/specs/man/index.html)
  * [The Java Version Almanac](https://javaalmanac.io/)
  * [Specification for the Standard Doclet](https://docs.oracle.com/en/java/javase/21/docs/specs/javadoc/doc-comment-spec.html) (javadoc)
    * [How to Write Doc Comments for the Javadoc Tool](https://www.oracle.com/technical-resources/articles/java/javadoc-tool.html#:~:text=A%20doc%20comment%20is%20written,%40return%20%2C%20and%20%40see%20.) 
  * [The Java Tutorials](https://docs.oracle.com/javase/tutorial/) (based on JDK 8)
  * [Effective Java 3rd ed](https://www.oreilly.com/library/view/effective-java/9780134686097/) (book)
  * [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)
  * [JSON](https://www.json.org/json-en.html) or
    [protobuf](https://developers.google.com/protocol-buffers) as alternative to
    [Java serialization](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/io/Serializable.html)

[*Go to parent page*](../README.md)

## Language

* [basic concepts](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/index.html)
  * [variables](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/variables.html)
    as [primitive data types](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html)
    or [array](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html)
  * [operators](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/operators.html)
  * [expressions, statements, and blocks](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/expressions.html)
  * [control flow](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/flow.html)
    with [if-then-else](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/if.html), 
    [switch](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/switch.html),  
    [while and do-while loop](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/while.html),
    [for loop](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/for.html),
    [for each loop](https://docs.oracle.com/javase/8/docs/technotes/guides/language/foreach.html),
    [break, continue, return](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/branch.html)
* [object oriented](https://docs.oracle.com/javase/tutorial/java/javaOO/index.html)
  * [classes](https://docs.oracle.com/javase/tutorial/java/javaOO/classes.html)
  * [objects](https://docs.oracle.com/javase/tutorial/java/javaOO/objects.html)
  * [nested classes](https://docs.oracle.com/javase/tutorial/java/javaOO/nested.html)
  * [lambda expressions](https://docs.oracle.com/javase/tutorial/java/javaOO/lambdaexpressions.html)
    and [method references](https://docs.oracle.com/javase/tutorial/java/javaOO/methodreferences.html)
  * [enums](https://docs.oracle.com/javase/tutorial/java/javaOO/enum.html)
  * [interfaces](https://docs.oracle.com/javase/tutorial/java/IandI/createinterface.html)
  * [inheritance / subclasses](https://docs.oracle.com/javase/tutorial/java/IandI/subclasses.html)
* other concepts
  * [packages](https://docs.oracle.com/javase/tutorial/java/package/index.html)
  * [numbers](https://docs.oracle.com/javase/tutorial/java/data/numbers.html)
  * [strings](https://docs.oracle.com/javase/tutorial/java/data/strings.html)
  * [annotations](https://docs.oracle.com/javase/tutorial/java/annotations/index.html)
  * [autoboxing and unboxing](https://docs.oracle.com/javase/tutorial/java/data/autoboxing.html)
  * [generics](https://docs.oracle.com/javase/tutorial/java/generics/index.html)
    (see also [changes from Java SE 5](https://docs.oracle.com/javase/tutorial/extra/generics/index.html)) 
  * [exceptions](https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html)
  * [virtual threads](https://docs.oracle.com/en/java/javase/21/core/virtual-threads.html);
    see [article](https://foojay.io/today/unleashing-the-power-of-lightweight-concurrency-a-comprehensive-guide-to-java-virtual-threads-part-1/) and
    [What are Java Virtual Threads ?](https://engineeringatscale.substack.com/p/what-are-java-virtual-threads)
  * [java preview features](https://www.baeldung.com/java-preview-features)
  * see also [history](#History) for other language/API features

[*Go to top*](#Java)


## History

* [Java history](https://en.wikipedia.org/wiki/Java_version_history)
  and [updates](https://docs.oracle.com/en/java/javase/21/language/java-language-changes.html):
  * _future features_:
    * [value classes](https://en.wikipedia.org/wiki/Value_type_and_reference_type)
      with [project valhalla](https://openjdk.org/projects/valhalla/) for better performances
  * 2023 - Java SE 21:
    [virtual threads](https://docs.oracle.com/en/java/javase/21/core/virtual-threads.html)
    for lightweight concurrency and better performances
  * 2022-2023 - Java SE 18-21 : nothing interesting
  * 2022 - Java SE 17 :
    [sealed classes](https://docs.oracle.com/en/java/javase/21/language/sealed-classes-and-interfaces.html)
    to restrict classes/interfaces inheritance
  * 2021 - Java SE 16 :
    [records](https://docs.oracle.com/en/java/javase/21/language/records.html) as immutable tuple
  * 2019-2020 - Java SE 13-15 : nothing interesting
  * 2019 - Java SE 12 : 
    [switch expressions](https://docs.oracle.com/en/java/javase/21/language/switch-expressions.html)
  * 2018 - Java SE 11 :
      [java.net.http.HttpClient](https://docs.oracle.com/en/java/javase/21/docs/api/java.net.http/java/net/http/HttpClient.html)
      as new HTTP client API
  * 2018 - Java SE 10 : 
    [local variable type inference](https://docs.oracle.com/en/java/javase/21/language/local-variable-type-inference.html)
    (not to overused!)
  * 2017 - Java SE 9:
    [Java platform module system](https://www.oracle.com/corporate/features/understanding-java-9-modules.html)
    ([project jigsaw](https://openjdk.org/projects/jigsaw/))
  * 2014 - Java SE 8
    [lambda expression](https://docs.oracle.com/javase/tutorial/java/javaOO/lambdaexpressions.html),
    [java.util.stream.Stream](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/stream/Stream.html),
    [java.util.Optional](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Optional.html),
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
    [java.util.concurrent](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/concurrent/package-summary.html)
  * 2002 - J2SE 1.4: 
    [Regular expressions](https://docs.oracle.com/javase/tutorial/essential/regex/index.html),
    [Chained exceptions](https://docs.oracle.com/javase/tutorial/essential/exceptions/chained.html)
  * 2000 - J2SE 1.3: nothing interesting
  * 1998 - J2SE 1.2: 
   [Collections framework](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/doc-files/coll-overview.html)
  * 1996/1997 - JDK 1.0 / JDK 1.1: JDBC
* Platforms
  * [Java SE](https://en.wikipedia.org/wiki/Java_Platform,_Standard_Edition) (Standard Edition)
  * [Java EE or Jakarta EE](https://en.wikipedia.org/wiki/Jakarta_EE) (Enterprise Edition) extends Java SE with some entreprise feature
    * most features are not usefull with modern frameworks
    * important features: [Bean Validation](https://en.wikipedia.org/wiki/Bean_Validation),
      [JPA](https://en.wikipedia.org/wiki/Jakarta_Persistence)
      [Servlet](https://en.wikipedia.org/wiki/Jakarta_Servlet)
    * package renaming happens with transfer of Java EE from Orace to Eclipse Foundation
  * out of scope:
    [Java ME](https://en.wikipedia.org/wiki/Java_Platform,_Micro_Edition),
    [Java Card](https://en.wikipedia.org/wiki/JavaFX),
    [JavaFX](https://en.wikipedia.org/wiki/Java_Card)

[*Go to top*](#Java)


## Standard APIs

* [New API since JDK 11](https://docs.oracle.com/en/java/javase/21/docs/api/new-list.html)
* [Overview](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/module-summary.html#packages-summary)
  * [java.base](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/module-summary.html#packages-summary) module
    * [java.nio.file](https://docs.oracle.com/javase/tutorial/essential/io/fileio.html)
      for file i/o 
    * [java.util.regex](https://docs.oracle.com/javase/tutorial/essential/regex/index.html)
      for regular expressions
    * [java.util.concurrent](https://docs.oracle.com/javase/tutorial/essential/concurrency/highlevel.html)
      for high-level concurrency APIs
    * [java.util | java.util.concurrent - java collection frameworks](https://docs.oracle.com/javase/8/docs/technotes/guides/collections/overview.html)
      for common data structures (list, map, etc.)
      ; see [tutorial](https://docs.oracle.com/javase/tutorial/collections/index.html)
    * [java.time](https://docs.oracle.com/javase/tutorial/datetime/index.html)
      for date/time
    * [java.net](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/net/package-summary.html)
      for networking
  * [java.net.http](https://docs.oracle.com/en/java/javase/21/docs/api/java.net.http/module-summary.html)
    module  
    * [java.net.http](https://docs.oracle.com/en/java/javase/21/docs/api/java.net.http/java/net/http/package-summary.html)
      for new HTTP client API
  * [java.sql](https://docs.oracle.com/en/java/javase/21/docs/api/java.sql/module-summary.html),
    [java.sql.rowset](https://docs.oracle.com/en/java/javase/21/docs/api/java.sql.rowset/module-summary.html)
    modules
    * [java.sql | javax.sql](https://docs.oracle.com/javase/tutorial/jdbc/basics/index.html)
      for database access (jdbc) 
* Major packages & classes
  * [java.io](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/io/package-summary.html):
    * [Closeable](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/io/Closeable.html),
    [Console](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/io/Console.html),
    [File](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/io/File.html),
    [InputStream](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/io/InputStream.html),
    [OutputStream](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/io/OutputStream.html),
    [Reader](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/io/Reader.html),
    [Writer](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/io/Writer.html)
  * [java.lang](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/package-summary.html):
    * [AutoCloseable](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/AutoCloseable.html),
    [Boolean](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Boolean.html),
    [Class](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Class.html),
    [Comparable](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Comparable.html),
    [Enum](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Enum.html),
    [Float](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Float.html),
    [@FunctionalInterface](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/FunctionalInterface.html),
    [IllegalArgumentException](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/IllegalArgumentException.html),
    [IllegalStateException](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/IllegalStateException.html),
    [Integer](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Integer.html),
    [Iterable](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Iterable.html),
    [Long](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Long.html),
    [Math](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Math.html),
    [NullPointerException](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/NullPointerException.html),
    [NumberFormatException](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/NumberFormatException.html),
    [OutOfMemoryError](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/OutOfMemoryError.html),
    [@Override](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Override.html),
    [Process](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Process.html),
    [ProcessBuilder](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/ProcessBuilder.html),
    [Runnable](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Runnable.html),
    [RuntimeException](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/RuntimeException.html),
    [@SafeVarargs](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/SafeVarargs.html)
    [String](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/String.html),
    [StringBuilder](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/StringBuilder.html),
    [@SuppressWarning](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/SuppressWarnings.html),
    [System](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/System.html),
    [Thread](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Thread.html),
    [ThreadLocal](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/ThreadLocal.html),
    [UnsupportedOperationException](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/UnsupportedOperationException.html),
    [Void](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Void.html)
  * [java.math](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/math/package-summary.html):
    [BigDecimal](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/math/BigDecimal.html),
    [BigInteger](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/math/BigInteger.html)
  * [java.net](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/net/package-summary.html):
    * [HttpClient](https://docs.oracle.com/en/java/javase/21/docs/api/java.net.http/java/net/http/HttpClient.html),
    [HttpClient.Builder](https://docs.oracle.com/en/java/javase/21/docs/api/java.net.http/java/net/http/HttpClient.Builder.html),
    [HttpResponse](https://docs.oracle.com/en/java/javase/21/docs/api/java.net.http/java/net/http/HttpResponse.html),
    [HttpRequest](https://docs.oracle.com/en/java/javase/21/docs/api/java.net.http/java/net/http/HttpRequest.html),
    [URL](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/net/URL.html),
    [URLDecoder](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/net/URLDecoder.html),
    [URLEncoder](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/net/URLEncoder.html) ,
    [URI](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/net/URI.html)
  * [java.nio](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/nio/package-summary.html):
    * [StandardCharsets](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/nio/charset/StandardCharsets.html),
    [FileStore](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/nio/file/FileStore.html),
    [FileSystem](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/nio/file/FileSystem.html),
    [Files](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/nio/file/Files.html),
    [Path](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/nio/file/Path.html),
    [Paths](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/nio/file/Paths.html),
    [StandardOpenOption](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/nio/file/StandardOpenOption.html)
  * [java.text](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/text/package-summary.html):
    [DecimalFormat](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/text/DecimalFormat.html),
    [NumberFormat](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/text/NumberFormat.html)
  * [java.time](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/time/package-summary.html):
    * [Duration](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/time/Duration.html),
    [LocalDate](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/time/LocalDate.html),
    [LocalDateTime](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/time/LocalDateTime.html),
    [LocalTime](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/time/LocalTime.html),
    [ZonedDateTime](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/time/ZonedDateTime.html),
    [DateTimeFormatter](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/time/format/DateTimeFormatter.html)
  * [java.sql](https://docs.oracle.com/en/java/javase/21/docs/api/java.sql/java/sql/package-summary.html) for DB API:
    * [Connection](https://docs.oracle.com/en/java/javase/21/docs/api/java.sql/java/sql/Connection.html),
    [ResultSet](https://docs.oracle.com/en/java/javase/21/docs/api/java.sql/java/sql/ResultSet.html),
    [Statement](https://docs.oracle.com/en/java/javase/21/docs/api/java.sql/java/sql/Statement.html),
    [PreparedStatement](https://docs.oracle.com/en/java/javase/21/docs/api/java.sql/java/sql/PreparedStatement.html),
    [CallableStatement](https://docs.oracle.com/en/java/javase/21/docs/api/java.sql/java/sql/CallableStatement.html)
  * [javax.sql](https://docs.oracle.com/en/java/javase/21/docs/api/java.sql/javax/sql/package-summary.html) to supplements java.sql:
    [DataSource](https://docs.oracle.com/en/java/javase/21/docs/api/java.sql/javax/sql/DataSource.html),
    [RowSet](https://docs.oracle.com/en/java/javase/21/docs/api/java.sql/javax/sql/RowSet.html) and its subclasses
  * [java.util](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/package-summary.html):
    * [ArrayList](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/ArrayList.html),
    [Arrays](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Arrays.html),
    [Base64](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Base64.html),
    [Collection](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Collection.html),
    [Collections](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Collections.html),
    [Currency](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Currency.html),
    [EnumMap](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/EnumMap.html),
    [EnumSet](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/EnumSet.html),
    [Formatter](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Formatter.html),
    [HashMap](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/HashMap.html),
    [HashSet](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/HashSet.html),
    [Iterator](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Iterator.html),
    [LinkedHashMap](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/LinkedHashMap.html),
    [LinkedHashSet](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/LinkedHashSet.html),
    [LinkedList](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/LinkedList.html),
    [List](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/List.html),
    [Locale](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Locale.html),
    [Map](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Map.html),
    [Objects](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Objects.html),
    [Optional](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Optional.html),
    [Properties](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Properties.html),
    [Set](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Set.html),
    [TreeMap](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/TreeMap.html),
    [TreeSet](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/TreeSet.html),
    [UUID](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/UUID.html)
  * [java.util.concurrent](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/concurrent/package-summary.html)
    for high-level concurrency APIs:
    * [Executors](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/concurrent/Executors.html),
      [Executor](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/concurrent/Executor.html),
      [ConcurrentLinkedQueue](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/concurrent/ConcurrentLinkedQueue.html),
      [ConcurrentHashMap](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/concurrent/ConcurrentHashMap.html),
      [AtomicBoolean](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/concurrent/atomic/AtomicBoolean.html),
      [AtomicInteger](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/concurrent/atomic/AtomicInteger.html),
      [AtomicLong](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/concurrent/atomic/AtomicLong.html),
      [ThreadLocalRandom](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/concurrent/ThreadLocalRandom.html) 
  * [java.util.fonction](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/function/package-summary.html)
    for functional interfaces to be used in lambda expressions/method references:
    * [BinaryOperator](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/function/BinaryOperator.html),
      [Consumer](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/function/Consumer.html),
      [Function](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/function/Function.html),
      [Predicate](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/function/Predicate.html),
      [Supplier](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/function/Supplier.html),
      [UnaryOperator](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/function/UnaryOperator.html),
      ...
  * [java.util.jar](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/jar/package-summary.html) 
    to package/unpack java libs:
    [Manifest](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/jar/Manifest.html)
  * [java.util.random](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/random/package-summary.html) 
    for stream based random number generation
  * [java.util.regex](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/regex/package-summary.html):
    [Pattern](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/regex/Pattern.html),
    [Matcher](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/regex/Matcher.html)
  * [java.util.stream.Stream](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/stream/Stream.html)
    for streams API based on lambda expressions
  * [java.util.zip](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/zip/package-summary.html) 
    for zipping/unzipping; see [tutorial](https://www.baeldung.com/java-compress-and-uncompress)

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
* JSON support with [Jackson](https://github.com/FasterXML/jackson),
  [Gson](https://github.com/google/gson), 
  [JSON](https://github.com/stleary/JSON-java)
  ; see also [article on compare of libs](https://www.innoq.com/en/articles/2022/02/java-json/)
* caching with [ehcache](https://www.ehcache.org/), [cache2k](https://cache2k.org/) or [guava](https://github.com/google/guava/wiki/CachesExplained)
* testing with [junit5](https://junit.org/junit5/),
  * [Java Hamcrest](http://hamcrest.org/JavaHamcrest/) to have better matchers
  * [mockito](https://site.mockito.org/) to have mocks; see also [Mockito vs EasyMock vs JMockit](https://www.baeldung.com/mockito-vs-easymock-vs-jmockit)
* [Jakarta Servlet](https://en.wikipedia.org/wiki/Jakarta_Servlet) to provide web applications (usually hidden behind a framework)
* dependency injection with [Guice](https://github.com/google/guice), [Spring](https://www.baeldung.com/inversion-control-and-dependency-injection-in-spring) or [Dagger](https://dagger.dev/)
  ; see also [comparison](https://www.baeldung.com/guice-spring-dependency-injection)
* [lombok](https://projectlombok.org/) to generate getter, setter, toString, builder, etc.
* [mapstruct](https://mapstruct.org/) to ease mapping of java beans
* [aspectj](https://www.eclipse.org/aspectj/) ([aspect-oriented programming](https://en.wikipedia.org/wiki/Aspect-oriented_programming)) to add cross-cutting concerns (generic functionality needed in many places; e.g. security)
* [Thymeleaf](https://www.thymeleaf.org/) :
  HTML template engine for web/non-web environments as substitute for JSP
  * see `spring-boot-starter-thymeleaf` for Spring Framework integration
* reactive programming
  * [ReactiveX](https://reactivex.io/)
  * [Project Reactor](https://projectreactor.io/) internally used by
    [Spring WebFlux](https://docs.spring.io/spring-framework/docs/current/reference/html/web-reactive.html)
  * ([java.util.concurrent.Flow](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/concurrent/Flow.html)
    API is used by JDK internally to have reactive-streams without external dependency like ReactiveX or Project Reactor)
  * see [RxJava vs Reactor](https://www.nurkiewicz.com/2019/02/rxjava-vs-reactor.html)

[*Go to top*](#Java)


## Tools

* [java](https://docs.oracle.com/en/java/javase/21/docs/specs/man/java.html) to launch a Java application
* [jar](https://docs.oracle.com/en/java/javase/21/docs/specs/man/jar.html) to package programs/libs; see [tutorial](https://docs.oracle.com/javase/tutorial/deployment/jar/index.html)
* [javac](https://docs.oracle.com/en/java/javase/21/docs/specs/man/javac.html) to compile java into class files / bytecode
* [javadoc](https://docs.oracle.com/en/java/javase/21/docs/specs/man/javadoc.html)
  to generate API documentation as HTML pages; see
  [standard doclet specifications](https://docs.oracle.com/en/java/javase/21/docs/specs/javadoc/doc-comment-spec.html)
* [maven](https://maven.apache.org/),
  [gradle](https://gradle.org/) as build process and dependencies management
* [hsql](http://hsqldb.org/), 
  [H2](https://www.h2database.com/html/main.html),
  [Apache Derby](https://db.apache.org/derby/) as in-memory databases
* [flyway](https://flywaydb.org/), 
  [liquibase](https://www.liquibase.com/) as database version control; see [liquibase vs flyway](https://www.liquibase.com/liquibase-vs-flyway)
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
* [Micronaut](https://micronaut.io/) :
  Cloudnative microservice/serverless full-stack framework
* [JHipster](https://www.jhipster.tech/) :
  microservice web application generator using Angular or React and the Spring Framework
* see [Spring vs. the World: Comparing Spring Boot Alternatives](https://www.jrebel.com/blog/spring-boot-alternatives)
  * Cloudnative solutions requires a cloud container (docker), SpringBoot/Dropwizard provide embedded server

[*Go to top*](#Java)


## Effective java

Preferred [Effective Java, 3rd Edition](https://www.oreilly.com/library/view/effective-java/9780134686097/) items:

* _Creating & Destroying objects_
  * consider static factory methods instead of constructor (item 1)
    * [Date.from(instant)](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Date.html#from(java.time.Instant)),
      [EnumSet.of(...)](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/EnumSet.html#of(E,E...)),
      [BigInteger.valueOf(long)](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/math/BigInteger.html#valueOf(long)),
      ...
  * consider a builder when faced many constructor parameters (item 2)
  * prefer dependency injection to hardwiring resources (item 5)
    * use a dependency injection framework like
      [Spring](https://spring.io/),
      [Guice](https://github.com/google/guice),
      [Dagger](https://dagger.dev/)
  * avoid creating unnecessary objects (item 6)
    * ... by using static factory methods (item 1)
  * prefer [try-with-resources](https://docs.oracle.com/javase/tutorial/essential/exceptions/tryResourceClose.html) 
    to try-finally (item 9)
* _Methods common to all objects_
  * obey the general 
    [contract](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Object.html#equals(java.lang.Object)) 
    when overring 
    [equals](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Object.html#equals(java.lang.Object)) (item 10)
  * always override [hashCode](https://docs.oracle.com/javase/7/docs/api/java/lang/Object.html#hashCode()) 
    when you override
    [equals](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Object.html#equals(java.lang.Object)) (item 11)
  * always override 
    [toString](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Object.html#toString())
    (item 12)
    * use IDE to generate equals, hashCode and toString
  * consider implementing 
    [Comparable](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Comparable.html)
    (item 14) 
    * follow 
      [compareTo](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Comparable.html#compareTo(T)) 
      [contract](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Comparable.html#compareTo(T)) 
      to not break other comparison-dependent classes like
      [TreeSet](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/TreeSet.html) or
      [TreeMap](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/TreeMap.html)
    * use [Comparator](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Comparator.html) 
      static construction methods like 
      [Comparator.comparing()](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Comparator.html#comparing(java.util.function.Function))
      ; see [tutorial](https://www.baeldung.com/java-8-comparator-comparing)
* _Classes & Interfaces_ 
  * minimize mutability (item 17)
    * classes should be immutable unless there's a very good reason to make them mutable
    * limit class mutability as much as possible
    * use [record](https://docs.oracle.com/en/java/javase/21/language/records.html)
      to design immutable classes (java 16 feature)
  * favor composition over inheritance (item 18)
  * prefer interfaces to abstract classes (item 20)
  * design interface for posterity (item 21)
    * avoid [default methods](https://docs.oracle.com/javase/tutorial/java/IandI/defaultmethods.html) unless the need is critical
      (because it can break implementations)
  * favor static member classes over nonstatic (item 24)
* _Generics_
  * don't use raw types (item 26)
  * eliminate unchecked warnings (item 27)
    * if you can't, suppress it with 
      [@SuppressWarning("unchecked)](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/SuppressWarnings.html) 
      annotation on the smallest scope possible
  * prefer lists to arrays (item 28)
  * favor designing generic types (item 29) and generic methods (30) 
  * use bounded wildcards (<? extends T>, <? super T>) to increase API flebility (item 31)
    * see [guidelines for wildcard use](https://docs.oracle.com/javase/tutorial/java/generics/wildcardGuidelines.html)
  * combine generics and varargs judiciously (item 32)
    * see [@SafeVarargs](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/SafeVarargs.html)
    * a generic varags method is safe if
      * it doesn't store anything in the varags paramater array
      * it doesn't make the array (or a clone) visible to untrusted code
* _Enums and Annotations_
  * use enums instead of int constants (item 34)
  * don't use 
    [ordinal()](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Enum.html#ordinal())
    as value will change with enum reorder (item 35)
  * prefer annotations to naming patterns (item 39)
  * consistently use the
    [@Override](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/Override.html) 
    annotation (item 40)
  * use marker interfaces to define types (item 41)
* _Lambdas and Streams_
  * prefer lambdas to anonymous classes (item 42)
    * lambda lack names and documentation; if a computation isn't self-explanatory, 
      or exceeds a few lines, don't put it in a lambda
  * favor the use of standard functional interfaces (item 44)
    * e.g. [BinaryOperator](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/function/BinaryOperator.html),
      [Consumer](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/function/Consumer.html),
      [Function](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/function/Function.html),
      [Predicate](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/function/Predicate.html),
      [Supplier](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/function/Supplier.html),
      [UnaryOperator](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/function/UnaryOperator.html),
      ...
    * annotate custom functional interfaces with
      [@FunctionalInterface](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/FunctionalInterface.html)
  * use streams judiciously (item 45)
    * overusing streams makes programs hard to read and maintain
    * good name for lambda parameters ease streams readability
    * helper methods could ease streams readability
  * prefer side-effect-free functions ([pure function](https://en.wikipedia.org/wiki/Pure_function)) in streams (item 46)
    * [forEach](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/stream/Stream.html#forEach(java.util.function.Consumer)) 
      operation should be used only to report the result of a stream computation, 
      not to perform the computation
  * use caution when making streams parallel (item 48)
* _Methods_
  * check parameters for validity (item 49)
    * use [@throws](https://docs.oracle.com/en/java/javase/21/docs/specs/javadoc/doc-comment-spec.html)
      javadoc tag to document the exception  
    * use [Objects.requireNonNull](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Objects.html#requireNonNull(T,java.lang.String))
      to perform null checks
  * make defensive copies when needed (item 50)
    * make defensive copy of each mutable parameter to constructors
    * returns defensive copies of mutable internal fields
  * design method signatures carefully (item 51)
    * choose method names carefully
    * don't go overboard in providing convenience methods
      * when in doubt, leave a method out
    * avoid long parameter lists
    * favor interface to class as parameter type
    * favor enum to boolean parameters
  * use overloading judiciously (item 52)
    * you can always give methods different names instead of overloading them to avoid confusion
  * return empty collections or arrays, not nulls (item 54)
  * return optionals judiciously (item 55)
    * never return null from an Optional
    * collections, maps, streams, arrays and optionals should not be wrapped in optionals
    * return Optional<T> if it might not be able to return a result and clients have
      to perform special processing if no result is returned
  * write javadocs for all exposed API elements (item 56)
    * see [Specification for the Standard Doclet](https://docs.oracle.com/en/java/javase/21/docs/specs/javadoc/doc-comment-spec.html)
    * and [How to Write Doc Comments for the Javadoc Tool](https://www.oracle.com/technical-resources/articles/java/javadoc-tool.html#:~:text=A%20doc%20comment%20is%20written,%40return%20%2C%20and%20%40see%20.)
* _General Programming_
  * minimize the scope of local variables (item 57)
    * declare local variable where it first used
    * nearly every local variable declaration should contain an initializer
    * keep methods small and focused
  * prefer [for each loops](https://docs.oracle.com/javase/8/docs/technotes/guides/language/foreach.html)
    to traditional loops (item 58) 
  * know and use the libraries (item 59)
    * use
      [ThreadLocalRandom](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/concurrent/ThreadLocalRandom.html)
      instead of 
      [Random](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Random.html)
    * every programmer should be familiar with the basics of
      [java.lang](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/package-summary.html), 
      [java.util](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/package-summary.html), 
      [java.io](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/io/package-summary.html),
      [collections framework](https://docs.oracle.com/javase/8/docs/technotes/guides/collections/overview.html), 
      [streams library](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/stream/Stream.html) and 
      high-level parts of 
      [java.util.concurrent](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/concurrent/package-summary.html)
    * use [guava](https://github.com/google/guava) if you can't find standard feature
  * avoid float and double if exact answers are required (item 60)
    * use [BigDecimal](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/math/BigDecimal.html), 
      int or long for monetary calculations
  * prefer primitive types to boxed primitives (item 61)
  * refer to objects by their interfaces (item 64)
  * prefer interfaces to reflection (item 65) 
  * optimize judiciously (item 67)
    * [Jackson's rules](https://softwarequotes.com/quote/jackson-s-rules-of-optimization--rule-1--don-t-do-):
      * Rule 1: don't do it
      * Rule 2: (for experts only). Don't do it yet - that is, not until you have a perfectly clear and unoptimized solution
    * strive to write good programs; speed will follow
    * avoid design decisions that limit performance (APIs, protocols, persistent data)
    * measure performance before and after each optimization
  * adhere to generally accepted naming conventions (item 68)
    * see [Google Java Style guide](https://google.github.io/styleguide/javaguide.html#s5-naming):
      * package: lower dot case (org.junit.jupiter.api)
      * class/interface: upper camel case (Stream)
      * method/field/local variable: lower camel case (remove)
      * constant field: screaming snake case (MIN_VALUE)
      * type parameter: single capital letter (T, E, K, T1, T2, V)
* _Exceptions_
  * use exceptions only for exceptional conditions (item 69)
    * exceptions should never be used for ordinary control flow
  * favor the use of standard exceptions (item 72)
    * [IllegalArgumentException](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/IllegalArgumentException.html),
      [IllegalStateException](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/IllegalStateException.html),
      [NullPointerException](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/NullPointerException.html),
      [UnsupportedOperationException](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/UnsupportedOperationException.html)
  * document all exceptions thrown by each method  
    with [@throws](https://docs.oracle.com/en/java/javase/21/docs/specs/javadoc/doc-comment-spec.html)
    javadoc tag (item 74) 
* _Concurrency_
  * prefer executors, tasks and streams to threads (item 80)
    * use high-level API
      [java.util.concurrent](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/concurrent/package-summary.html)
    * prefer concurrency utilities to wait and notify (item 81) 
      * use [ConcurrentHashMap](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/concurrent/ConcurrentHashMap.html)
        instead of 
        [Collections.synchronizedMap](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/util/Collections.html#synchronizedMap(java.util.Map))
      * use 
        [System.nanoTime](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/System.html#nanoTime()) 
        instead of
        [System.currentTimeMillis](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/lang/System.html#currentTimeMillis())
    * document thread safety (item 82)
      * use [ThreadSafe](https://github.com/amaembo/jsr-305/blob/master/ri/src/main/java/javax/annotation/concurrent/ThreadSafe.java),
        [NotThreadSafe](https://github.com/amaembo/jsr-305/blob/master/ri/src/main/java/javax/annotation/concurrent/NotThreadSafe.java),
        [Immutable](https://github.com/amaembo/jsr-305/blob/master/ri/src/main/java/javax/annotation/concurrent/Immutable.java)
        annotations from [JSR-305 home page](https://code.google.com/archive/p/jsr-305/)
    * use lazy initialization judiciously (item 83)
      * in most cases, normal initialization is preferable to lazy initialization
      * lazy initialization is an optimization, don't do it unless you need to
    * don't depend on the thread scheduler (item 84)
      * thread priorities are among the least portable feature of Java
* _Serialization_
  * prefer alternatives to
    [Java serialization](https://docs.oracle.com/en/java/javase/21/docs/api/java.base/java/io/Serializable.html)
    like [JSON](https://www.json.org/json-en.html) or 
    [protobuf](https://developers.google.com/protocol-buffers) (item 85)
  
[*Go to top*](#Java)

*(Page mainly written in 2022; links checked on 18.02.2024)*
