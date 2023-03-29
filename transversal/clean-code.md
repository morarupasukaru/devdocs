# Clean Code

[Clean code](https://de.wikipedia.org/wiki/Clean_Code)
is concice uncomplex readable and meaningfull code to be easy to understand.

* [naming rules](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29#names-rules)
  * names should be meaningful (and short), best practises:
    * variable: nouns (user), short phrases (isValid)
    * functions: verbs (sendData), short phrases (isValid)
    * classes: nouns (User), short phrases (RequestBody)
  * see [naming in Google Java Style Guide](https://google.github.io/styleguide/javaguide.html#s5-naming)
* [comments](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29#comments-rules) are o good for
  * don't write comments in most cases expect
    * ... explanations/warns that cannot be replacing by good naming
    * ... documentation of public library (e.g. with javadoc)
    * ... (TODOs, legal informations)
* [code formatting](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29#source-code-structure)
  * use IDEs autoformatting (e.g. [Java formatting and linting in Visual Studio Code](https://code.visualstudio.com/docs/java/java-linting))
    with language-specific guidelines 
    (e.g. [google style](https://google.github.io/styleguide/javaguide.html#s4-formatting) for java)
  * write from top to bottom and keep related concepts close to each other (without too many jumps)  

key concepts
* functions (length, parameters)
* conditionals & errors handling
* classes & data structures

TODO
* links
  * [summary of 'Clean code' by Robert C. Martin](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29)
  * [summary of clean code academind course](https://github.com/academind/clean-code-course-code/tree/general-resources)
  * [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)
  * [Java formatting and linting in Visual Studio Code](https://code.visualstudio.com/docs/java/java-linting)

*(Page mainly started in march 2023)*

[*Go to parent page*](../README.md)