# Webstack

Webstack based on [Angular](https://angular.io/) & [Spring Boot](https://spring.io/projects/spring-boot)

* *frontend*: 
  [**Angular**](frontend/Angular.md) +
  [CSS](frontend/CSS.md), 
  [HTML](frontend/HTML.md),
  [Javascript](frontend/JavaScript.md) or 
  [Typescript](frontend/TypeScript.md)
  * [WebAPIs](frontend/WebAPIs.md) like
    [progressive web app](frontend/PWA.md)
    and [web components](frontend/WebComponents.md)
  * [RxJS](frontend/RxJS.md) ([reactive programming](https://www.baeldung.com/cs/reactive-programming)),
    [UX design](frontend/UXDesign.md), 
    [frontend testing](frontend/FrontendTesting.md)
* *backend:*
  [**SpringBoot**](backend/SpringBoot.md) +
  [REST API](transversal/REST-API-Guidelines.md),
  [Java](backend/Java.md) (with 
  [JPA](https://jakarta.ee/specifications/persistence/) ORM & 
  [JPQL](https://en.wikipedia.org/wiki/Jakarta_Persistence_Query_Language)), 
  [PostgreSQL](backend/PostgreSQL.md) db
* *continuous integration* with [jenkins](https://www.jenkins.io/)
  * [Git](transversal/Git.md) with [GitHub](transversal/GitHub.md)
  * [maven](https://maven.apache.org/), [gradle](https://gradle.org/) and [npm](https://www.npmjs.com/) as build process and dependencies management; see [gradle vs maven](https://www.geeksforgeeks.org/difference-between-gradle-and-maven/)
  * linters: [ESLint](https://eslint.org/), 
    [stylelint](https://stylelint.io/), 
    [checkstyle](https://checkstyle.sourceforge.io), 
    [PMD](https://pmd.github.io/)
  * testing: 
    [Selenium](https://www.selenium.dev/) (e2e), 
    [Puppeteer](https://pptr.dev/) (e2e), 
    [Cypress](https://www.cypress.io/) (e2e),
    [junit](https://junit.org/junit5/) + [mockito](https://site.mockito.org/) (java),
    [Jasmine](https://jasmine.github.io/) (js), 
    [Jest](https://jestjs.io/) (js)
  * db versioning: [flyway](https://flywaydb.org/), 
    [liquibase](https://www.liquibase.com/); 
    see [liquibase vs flyway](https://www.liquibase.com/liquibase-vs-flyway)
* *others topics*:
  [web accessibility](transversal/WebAccessibility.md),
  [micro-frontends](frontend/MicroFrontends.md) ,
  [security](transversal/Security.md) ,
  [agile manifesto](https://agilemanifesto.org/),
  [kafka](backend/Kafka.md),
  [clean code rules](transversal/clean-code-rules.md),
  _cloud computing_
* *servers*  
  * [tomcat](https://tomcat.apache.org/),
    [jetty](https://www.eclipse.org/jetty/),
    [undertow](https://undertow.io/) as java web containers
  * [http-server](https://github.com/http-party/http-server)
    to serve static web apps (frontends)   
  * [json-server](https://github.com/typicode/json-server) to fake REST API
* *tools*
  * [markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) or
    [AsciiDoc](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/) for documentation
    * see [gray-matter](https://github.com/jonschlinkert/gray-matter) & [front-matter](https://jekyllrb.com/docs/front-matter/) to include yaml in markdown
  * [PlantText](https://www.planttext.com/) or
    [diagrams.net](https://www.diagrams.net) as diagram editors
  * [Visual Studio Code](https://code.visualstudio.com/) 
    IDE with 
    [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode),
    [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer),
    [Angular Essentials](https://marketplace.visualstudio.com/items?itemName=johnpapa.angular-essentials),
    [REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client) plugins
  * [dbeaver](https://dbeaver.io/) as db tool
  * [Lighthouse](https://developers.google.com/web/tools/lighthouse/) to audit website performance, accessibility, etc.
  * [Storybook](https://storybook.js.org/) for building UI components and pages in isolation
  * [Stencil](frontend/Stencil.md) as web components compiler
  * [pg-sql](https://pg-sql.com/) as temporary online Postgres Database
  * https://ondras.zarovi.cz/sql/demo/ or
    [dbdiagram.io](https://dbdiagram.io/home) for sql schema designers


## Alternatives
* frontend frameworks:
  [Svelte](frontend/Svelte.md),
  [Next.js](frontend/NextJS.md) (based on [React](frontend/ReactJS.md)),
  [Remix](frontend/RemixJS.md) (based on [React](frontend/ReactJS.md)),
  ([JSF](frontend/JSF.md) _legacy_)
* application state management: [NgRx](frontend/NgRx.md)
* JPA: 
  [JOOQ](https://www.jooq.org/), 
  [Spring Data R2DBC](https://spring.io/projects/spring-data-r2dbc),
  [Prisma](https://www.prisma.io/) (Typescript)
* backend frameworks:
  [Quarkus](https://quarkus.io/),
  [Micronaut](https://micronaut.io/),
  [Dropwizard](https://www.dropwizard.io/en/latest/),
  [NodeJS](https://nodejs.org/) (JS), 
  [Deno](https://deno.land/) (JS)
  * see [comparing Spring Boot alternatives](https://www.jrebel.com/blog/spring-boot-alternatives)
* JVMs: [graalvm](https://www.graalvm.org/)
* webstacks: [JAMStack](frontend/JAMStack.md) 
* databases: 
  [MongoDB](https://www.mongodb.com/docs/manual/) (nosql), [Elasticsearch](backend/Elasticsearch.md) (nosql),
  [hsql](http://hsqldb.org/) (in-memory), 
  [H2](https://www.h2database.com/html/main.html) (in-memory),
  [Apache Derby](https://db.apache.org/derby/) (in-memory)
* REST API: [GraphQL](backend/GraphQL.md)


## Assets
* [unsplash.com](https://unsplash.com/) for images
* [heroicons](https://heroicons.com/),
  [Feather](https://feathericons.com/),
  [Line Awesome](https://icons8.com/line-awesome),
  [fontawesome](https://fontawesome.com/),
  [Material Design Icons](https://pictogrammers.com/library/mdi/),
  [Noun Project](https://thenounproject.com/),
  [React Icons](https://react-icons.github.io/react-icons) for icons
* [Star Wars API](https://pipedream.com/apps/swapi) to do some quick testing


## Links
* [state of JS 2022](https://2022.stateofjs.com/en-US/)
* [state of CSS 2022](https://2022.stateofcss.com/en-US)
* [state of frontend 2022](https://tsh.io/state-of-frontend/)
* [2022 javaScript rising stars](https://risingstars.js.org/2022/en)
* [web almanac 2022](https://almanac.httparchive.org/en/2022/)


*(last update April 2023; links checked on 13.02.2023)*
