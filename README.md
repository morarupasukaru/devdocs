# Webstack

Webstack based on [Angular](frontend/Angular.md) & [Spring Boot](backend/SpringBoot.md)

* api: [REST](transversal/REST-API-Guidelines.md)
* application state management: [RxJS](frontend/RxJS.md)
* build: [maven](https://maven.apache.org/)
* [clean code](#Clean-code)
  * [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) (don't repeat yourself)
  * [KISS](https://en.wikipedia.org/wiki/KISS_principle) (keep it simple stupid)
  * [YAGNI](https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it) (you aren't gonna need it)
* code analyzer/formatter: **TODO**
* databases: [H2](https://www.h2database.com/html/main.html)
* documentation: [markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
* frameworks: [Angular](frontend/Angular.md) & [Spring Boot](backend/SpringBoot.md)
* ide: IntelliJ IDEA
* languages:
  [Java](backend/Java.md),
  [Typescript](frontend/TypeScript.md),
* persistence: [JPA](https://jakarta.ee/specifications/persistence/)
* testing
  * backend: [junit5](https://junit.org/junit5/) + [mockito](https://site.mockito.org/),
    [Spring Boot Testing](https://docs.spring.io/spring-boot/reference/testing/index.html)
  * frontend: **TODO** (see angular docs)
  * e2e: **TODO** (see angular docs)
  * [TDD](https://martinfowler.com/bliki/TestDrivenDevelopment.html) (test-driven development)
* vcs: [Git](transversal/Git.md), [Github](https://github.com/)


(See also [minor topics](./minor-topics.md) and [archived topics](./archive/archive.md))


## Clean code

Summary of [Clean code](https://de.wikipedia.org/wiki/Clean_Code)
from by Robert C. Martin,
about writing uncomplex readable and meaningfull code that is easy to understand.

* naming rules
  * names should be meaningful (and short), best practises:
    * variable: nouns (user), short phrases (isValid)
    * functions: verbs (sendData), short phrases (isValid)
    * classes: nouns (User), short phrases (RequestBody)
      * replace [magic numbers](https://en.wikipedia.org/wiki/Magic_number_(programming))
        with named constant
    * see [naming in Google Java Style Guide](https://google.github.io/styleguide/javaguide.html#s5-naming)
* comments rules
  * don't write comments in most cases expect
    * ... explanations/warns that cannot be replacing by good naming
    * ... documentation of public library (e.g. with javadoc)
    * ... (TODOs, legal informations)
* code formatting rules
  * use IDEs autoformatting (e.g. [Java formatting and linting in Visual Studio Code](https://code.visualstudio.com/docs/java/java-linting))
    with language-specific guidelines
    (e.g. [google style](https://google.github.io/styleguide/javaguide.html#s4-formatting) for java)
  * write from top to bottom and keep related concepts close to each other (without too many jumps)
* functions rules
  * minimize the number of parameters (max 2)
  * small
  * do one thing
  * try to write [pure functions](https://en.wikipedia.org/wiki/Pure_function) (same inputs provide same output)
    * or functions should at least not have unexpected
      [side effects](https://en.wikipedia.org/wiki/Side_effect_(computer_science))
* objects and data structures rules
  * small
  * do one thing / have one responsibily (can have several methods)
  * avoid hybrids structures (half objects and half data structure)
    * objects: hide their data (private) and have functions to operate on that data (API, business logic)
    * data structures: show their data (public) and have no functions (no API)
* other rules
  * keep it simple (see [KISS principle](https://en.wikipedia.org/wiki/KISS_principle))
  * follow standard conventions
  * boy scout rule: leave the campground cleaner than you found it
  * use dependency injection
  * be consistent: if you do something a certain way, do all similar things in the same way
  * [don't repeat yourself (DRY)](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)
    (e.g. a small function that do one thing can be re-used)
  * one assert per test (split a function if it cannot be easily tested)
  * use [guard](https://en.wikipedia.org/wiki/Guard_(computer_science)) to fail fast (and reduce deep nesting)
  * prefer positive to negative check (isEmpty instead of isNotEmpty)
  * prefer polymorphism & factory functions to if/else or switch/case
* links
  * [summary of "Clean code" by Robert C. Martin](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29)
  * [clean code academind course](https://www.udemy.com/course/writing-clean-code/)
  * [Conventional Commits 1.0.0](https://www.conventionalcommits.org/en/v1.0.0/) provides an easy set of rules for creating an explicit commit history


[*Go to top*](#Webstack)

*(last update december 2024; links checked on 22.01.2024)*