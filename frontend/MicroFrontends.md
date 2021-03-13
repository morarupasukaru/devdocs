# Micro frontends

*Micro frontends* is a [microservice](https://en.wikipedia.org/wiki/Microservices) approach to front-end web development.

*(Page mainly written in december 2020)*

* Concepts
  * single page applications are typically frontend monolith above backend micro-services
  * micro frontend web applications are composed of independent features/UI parts that can be develop by different 
    teams in different technologies
  * teams develop features/micro frontends end-to-end, from database to user interface
* Goals of micro frontends
  * *independent of technology*: each team could choose a stack without having dependencies to other teams 
  * *isolate team code*: don't share code between team
  * *avoid naming collisions*: define naming conventions (prefix pro team) where isolation is not possible 
    (e.g. css, localStorage, etc.)
  * *use native browser features instead of custom APIs*
  * *be resilient*: feature should be useful even if JavaScript failed or has not executed yet with 
    [server-side rendering](https://developers.google.com/web/updates/2019/02/rendering-on-the-web)
* Implementation approaches
  * the [container application](https://martinfowler.com/articles/micro-frontends.html#IntegrationApproaches)
    is typically responsible of rending common elements (toolbar, navigation), owned authentication and
    bundle micro-frontends/pages together
  * there is a micro frontend pro page
  * integrations of micro frontends 
    * ... with [iframes](https://martinfowler.com/articles/micro-frontends.html#Run-timeIntegrationViaIframes)
    * ... with [web components](https://martinfowler.com/articles/micro-frontends.html#Run-timeIntegrationViaWebComponents)
    * ... at [build-time](https://martinfowler.com/articles/micro-frontends.html#Build-timeIntegration)
    * ([or see other variants](https://martinfowler.com/articles/micro-frontends.html#IntegrationApproaches))
  * [Communication between micro frontends](https://martinfowler.com/articles/micro-frontends.html#Cross-applicationCommunication)
    * with [custom DOM events](https://developer.mozilla.org/en-US/docs/Web/Guide/Events/Creating_and_triggering_events): 
      increase coupling between micro frontends
    * with [Window.postMessage()](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage)
    * it's better to avoid as much as possible communication between micro frontends to prevent coupling between teams
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
  * [scion](https://github.com/SchweizerischeBundesbahnen/scion-microfrontend-platform/blob/master/docs/site/microfrontend-architecture.md): uses iFrames for isolation and provides custom Intent/Capability solution for shell  and inter-module communication
  * [windowed-observable](https://github.com/luistak/windowed-observable): library for pub/sub messaging using Observables
* References
  * see [micro-frontends.org](https://micro-frontends.org/) and [article on martinfowler site](https://martinfowler.com/articles/micro-frontends.html)

[*Go to parent page*](../README.md)
