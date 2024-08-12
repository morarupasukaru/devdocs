# Webstack

Webstack based on [Angular](frontend/Angular.md) & [Spring Boot](backend/SpringBoot.md)
* languages: 
  [Java](backend/Java.md), 
  [Typescript](frontend/TypeScript.md),
  [Javascript](frontend/JavaScript.md),
  [CSS](frontend/CSS.md),
  [HTML](frontend/HTML.md)
* libs:
  [WebAPIs](frontend/WebAPIs.md),
  [JPA](https://jakarta.ee/specifications/persistence/),
  [JPQL](https://en.wikipedia.org/wiki/Jakarta_Persistence_Query_Language),
  [RxJS](frontend/RxJS.md)

# Other topics
* api: [REST](transversal/REST-API-Guidelines.md), [GraphQL](backend/GraphQL.md)
  * [json-server](https://github.com/typicode/json-server) as fake REST API
* application state management: [RxJS](frontend/RxJS.md) or [NgRx](frontend/NgRx.md)
* audit website: [Lighthouse](https://developers.google.com/web/tools/lighthouse/)
* build: [maven](https://maven.apache.org/), [gradle](https://gradle.org/), [npm](https://www.npmjs.com/)
  (see [comparison](https://www.geeksforgeeks.org/difference-between-gradle-and-maven/))
* ci: [jenkins](https://www.jenkins.io/)
* [clean code](#Clean-code)
* code analyzer/formatter: [ESLint](https://eslint.org/),
  [prettier](https://prettier.io/)
  [stylelint](https://stylelint.io/),
  [checkstyle](https://checkstyle.sourceforge.io),
  [PMD](https://pmd.github.io/)
* databases: [PostgreSQL](backend/PostgreSQL.md)
  * in-memory relational:
    [hsql](http://hsqldb.org/),
    [H2](https://www.h2database.com/html/main.html),
    [Apache Derby](https://db.apache.org/derby/)
  * nosql:
    [MongoDB](https://www.mongodb.com/docs/manual/),
    [Elasticsearch](backend/Elasticsearch.md)
* db tool: [dbeaver](https://dbeaver.io/)
* db versioning: [flyway](https://flywaydb.org/), 
  [liquibase](https://www.liquibase.com/) 
  (see [comparison](https://www.liquibase.com/liquibase-vs-flyway))
* diagram editors: [PlantText](https://www.planttext.com/)
* distributed event streaming: [kafka](backend/Kafka.md)
* documentation: [markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet), 
  [AsciiDoc](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/)
* frameworks
  * backend:
    [Quarkus](https://quarkus.io/),
    [Micronaut](https://micronaut.io/),
    [Dropwizard](https://www.dropwizard.io/en/latest/),
    [NodeJS](https://nodejs.org/) (JS),
    [Deno](https://deno.land/) (JS)
  * frontend:
    [Stencil](frontend/Stencil.md),
    [Svelte](frontend/Svelte.md),
    [Next.js](frontend/NextJS.md),
    [Remix](frontend/RemixJS.md),
    [React](frontend/ReactJS.md),
    [Storybook](https://storybook.js.org/),
    [Solid](https://www.solidjs.com/)
  * webstacks: [JAMStack](frontend/JAMStack.md)
* http servers
  * java:
    [tomcat](https://tomcat.apache.org/),
    [jetty](https://www.eclipse.org/jetty/),
    [undertow](https://undertow.io/)
  * other:
    [http-server](https://github.com/http-party/http-server),
    [nginx](https://nginx.org/en/)
* icons: [heroicons](https://heroicons.com/), [Feather](https://feathericons.com/),
  [Material Design Icons](https://pictogrammers.com/library/mdi/),
  [React Icons](https://react-icons.github.io/react-icons)
* ide: [Visual Studio Code](https://code.visualstudio.com/) + pluggins
  [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode),
  [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer),
  [Angular Essentials](https://marketplace.visualstudio.com/items?itemName=johnpapa.angular-essentials),
  [REST client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client),
  * see [guide for building java](https://spring.io/guides/gs/guides-with-vscode)
* images: [unsplash.com](https://unsplash.com/), [Noun Project](https://thenounproject.com/)
* [micro-frontends](frontend/MicroFrontends.md)
* orm: [JOOQ](https://www.jooq.org/),
  [Spring Data R2DBC](https://spring.io/projects/spring-data-r2dbc),
  [Prisma](https://www.prisma.io/) (TS) as alternatives to JPA 
* [progressive web app](frontend/PWA.md)
* [reactive programming](https://www.baeldung.com/cs/reactive-programming): [RxJS](frontend/RxJS.md)
* [security](transversal/Security.md)
* testing
  * java: [junit](https://junit.org/junit5/) + [mockito](https://site.mockito.org/)
  * javascript 
    * [Jest](https://jestjs.io/);
      see [article](https://academind.com/tutorials/javascript-testing-introduction)
    * [Jasmine](https://jasmine.github.io/); 
      see [cheatsheet](https://devhints.io/jasmine)
  * e2e: [Playwright](https://playwright.dev/), ([Selenium](https://www.selenium.dev/), [Cypress](https://www.cypress.io/))
  * principles: [Test-driven development (TDD)](https://martinfowler.com/bliki/TestDrivenDevelopment.html)
* UX design:
  * [Checklist Design](https://www.checklist.design/) for best practices about UX design
  * [The Data Visualisation Catalogue](https://datavizcatalogue.com/)
    to choose a diagram / graph for a given purpose
* vcs: [Git](transversal/Git.md), [Github](https://github.com/)
* vm: [graalvm](https://www.graalvm.org/)
* [web accessibility](transversal/WebAccessibility.md)
* [web components](frontend/WebComponents.md)

(see also [archived topics](./archive/archive.md))

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


*(last update January 2024; links checked on 22.01.2024)*
