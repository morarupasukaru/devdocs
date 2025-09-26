# JAMStack

[JAMStack](https://jamstack.org/) is "a modern web development architecture based on client-side 
JavaScript, reusable APIs, and prebuilt Markup (static HTML files)"

* [JAMStack](https://jamstack.org/) stands for **J**avasScript, **A**PIs, **M**arkdown
  * **JavaScript** handle dynamic aspects of web pages (choose of JS lib/framework is free)
  * **APIs** as microservices or [serverless functions](https://en.wikipedia.org/wiki/Serverless_computing) 
    provide dynamic data retrieved by JavaScript
  * **Markup** (M in HTML) means complete websites (+ assets & JavaScript) are served as
    static HTML files
* concepts
  * whole website (HTML, assets and JavaScript) is generated during build process
    with a [static site generator](https://jamstack.org/generators/) 
  * serve web app via [content delivery network (CDN)](https://www.cloudflare.com/learning/cdn/what-is-a-cdn/)
    to provides better performance and easier scalability as web servers
  * make [atomic deploys](https://buddy.works/blog/introducing-atomic-deployments#what-are-atomic-deployments)
    to deploy a full snapshot of the site
  * [invalidate cache of CDN](https://www.netlify.com/blog/2015/09/11/instant-cache-invalidation/) 
    once your build is uploaded
  * project getting started should consist only of git clone + npm install (no db, no complex config) 
  * automate builds with webhooks to build & deploy on CDN automatically
* getting started
  * static site generator: [Scully](https://scully.io/) for *Angular* or see [other SSGs](https://jamstack.org/generators/)
  * deployment: [Github Pages](https://pages.github.com/), etc.
* articles
  * [What is the JAMStack?](https://academind.com/tutorials/what-is-the-jamstack)


## JAMStack in Angular

JAMStack can be implemented in [Angular](../../webstack/Angular.md) with [Scully](https://scully.io/) or [Angular Universal](https://angular.io/guide/universal) (with pre-rendering)

* [Introduction about Scully](https://academind.com/tutorials/scully-introduction/)
* [Angular Universal vs Scully](https://medium.com/joolsoftware/angular-pre-rendering-scully-io-vs-angular-universal-6f026150f341)

[*Go to parent page*](README.md)

*(Page mainly written in december 2020; links checked on 26.02.2024)*
