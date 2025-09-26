# Micro-frontends

*Micro-frontends* is a [microservice](https://en.wikipedia.org/wiki/Microservices) approach to front-end web development.

* Concepts
  * single page applications are typically frontend monolith above backend microservices
  * micro frontend web applications are composed of independent features/UI parts that can be developed by different 
    teams in different technologies
  * teams develop features/micro-frontends end-to-end, from database to user interface
* Goals of micro-frontends
  * *independent of technology*: each team could choose a stack without having dependencies to other teams 
  * *isolate team code*: don't share code between team
  * *avoid naming collisions*: define naming conventions (prefix pro team) where isolation is not possible 
    (e.g. css, localStorage, etc.)
  * *use native browser features instead of custom APIs*
  * *be resilient*: feature should be useful even if JavaScript failed or has not executed yet with 
    [server-side rendering](https://web.dev/articles/rendering-on-the-web#server-side_rendering)
* Implementation approaches
  * the [container application](https://martinfowler.com/articles/micro-frontends.html#IntegrationApproaches)
    is typically responsible for rendering common elements (toolbar, navigation), owned authentication and
    bundle micro-frontends/pages together
  * there is a micro frontend pro page
  * integrations alternatives of micro-frontend
    * [server-side](https://martinfowler.com/articles/micro-frontends.html#Server-sideTemplateComposition)
      integration could be too much complex
    * [build-time](https://martinfowler.com/articles/micro-frontends.html#Build-timeIntegration)
      integration require to release all micro-frontends order to ship a change in one micro-frontend
      * build-time approach with e.g. [Angular feature module](https://angular.io/guide/feature-modules) (lazy or not) 
        could be an alternative for web application that require less isolation between teams 
        (would be not obviously a micro-frontends architecture)
    * [JavaScript](https://martinfowler.com/articles/micro-frontends.html#Run-timeIntegrationViaJavascript)'s 
      integration provide no isolation of window global scope populated from different micro-frontends. 
      Clatches could occur if e.g. different versions of same library/framework is used
    * [web components](https://martinfowler.com/articles/micro-frontends.html#Run-timeIntegrationViaWebComponents)
      integration is cleaner as with JavaScript but also do not isolate window global scope 
    * [iframes](https://martinfowler.com/articles/micro-frontends.html#Run-timeIntegrationViaIframes)
      integration isolate window global scope but performance issue could occur and interaction 
      between micro-frontends could be complex
  * [Communication between micro-frontends](https://martinfowler.com/articles/micro-frontends.html#Cross-applicationCommunication)
    * with [custom DOM events](https://developer.mozilla.org/en-US/docs/Web/Guide/Events/Creating_and_triggering_events): 
      increase coupling between micro-frontends and is not available for iframe approach
    * with [Window.postMessage()](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage) 
      is complex but is available for iframe approach
    * it's better to avoid as much as possible communication between micro-frontends to prevent coupling between teams
  * each micro frontend should have its own backend (known as 
    [BFF pattern (backend for frontend)](https://samnewman.io/patterns/architectural/bff/))
  * [testing](https://martinfowler.com/articles/micro-frontends.html#Testing)
    * *unit tests*: test internal business logic of each micro frontend
    * *integration test*: 
      * test that the page is assembled correctly (e.g. check page title)
      * avoid to test business logic to prevend complex integration tests
    * [consumer-driven contracts pattern](https://martinfowler.com/articles/consumerDrivenContracts.html) 
      could avoid complex integration tests
* Frameworks / Tools
  * [single-spa](https://single-spa.js.org/): 
    javascript router for micro front-ends that can be written in different framework
  * [scion](https://github.com/SchweizerischeBundesbahnen/scion-microfrontend-platform/blob/master/docs/site/microfrontend-architecture.md): 
    ease iframes integration approach with a solution for container application and communication between micro-frontends
  * [windowed-observable](https://github.com/luistak/windowed-observable): library for pub/sub messaging using Observables
* References
  * see [micro-frontends.org](https://micro-frontends.org/) and [article on martinfowler site](https://martinfowler.com/articles/micro-frontends.html)

[*Go to parent page*](README.md)

*(Page mainly written in december 2020; links checked on 23.02.2024)*
