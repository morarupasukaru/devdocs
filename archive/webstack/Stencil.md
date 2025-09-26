# Stencil

[Stencil](https://stenciljs.com/docs/introduction) is a compiler that generates Web Components
in plain JavaScript.

* Stencil is a tool (not a framework or library) to compile native JavaScript Web Components with 
  following additional features:
  * loading component code lazily
  * loading required polyfills automatically for browsers that need it
  * re-rendering the web (component) DOM efficiently
  * no extra library is required to be deployed, Stencil build native JavaScript Web Components
* Stencil generate vanilly JS and can be integrated in any frameworks (or without framework)
* Stencil is based on best concepts of popular frontend frameworks
* Concepts
  * [TypeScript](https://www.typescriptlang.org/): 
    TypeScript extends JavaScript by adding types
  * [JSX](https://stenciljs.com/docs/templating-jsx#using-jsx) 
    "HTML in JavaScript" (syntax extension to JavaScript)
  * Virtual DOM: (VDOM) is a programming concept where an ideal, or "virtual", representation of a 
    UI is kept in memory and synced with the "real" DOM (concept from React)
  * [Async rendering](https://stenciljs.com/docs/component-lifecycle#async-lifecycle-methods): 
    Stencil lifecycle methods allow retrieving data asynchronously or perform any async tasks
  * [Reactive data-binding](https://stenciljs.com/docs/reactive-data): Stencil components update 
    when props or state on a component change
  * [Static Site Generation](https://stenciljs.com/docs/static-site-generation) (SSG): means 
    building and rendering components and routes at build time (aka prerendering) rather than server 
    request time (SSR) or at client run-time (SPA)
* Basic decorators
  * [@Prop()](https://stenciljs.com/docs/properties) decorator are custom attribute/properties 
    exposed publicly on the element
  * [@State()](https://stenciljs.com/docs/state) decorator is used to manage internal state 
    properties
  * [@Method()](https://stenciljs.com/docs/methods) decorator is used to expose methods on the 
    public API
* Tutorials: [Getting Started](https://stenciljs.com/docs/getting-started), 
  [my first component](https://stenciljs.com/docs/getting-started#my-first-component)
* Advanced concepts
  * [@Element()](https://stenciljs.com/docs/host-element#element-decorator) decorator allow to access the host 
    element (to access standard DOM methods/events)
  * [reference to a DOM element](https://stenciljs.com/docs/templating-jsx#getting-a-reference-to-a-dom-element) 
    can be set instead of using `document.querySelector`
  * state can be bind in JSX template to receive value of attribute
  * [component lifecycle methods](https://stenciljs.com/docs/component-lifecycle)
    * [componentWillLoad()](https://stenciljs.com/docs/component-lifecycle#componentwillload): 
      called once just after the component is first connected to the DOM
      * since this method is only called once, it's a good place to load data asynchronously
      * see [async lifecycle methods](https://stenciljs.com/docs/component-lifecycle#async-lifecycle-methods)
    * [componentWillRender()](https://stenciljs.com/docs/component-lifecycle#componentwillrender): 
      called before every render(). It's always recommended to make any rendered state updates 
      within componentWillRender(), since this is the method which get called before the render() 
      method.
  * [@Watch()](https://stenciljs.com/docs/reactive-data#the-watch-decorator-watch) decorator is used to watch 
    changes on a property
  * [loops / list of elements in JSX](https://stenciljs.com/docs/templating-jsx#dealing-with-children)
  * [custom events](https://stenciljs.com/docs/events) is implemented with `@Event()` and 
    `@Listen()` decorators
  * [<Host>](https://stenciljs.com/docs/host-element#host) JSX functional component can be used at 
    the root of the render function to set attributes and event listeners to the host element itself
  * [Embedding components into components](https://stenciljs.com/docs/component#embedding-or-nesting-components): 
    components can be composed easily by adding the HTML tag to the JSX code
  * [CSS Variables](https://stenciljs.com/docs/styling#css-custom-properties) are also available 
    in Stencil
* Deployment & Publishing
  * target build is defined in [outputTargets](https://stenciljs.com/docs/output-targets) of 
    [stencil.config.ts](https://stenciljs.com/docs/config) 
    * target [dist](https://stenciljs.com/docs/distribution) type is to generate the component(s) 
      as a reusable library that can be self-lazy loading
  * `npm run build` to build the project in dist folder
  * [Publishing A Component Library to npm](https://stenciljs.com/docs/publishing)
  * Integration of Stencil web components into
    * ... [Angular](https://stenciljs.com/docs/angular) applications
    * ... [vanilla JavaScript](https://stenciljs.com/docs/javascript) applications
    * ... [and others](https://stenciljs.com/docs/overview)
* Other references
  * SPA written only with Stencil require following two additional features/libs:
    * routing with [stencil-router](https://github.com/ionic-team/stencil-router)
    * see [Using RxJS Observables with StencilJS and Ionic](https://www.joshmorony.com/using-observables-with-stencil-js-and-ionic/) 
  * [Stencil App Starter](https://github.com/stencil-community/stencil-app-starter)
  * [Stencil Component Starter](https://github.com/ionic-team/stencil-component-starter)
  * [tslint-stencil](https://www.npmjs.com/package/tslint-stencil)
  * course: [Web Components & Stencil.js - Build Custom HTML Elements](https://www.udemy.com/course/web-components-stenciljs-build-custom-html-elements/)
* Alternatives to Stencil
  * [svelte.js](https://svelte.dev/)
  * [lit](https://github.com/lit/lit) with use of 
    [lit-html](https://lit.dev/docs/v1/lit-html/introduction/) for templating
  * [skatejs](https://github.com/skatejs/skatejs)

[*Go to parent page*](README.md)

*(Page mainly written in december 2020; links checked on 26.02.2024)*
