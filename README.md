# Webstack

Webstack based on [Angular](https://angular.io/) & [Spring Boot](https://spring.io/projects/spring-boot)
* [Angular](frontend/Angular.md) 
  is a TypeScript **frontend** framework to build
  [Single-page applications](https://en.wikipedia.org/wiki/Single-page_application) (SPA)
* [SpringBoot](backend/SpringBoot.md) 
  **backend** framework ease writing of web applications in Java
* *frontend*
  * [CSS](frontend/CSS.md), 
    [HTML](frontend/HTML.md),
    [Javascript](frontend/JavaScript.md) or [Typescript](frontend/TypeScript.md)
    languages
  * [WebAPIs](frontend/WebAPIs.md) like
    [progressive web app](frontend/PWA.md)
    and [web components](frontend/WebComponents.md)
  * [RxJS](frontend/RxJS.md) ([reactive programming](https://www.baeldung.com/cs/reactive-programming))
  * [UX design](frontend/UXDesign.md)
  * [frontend testing](frontend/FrontendTesting.md)
* *backend*
  * [REST API](transversal/REST-API-Guidelines.md)
  * [Java](backend/Java.md) language
  * [PostgreSQL](backend/PostgreSQL.md) database
  * [JPA](https://jakarta.ee/specifications/persistence/) ORM & [JPQL](https://en.wikipedia.org/wiki/Jakarta_Persistence_Query_Language) 
* *continuous integration*
  * [git](https://git-scm.com/) as version control system
    * using [Gitflow Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) branching model
  * [jenkins](https://www.jenkins.io/) for continuous integration
  * [maven](https://maven.apache.org/), [gradle](https://gradle.org/) and [npm](https://www.npmjs.com/) as build process and dependencies management; see [gradle vs maven](https://www.geeksforgeeks.org/difference-between-gradle-and-maven/)
  * [clean code rules](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29) 
    enforced with linters like
    [ESLint](https://eslint.org/), 
    [stylelint](https://stylelint.io/), 
    [checkstyle](https://checkstyle.sourceforge.io), 
    [PMD](https://pmd.github.io/)
* *others topics*
  * [web accessibility](transversal/WebAccessibility.md)
  * [micro-frontends](frontend/MicroFrontends.md) 
  * [security](transversal/Security.md) 
  * [agile manifesto](https://agilemanifesto.org/)
  * cloud computing (_TODO_)
  * [kafka](backend/Kafka.md) 
* *tools*
  * [markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) or
    [AsciiDoc](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/) for documentation
    * see [gray-matter](https://github.com/jonschlinkert/gray-matter) & [front-matter](https://jekyllrb.com/docs/front-matter/) to include yaml in markdown
  * [PlantText](https://www.planttext.com/) or
    [diagrams.net](https://www.diagrams.net) as diagram editors
  * [http-server](https://github.com/http-party/http-server)
    to serve frontends   
  * [json-server](https://github.com/typicode/json-server) to fake REST API
  * [Star Wars API](https://pipedream.com/apps/swapi) to do some quick testing
  * [Visual Studio Code](https://code.visualstudio.com/) 
    IDE and plugins 
    [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode),
    [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer),
    [Angular Essentials](https://marketplace.visualstudio.com/items?itemName=johnpapa.angular-essentials),
    [REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)
  * [dbeaver](https://dbeaver.io/) as db tool
  * [Lighthouse](https://developers.google.com/web/tools/lighthouse/) to audit website about performance, accessibility, etc.
  * [unsplash.com](https://unsplash.com/) for images
  * [heroicons](https://heroicons.com/),
    [Feather](https://feathericons.com/),
    [Line Awesome](https://icons8.com/line-awesome),
    [fontawesome](https://fontawesome.com/),
    [Material Design Icons](https://pictogrammers.com/library/mdi/),[Noun Project](https://thenounproject.com/) for icons
  * [Storybook](https://storybook.js.org/) for building UI components and pages in isolation

<details>
  <summary>Click to see alternatives</summary>
  
## Alternatives
* alternative to _Angular_ frontend frameworks
  * [Svelte](frontend/Svelte.md) is a compiler that generate SPA web applications
  * [Next.js](frontend/NextJS.md) as [React](frontend/ReactJS.md)
  framework for production
  * [Remix](frontend/RemixJS.md) as another (better) [React](frontend/ReactJS.md) full stack web framework
  * [JSF](frontend/JSF.md) (legacy) is/was the [Java EE](https://en.wikipedia.org/wiki/Jakarta_EE) standard framework to build web applications in Java
* webcomponent
  * [Stencil](frontend/Stencil.md) is a compiler that generates Web Components in plain JavaScript
* rxjs
  * [NgRx](frontend/NgRx.md) to manage application state
* JPA
  * JOOQ, [Spring Data R2DBC](https://spring.io/projects/spring-data-r2dbc)

* alternative to _SpringBoot_ backend frameworks
  * [Quarkus](https://quarkus.io/),
    [Micronaut](https://micronaut.io/),
    [Dropwizard](https://www.dropwizard.io/en/latest/),
    [NodeJS](https://nodejs.org/) (JS), 
    [Deno](https://deno.land/) (JS)
  * see [Spring vs. the World: Comparing Spring Boot Alternatives](https://www.jrebel.com/blog/spring-boot-alternatives)

  https://www.graalvm.org/
* alternative webstack
  * [JAMStack](frontend/JAMStack.md) 
  is webstack based on client-side JavaScript, reusable APIs and static HTML (pre-rendered)

* alternative to _PostgreSQL_ databases
  * [MongoDB](https://www.mongodb.com/docs/manual/) (document / NoSQL database)
  * [Elasticsearch](backend/Elasticsearch.md) (NoSQL database) is a RESTful search engine
* REST
  * [GraphQL](backend/GraphQL.md) is a query language for APIs as alternative to SOAP and REST APIs

</details>

## Links
* [state of JS 2022](https://2022.stateofjs.com/en-US/)
* [state of CSS 2022](https://2022.stateofcss.com/en-US)
* [state of frontend 2022](https://tsh.io/state-of-frontend/)
* [2022 javaScript rising stars](https://risingstars.js.org/2022/en)
* [web almanac 2022](https://almanac.httparchive.org/en/2022/)


*(last update march 2023; links checked on 13.02.2023)*
