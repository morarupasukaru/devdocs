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
  * [Git](transversal/Git.md) with [Github](https://github.com/)
  * [maven](https://maven.apache.org/), [gradle](https://gradle.org/) and [npm](https://www.npmjs.com/) as build process and dependencies management; see [gradle vs maven](https://www.geeksforgeeks.org/difference-between-gradle-and-maven/)
  * linters: [ESLint](https://eslint.org/), 
    [stylelint](https://stylelint.io/), 
    [checkstyle](https://checkstyle.sourceforge.io), 
    [PMD](https://pmd.github.io/)
  * testing: 
    [Selenium](https://www.selenium.dev/) (e2e), 
    [Puppeteer](https://pptr.dev/) (e2e),
    [Playwright](https://playwright.dev/),
    [Cypress](https://www.cypress.io/) (and [cypress-realworld-app](https://github.com/cypress-io/cypress-realworld-app)) (e2e),
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
  [clean code rules](transversal/clean-code-rules.md)
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

## Resources

* api
  * [GraphQL](backend/GraphQL.md) as alternatives to REST
  * [json-server](https://github.com/typicode/json-server) as fake REST API
* application state management: [NgRx](frontend/NgRx.md)
* databases
  * in-memory relational:
    [hsql](http://hsqldb.org/),
    [H2](https://www.h2database.com/html/main.html),
    [Apache Derby](https://db.apache.org/derby/)
  * nosql:
    [MongoDB](https://www.mongodb.com/docs/manual/),
    [Elasticsearch](backend/Elasticsearch.md)
* frameworks
  * backend:
    [Quarkus](https://quarkus.io/),
    [Micronaut](https://micronaut.io/),
    [Dropwizard](https://www.dropwizard.io/en/latest/),
    [NodeJS](https://nodejs.org/) (JS),
    [Deno](https://deno.land/) (JS)
  * frontend:
    [Svelte](frontend/Svelte.md),
    [Next.js](frontend/NextJS.md),
    [Remix](frontend/RemixJS.md),
    [React](frontend/ReactJS.md)
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
* images: [unsplash.com](https://unsplash.com/), [Noun Project](https://thenounproject.com/)
* orm: [JOOQ](https://www.jooq.org/),
  [Spring Data R2DBC](https://spring.io/projects/spring-data-r2dbc),
  [Prisma](https://www.prisma.io/) (TS) as alternatives to JPA
* vm: [graalvm](https://www.graalvm.org/)

(see also [archived topics](./archive/archive.md))

*(last update January 2024; links checked on 22.01.2024)*
