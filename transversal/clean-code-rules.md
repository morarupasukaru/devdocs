# Clean Code

----
TODO
* solve error found by IDEA (e.g. typo)
* read page & correct if needed
* check links
* update date of verification
----

[Clean code](https://de.wikipedia.org/wiki/Clean_Code)
is about writing uncomplex readable and meaningfull code 
that is easy to understand.

* Clean Code Rules
  * [naming](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29#names-rules)
    * names should be meaningful (and short), best practises:
      * variable: nouns (user), short phrases (isValid)
      * functions: verbs (sendData), short phrases (isValid)
      * classes: nouns (User), short phrases (RequestBody)
        * replace [magic numbers](https://en.wikipedia.org/wiki/Magic_number_(programming))
          with named constant
    * see [naming in Google Java Style Guide](https://google.github.io/styleguide/javaguide.html#s5-naming)
  * [comments](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29#comments-rules) are good for
    * don't write comments in most cases expect
      * ... explanations/warns that cannot be replacing by good naming
      * ... documentation of public library (e.g. with javadoc)
      * ... (TODOs, legal informations)
  * [code formatting](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29#source-code-structure)
    * use IDEs autoformatting (e.g. [Java formatting and linting in Visual Studio Code](https://code.visualstudio.com/docs/java/java-linting))
      with language-specific guidelines 
      (e.g. [google style](https://google.github.io/styleguide/javaguide.html#s4-formatting) for java)
    * write from top to bottom and keep related concepts close to each other (without too many jumps)  
  * [functions](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29#functions-rules)
    * minimize the number of parameters (max 2)
    * small
    * do one thing
    * try to write [pure functions](https://en.wikipedia.org/wiki/Pure_function) (same inputs provide same output)
      * or functions should at least not have unexpected
        [side effects](https://en.wikipedia.org/wiki/Side_effect_(computer_science))
  * [objects and data structures](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29#objects-and-data-structures)
    * small
    * do one thing / have one responsibily (can have several methods)
    * avoid hybrids structures (half objects and half data structure)
      * objects: hide their data (private) and have functions to operate on that data (API, business logic)
      * data structures: show their data (public) and have no functions (no API)
  * other rules ([general](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29#general-rules),
    [design](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29#design-rules),
    [understandability](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29#understandability-tips),
    [test](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29#tests))
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
  * [summary of 'Clean code' by Robert C. Martin](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29)
  * [clean code academind course](https://www.udemy.com/course/writing-clean-code/)
    and [summary](https://github.com/academind/clean-code-course-code/tree/general-resources)
  * [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)
  * [Java formatting and linting in Visual Studio Code](https://code.visualstudio.com/docs/java/java-linting)

*(Page written in March 2023)*

[*Go to parent page*](../README.md)