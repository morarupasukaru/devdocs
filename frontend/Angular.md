# Angular

TODO restructuring page in progress
TODO decide if spliting into several sections afterward (to get a quicker overview)

[Angular](https://angular.io/) is a [TypeScript](TypeScript.md) framework to build 
[Single-page applications](https://en.wikipedia.org/wiki/Single-page_application) (SPA).

* [Angular concepts](https://angular.io/guide/architecture)
  * [Angular CLI](https://cli.angular.io/) is a command-line tool to create project, components, deploy application 
     locally, etc.
    * [installation](https://angular.io/cli#installing-angular-cli) of Angular CLI
    * [how-to create project and deploy app locally](https://angular.io/cli#basic-workflow)
  * [@NgModule](https://angular.io/guide/architecture#modules) bundle a set of components together
    * [introduction to modules](https://angular.io/guide/architecture-modules#introduction-to-modules)
    * [JavaScript modules vs NgModules](https://angular.io/guide/ngmodule-vs-jsmodule)
    * [@NgModule](https://angular.io/guide/ngmodules) is a decorator used to identify a class as a NgModule; 
      a container of components
    * root module is normally `app.module.ts`; the `AppModule`
    * most important [properties of @NgModule](https://angular.io/guide/architecture-modules#ngmodule-metadata):
      * [declarations](https://angular.io/api/core/NgModule#declarations): 
        components that belong to this module
      * [imports](https://angular.io/api/core/NgModule#imports): 
        other modules needed by this NgModule (cascade)
      * [bootstrap](https://angular.io/api/core/NgModule#bootstrap): 
        configure root component (only for root module); see [bootstrapping](https://angular.io/guide/bootstrapping)
      * [providers](https://angular.io/api/core/NgModule#providers): 
        specify services available to this module (and submodules)
      * [entryComponents](https://angular.io/api/core/NgModule#entrycomponents): 
        specify components that can be dynamically loaded
      * [exports](https://angular.io/api/core/NgModule#exports): 
        components, directives, pipes and modules declared in this NgModule that can be used in any component part 
        of an NgModule that imports this NgModule
    * [feature modules](https://angular.io/guide/feature-modules) are submodules of AppModule that group components, 
       directives, etc. of a certain business feature of the application
      * splitting application in feature modules ease optimizations (like lazy-loaded modules; see optimizations above)
      * use [CommonModule](https://angular.io/api/common/CommonModule) 
        instead of [BrowserModule](https://angular.io/api/platform-browser/BrowserModule) 
        to get access to ngIF or ngFor in feature module 
        ([BrowserModule](https://angular.io/api/platform-browser/BrowserModule) has to be declared once per application)
      * use [RouterModule.forChild(...)](https://angular.io/api/router/RouterModule#forchild) 
        instead of [.forRoot(...)](https://angular.io/api/router/RouterModule#forroot) to specify feature module routes
      * using [RouterModule.forChild(...)](https://angular.io/api/router/RouterModule#forchild) 
        permit to avoid to have to export inner components of feature module
    * [shared modules](https://angular.io/guide/sharing-ngmodules) 
      allow to package components, directives, etc. shared by feature modules 
      (shared modules export the modules, components, directives in common)
    * [lazy loading feature modules](https://angular.io/guide/lazy-loading-ngmodules) 
      are *lazy loaded* when visiting their associated route
      * lazy loading technical require that feature module provide their own route
      * a route with [Routes.loadChildren](https://angular.io/api/router/Route#lazy-loading) allow to specify the module to be loaded on demand
      * angular CLI analyse the routes and will split bundle if `loadChildren` is used
      * `import` in module impact the size of bundle; it is therefore important to clean-up unused `import`
      * empty path is required for the root route in the feature module
      * lazy loaded feature module must not be declared in app module
      * preload lazy loaded modules by calling [RouterModule.forRoot(..., )](https://angular.io/api/router/RouterModule#forroot) with a second argument `{ preloadingStrategy: PreloadAllModules }`
      * if a service appear in `providers` of several lazy-loading feature modules, they are different instance of the service
      * common source of bug: if a service is provided into a shared module imported in various lazy-loading feature modules, different service instances will be created
      * a guard that implements [CanLoad](https://angular.io/api/router/CanLoad) interface could be used to prevent to load lazy-loading modules (e.g. if unauthorized)
  * [@Component](https://angular.io/guide/architecture#components)
    is a decorator used to identify a class as a component
    * most important [properties of @Component](https://angular.io/api/core/Component):
      * [selector](https://angular.io/api/core/Directive#selector): 
        CSS selector (tag, class or attribute name) that tells Angular to create and insert an instance of this 
        component wherever it finds the corresponding tag in template HTML
      * [templateUrl](https://angular.io/api/core/Component#templateurl): 
        module-relative address of this component's HTML template
      * [styleUrls](https://angular.io/api/core/Component#styleurls): 
        one or more relative paths or absolute URLs for files containing CSS stylesheets to use in this component
      * [providers](https://angular.io/api/core/Directive#providers): 
        specify services available to this component (if not defined in a @NgModule or with `providedIn: 'root'` 
        on service self)
      * creating component with Angular CLI: `ng g c name-of-component`
  * Templates TODO
  * Directives
      * [Directives](#Directives)
  * Data binding
        * [Databinding](#Databinding)
          * [Custom property & event bindings](#Custom-property-and-event-bindings)
          * [Template reference variables](#Template-reference-variables)
          * [@ViewChild](#ViewChild)
          * [ng-content](#ng-content)
          * [ng-container](#ng-container)
          * [Lifecycle hooks](#Lifecycle-hooks)
  * Services and dependency injection
    * [Services and Dependency Injection](#Services-and-Dependency-Injection)
  * Routing
    * [Routing](#Routing)
      * [Routing configuration](#Routing-configuration)
      * [Navigation](#Navigation)
      * [Retrieve route datas](#Retrieve-route-datas)
      * [Child routes](#Child-routes)
      * [Guards](#Guards)
      * [Provide static data to route](#Provide-static-data-to-route)
      * [Resolve](#Resolve)
      * [Location strategies](#Location-strategies)
      * [Miscelleanous](#Miscelleanous)
* Other features
  * [Forms](#Forms)
    * [Template-driven forms](#Template-driven-forms)
    * [Reactive forms](#Reactive-forms)
  * [Styling](#Styling)
  * [Animations](#Animations)
  * [Observables - RxJS](#Observables---RxJS)
  * [Pipes](#Pipes)
  * [Http](#Http)
  * [Authentication](#Authentication)
  * [Dynamic Components](#Dynamic-Components)
  * [Optimizations](#Optimizations)
  * [Deployment](#Deployment)
  * [Testing](#Testing)
  * [Debugging](#Debugging)
  * [Angular Elements](https://angular.io/guide/elements) turn Angular Components as [Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components)
  * [Service Workers & PWA](https://angular.io/guide/service-worker-intro) provide a way to have offline web applications 
    and are used to make a [Progressive Web App (PWA)](https://developers.google.com/web/progressive-web-apps/)
    * Offline can be simulated in chrome in devtools > Application > Service Workers > select "Offline"
    * JavaScript application run in a single Thread
    * [Web workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers) are executed in another Thread (in background; perform tasks without interfering with the user interface)
    * [Service Workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API) are a special types of Web workers
    * Service workers essentially act as proxy servers that sit between web applications, the browser, and the network (when available).
    * Service workers are decoupled from webpage
    * Configure Service Workers in an Angular project: `ng add @angular/pwa`
    * Angular/PWA generate a service worker based on the `ngsw-config.json`
    * we can specify in `ngsw-config.json`
       * which files or urls should be prefetch by the generated service worker
       * caches to be used for rest APIs
  * [Angular Universal](https://angular.io/guide/universal) provide
    [Server-side Rendering](https://developers.google.com/web/updates/2019/02/rendering-on-the-web)
    (pre-render web-pages on the server on the fly) with [ExpressJS](https://expressjs.com/) 
    (a web framework for [Node.js](https://nodejs.org/en/))
    * hint: JavaScript of Angular application will be executed on the server to pre-render HTML pages but 
      does not have access to several APIs like [localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
      * use [PLATFORM_ID](https://angular.io/api/core/PLATFORM_ID) and [isPlatformBrowser()](https://angular.io/api/common/isPlatformBrowser) to check if code is running in the browser or not:
        ```
        import { ..., Inject, PLATFORM_ID } from '@angular/core';
        import { isPlatformBrowser } from '@angular/common';

        export class AppComponent implements OnInit {
          constructor(@Inject(PLATFORM_ID) private platformId) {}

          ngOnInit() {
            if (isPlatformBrowser(this.platformId)) {
              ... call e.g. localStorage
            }
            ...
          }
        ```
* [References](#References)
  * [changelog](https://github.com/angular/angular/blob/master/CHANGELOG.md) to learn latest improvements and breaking changes
  * [TypeScript](TypeScript.md)
  * [Angular Docs](https://angular.io/docs)
  * [Angular CLI](https://angular.io/cli)
  * [Cheatsheet](https://angular.io/guide/cheatsheet)
  * [Angular Update Guide](https://update.angular.io/)
  * courses: [the complete guide to angular](https://www.udemy.com/the-complete-guide-to-angular-2/), 
    [angular material, angularfire & NgRx](https://www.udemy.com/angular-full-app-with-angular-material-angularfire-ngrx/),
    [angular styling & animations](https://www.udemy.com/angular-styling-animations-for-angular-2-and-angular-4/)
* Ecosystem
  * [ngx-translate](http://www.ngx-translate.com/) as internationalization library
  * [RxJS](RxJS.md) for reactive programming using observables that makes it easier to compose asynchronous 
    or callback-based code
  * [NgRx](https://ngrx.io/) and [Redux](https://redux.js.org/) used to manage application state
    * application state is the data used by the application at runtime; the *session data* (state is lost by application refresh)
    * to not loose all important data, some of them are stored in the *persistent state* on backend (db)
    * application state is scattered in several components, services
    * for big projects, application state can be difficult to manage 
    * [RxJS](./RxJS.md) ease management of the application state with Subject and Observable
    * Angular does not force to have a clear structure about application state
    * [Redux](https://redux.js.org/) is a state management pattern (available in ReactJS) and a library
    * Redux library could be used in Angular
    * [NgRx](https://ngrx.io/) is an Angular implementation of [Redux](https://redux.js.org/) and is therfore easier to use as Redux directly
    * Redux vs NgRx
      * NgRx provide injectable services
      * NgRx integrate/use RxJS to have Observable
      * NgRx is written in TypeScript
      * NgRx provide a concept *Side Effect* to support asynchronous code (e.g. http requests)
    * docs:
      * [NgRx docs](https://ngrx.io/docs)
      * [example-app of ngrx/platform](https://github.com/ngrx/platform/tree/master/projects/example-app) is a project example with best-practises of NgRx
    * Redux basics
      * lifecycle:
        ![Redux Lifecycle](https://res.cloudinary.com/practicaldev/image/fetch/s--fCDvEpjd--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://i.stack.imgur.com/LNQwH.png)
        *(source: [ABC of Redux](https://dev.to/radiumsharma06/abc-of-redux-5461))*
      * there is only one application state; the *Store*
      * services and components can interact between themselves but receives their state from the *Store* (with use of subscriptions)
      * change in the store are *dispatched* into *Actions*
      * an *Action* has an type and could have data; the *Payload*
      * *Actions* are sent to *Reducers* by dispatching them from the *Store*
      * an Action is dispatched to every *Reducers* no matter whether the reducer could handle the action or not
        * always provide a default case in reducer that returns the unchanged state
        * action.type must be unique in the whole application
      * *Reducers* copy a *State* from the *Store*, apply required changed on it with the *Action* & *Payload* and saves the reduced State in the *Store*
      * *State* are immutable (or must be immutable)
      * a JavaScript object can be shallow-copied with spread operator: `const newObject = { ...object };`
    * NgRx basics
      * lifecycle: 
        ![NgRx Lifecycle](https://ngrx.io/generated/images/guide/store/state-management-lifecycle.png)
        *(source: [NgRx](https://ngrx.io/guide/store))*
      * *selector*: [selectors](https://ngrx.io/guide/store/selectors) are pure functions used for obtaining slices of store state.
        * see [example of selector](https://ngrx.io/guide/store/selectors#selecting-feature-states) that uses [createFeatureSelector](https://ngrx.io/api/store/createFeatureSelector) and [createSelector](https://ngrx.io/api/store/createSelector) functions
      * *feature state*: state associated to a feature module; see [register feature state](https://ngrx.io/guide/store/reducers#register-feature-state)
      * *effect*: allow to handle asynchronous events
        * Effects are long-running services that listen to an observable of every action dispatched from the Store.
        * Effects filter those actions based on the type of action they are interested in. This is done by using an operator.
        * Effects perform tasks, which are synchronous or asynchronous and return a new action (have to).
      * *router-store module*: @ngrx/router-store module allow to dispatch events to route navigation (that could be listened in effect e.g.)
        * npm install --save-dev @ngrx/router-store
        * import StoreRouterConnectingModule to app.module.ts
      * *browser redux devtools* extension allow to see dispatched actions and Store changes
        * search "redux devtools extension" and install it in chrome
        * npm install --save-dev @ngrx/store-devtools
        * import StoreDevtoolsModule in app.module.ts
        * call .instrument({logOnly: environment.production})
  * [Angular Flex-Layout](https://github.com/angular/flex-layout/wiki/API-Documentation) provide layout API using 
    [Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
    and [mediaQuery](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)
    * basics
      * use [fxLayout](https://github.com/angular/flex-layout/wiki/fxLayout-API) directive to define flex-direction on the container
      * use [fxLayoutAlign](https://github.com/angular/flex-layout/wiki/fxLayoutAlign-API) directive to align flex items on the main and cross-axis
      * use [fxLayoutGap](https://github.com/angular/flex-layout/wiki/fxLayoutGap-API) directive to specify margin gaps on children within a flexbox container
      * use [fxHide](https://github.com/angular/flex-layout/wiki/fxHide-API) and [fxShow](https://github.com/angular/flex-layout/wiki/fxShow-API) directives to show/hide component in combination with breakpoints;
        * hide a div on small devices: ```<div fxHide.xs>...</div>```
        * hide a div on greater than small devices: ```<div fxHide.gt-xs>...</div>```
    * docs: [Overview of core directives](https://github.com/angular/flex-layout/wiki/Declarative-API-Overview)
      and [Responsive API](https://github.com/angular/flex-layout/wiki/Responsive-API)
  * [Angular Material](https://material.angular.io/) is an Angular components suite based on 
    [Google Material Design specifications](https://material.io/design/)
    * [Getting Started with Angular Material](https://material.angular.io/guide/getting-started)
    * Angular Material is based on two packages:
      * [component dev kit](https://material.angular.io/cdk/categories)(CDK) to develop a component suite (@angular/cdk)
      * [component suite](https://material.angular.io/components/categories) based on Material Design (@angular/material)
    * see list of [Material Icons](https://material.io/resources/icons/?style=baseline)
    * Angular Material provide no grid system; 
      use [Angular Flex-Layout](https://github.com/angular/flex-layout/wiki/API-Documentation)
  * [AngularFire](https://github.com/angular/angularfire) is an Angular connector library to 
    [Firebase](https://firebase.google.com/) (Backend-as-a-Service (BaaS); no service-side code required)
  * [NestJS](https://nestjs.com/) is a web framework for [Node.js](https://nodejs.org/en/) and can used in 
    [Angular Universal](https://angular.io/guide/universal#universal-in-action) instead of 
    [ExpressJS](https://expressjs.com/) to provide
    [Server-side Rendering](https://developers.google.com/web/updates/2019/02/rendering-on-the-web)
    * Angular Universal with NestJS vs Angular Universal with ExpressJS:
      * default Angular Universal only pre-render HTML webpage
      * NestJS allow to build REST APIs
      * NestJS is a server-side framework that borrow a lot from Angular and use TypeScript
      * Angular + NestJS is a full-stack
    * use [nestjs/ng-universal](https://github.com/nestjs/ng-universal) to integrate NestJS to Angular Universal 
    * see [NestJS docs](https://docs.nestjs.com/) 

*(Page mainly written in 2019, last update: july 2020)*

[*Go to parent page*](../README.md)


## Databinding
Angular offers various solutions to [components interaction](https://angular.io/guide/component-interaction#component-interaction) for different use cases.

* [String interpolation](https://angular.io/guide/interpolation): `{{ data }}` (ctrl>view)
* [Property binding](https://angular.io/guide/property-binding): `[property]="data"` (ctrl>view)
* [Event binding](https://angular.io/guide/event-binding): `(event)="expression"` (view>ctrl)
* [Two-way binding](https://angular.io/guide/two-way-binding): `[(property)]="data"` (view<>ctrl)
  * (two-way binding is a syntactic sugar for a property binding and an event binding)
* [ngModel](https://angular.io/guide/built-in-directives#ngModel) directive allow two-way binding of form's inputs 
  
[*Go to top*](#Angular)

### Custom property and event bindings
* Binding custom properties with [@Input](https://angular.io/api/core/Input#usage-notes)
* Binding custom events with [@Output](https://angular.io/guide/inputs-outputs#configuring-the-child-component-1)
* [Alias of @Input/@Output](https://angular.io/guide/attribute-directives#bind-to-an-input-alias) to have different public name than class property
* Components communication with @Input & @Output is good is component are not far for themselves (e.g. parent-child)
  
[*Go to top*](#Angular)

### Template reference variables
* a [template reference variable](https://angular.io/guide/template-reference-variables) is a reference to a DOM element available within in template (could replace bindings with custom properties)
  
[*Go to top*](#Angular)

### ViewChild
* [@ViewChild](https://angular.io/guide/component-interaction#parent-calls-an-viewchild) allow to access template reference element as [ElementRef](https://angular.io/api/core/ElementRef) from Component ts file (e.g. input field value readable with ElementRef.nativeElement.value)
  
[*Go to top*](#Angular)

### ng-content
* ng-content allow to project content into a reusable component (e.g. tabs component)
* see following [article](https://medium.com/claritydesignsystem/ng-content-the-hidden-docs-96a29d70d11b) (ng-content is officialy not documented; [issue](https://github.com/angular/angular/issues/17983))
* [@ContentChild](https://angular.io/api/core/ContentChild) allow to access reference of the ng-content element as [ElementRef](https://angular.io/api/core/ElementRef) from injected component ts file
  
[*Go to top*](#Angular)

### ng-container
* [ng-container](https://angular.io/guide/structural-directives#ng-container-to-the-rescue)  is a grouping element that doesn't interfere with styles or layout because Angular doesn't put it in the DOM.
  
[*Go to top*](#Angular)

### Lifecycle hooks
* See [component & directives lifecycle & hooks](https://angular.io/guide/lifecycle-hooks#lifecycle-hooks)
* [@ViewChild](https://angular.io/api/core/ViewChild) properties are available on/after [ngAfterViewInit](https://angular.io/api/core/AfterViewInit#ngafterviewinit); not on [ngOnInit](https://angular.io/api/core/OnInit)
* [@ContentChild](https://angular.io/api/core/ContentChild) properties are available on/after [ngAfterContentInit](https://angular.io/api/core/AfterContentInit#ngaftercontentinit); not on [ngOnInit](https://angular.io/api/core/OnInit)
* See article [Everything you need to know about the `ExpressionChangedAfterItHasBeenCheckedError` error](https://indepth.dev/everything-you-need-to-know-about-the-expressionchangedafterithasbeencheckederror-error/), [page 2](https://indepth.dev/everything-you-need-to-know-about-the-expressionchangedafterithasbeencheckederror-error/)

[*Go to top*](#Angular)


## Directives
* [types of directives](https://angular.io/guide/attribute-directives#directives-overview): components, [structural](https://angular.io/guide/structural-directives) & [attribute](https://angular.io/guide/attribute-directives) directives
* built-in structural directives: [ngIf](https://angular.io/api/common/NgIf), [ngStyle](https://angular.io/api/common/NgStyle), [ngClass](https://angular.io/api/common/NgClass), [ngFor](https://angular.io/api/common/NgForOf), [ngSwitch](https://angular.io/guide/structural-directives#inside-ngswitch-directives)
  * [ng-if else](https://angular.io/api/common/NgIf#showing-an-alternative-template-using-else) (or write ngIf twice)
  * [getting index of ng-for](https://angular.io/api/common/NgForOf#description)
* see explanation of [`*` structural directive's prefix](https://angular.io/guide/structural-directives#asterisk) 
* [custom attribute directive](https://angular.io/guide/attribute-directives#build-a-simple-attribute-directive)
  * by using [Renderer2](https://angular.io/api/core/Renderer2)
  * [@HostListener](https://angular.io/api/core/HostListener) to listen host event
  * [@HostBinding](https://angular.io/api/core/HostBinding) to bind host properties
  * [@Input to pass values to directive](https://angular.io/guide/attribute-directives#pass-values-into-the-directive-with-an-input-data-binding)
    * [Use alias to avoid extra attribute](https://angular.io/guide/attribute-directives#bind-to-an-input-alias)
* [custom structural directive](https://angular.io/guide/structural-directives#write-a-structural-directive)
* [AngularJS ngShow](https://docs.angularjs.org/api/ng/directive/ngShow) can be simulated in Angular by using property binding `[hidden]="condition"` on [hidden](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/hidden) html attribute

[*Go to top*](#Angular)


## Debugging
* Read carefully Angular Error Message in console and google
* Use [Angular Augury](https://augury.rangle.io/) DevTools extension
* Add breakpoint to sourcemaps (e.g. under Sources > webpack:// > . > src > ...)

[*Go to top*](#Angular)


## Styling
* application-wide styles can be done by
  1. add `<link rel="stylesheet" href="...">` into `index.html` with CDN url or local file (should be in assets folder)
  2. update `styles.css` (default global angular style)
  3. modify [global style](https://angular.io/guide/workspace-config#styles-and-scripts-configuration) in `angular.json`
      * typical use-case: `styles` link to a css file of a css framework npm module
* component-scoped styles can be done by
  1. use `styles` or [styleUrls](https://angular.io/api/core/Component#styleurls) of `@Component` decorator
  2. add `<style>` or `<link>` to component template
* [View encapsulation](https://angular.io/guide/view-encapsulation): component styles are applied, by default, only within the template of that component
  * Angular emulate [shadow DOM](https://en.wikipedia.org/wiki/Web_Components#Shadow_DOM) by giving a specific attribute value for every html tags of a component; CSS can be applied then by using this attribute in the CSS selector
  * see [style scope](https://angular.io/guide/component-styles#style-scope)
  * default view encapsulation can be overidden by changing [@Component.encapsulation](https://angular.io/api/core/Component#encapsulation)
* Special selectors
  * [:host](https://angular.io/guide/component-styles#host) targets the element which host the component
    * function form `:host` component allow to style the host component on given css selector condition(e.g. `:host(.active)`)
  * [:hostcontext](https://angular.io/guide/component-styles#host-context) style elements inside a component, depending on some condition set outside of it
* Directives [ngClass](https://angular.io/api/common/NgClass) and [ngStyle](https://angular.io/api/common/NgStyle) are common way to dynamic style components
* Angular component selector like `app-xyz { ... }` can be used in css
* [@import](https://angular.io/guide/component-styles#css-imports) can be used to import css files into css file
* Angular [Renderer2](https://angular.io/api/core/Renderer2) is a service to manipulate elements of your app without having to touch the DOM directly

[*Go to top*](#Angular)


## Animations
* Angular's Animations system is built on CSS functionality and allow animate HTML elements in complex sequences and choreographies.
* Angular's Animations are implemented through a DSL language
* CSS Transitions/CSS Animations vs Angular Animations
  * allow to style an animation on one step; to keep all the stuff in angular world
  * angular animation allow to animate element added on the fly in the DOM (e.g. with *ngIf); its very difficult to manage it with CSS Animations
  * complex animation should be done in Angular Animations
  * infinite animation should be done with CSS Transitions/CSS Animations (not well done in Angular Animations)
* Concepts
  * [trigger](https://angular.io/guide/animations#triggering-the-animation) encapsulates a named animation; the transitions between states included in its definition when a change occurs
  * [state](https://angular.io/guide/animations#animation-state-and-styles) define styles related to a given named state
  * [transition](https://angular.io/guide/animations#transitions-and-timing) define animation between styles of state
* [Introduction to Angular Animations](https://angular.io/guide/animations)
* List of [animatable CSS properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) (evolves over time)
* Advanced topics
  * [Animations transitions and triggers](https://angular.io/guide/transition-and-triggers)
    * [wildcard state (*)](https://angular.io/guide/transition-and-triggers#wildcard-state) means any state
    * [void state](https://angular.io/guide/transition-and-triggers#void-state) means state when element is not in the DOM
    * [:enter and :leave aliases](https://angular.io/guide/transition-and-triggers#enter-and-leave-aliases) for `void => *` and `alias for * => void`
    * [use wildcards with styles](https://angular.io/guide/transition-and-triggers#using-wildcards-with-styles) to use current style value
  * [Animation callbacks](https://angular.io/guide/transition-and-triggers#animation-callbacks) (be informed when animation start/end)
  * [Complex animation sequences](https://angular.io/guide/complex-animation-sequences)
    * [query()](https://angular.io/guide/complex-animation-sequences#animate-multiple-elements-using-query-and-stagger-functions) allow to find and animate inner elements; see also [query](https://angular.io/api/animations/query) in reference
  * [Route transition animations](https://angular.io/guide/route-animations)
  * [AnimationBuilder](https://angular.io/api/animations/AnimationBuilder) allow to produce animation programmatically
  * Animation can be added to component by using [HostBinding](https://angular.io/api/core/HostBinding); see [example](https://angular.io/guide/complex-animation-sequences#animate-multiple-elements-using-query-and-stagger-functions)
* Tips
  * Animations works on block element but per default Component are inline-block element. Don't forget to add e.g.
```
:host {
    display: block;
}
```

[*Go to top*](#Angular)


## Services and Dependency Injection
* [services](https://angular.io/guide/architecture-services#introduction-to-services-and-dependency-injection) are normally classes and are provided
  * ... in [@Injectable](https://angular.io/guide/hierarchical-dependency-injection#moduleinjector) decorator on the service itself
  * ... in [@NgModule.providers](https://angular.io/guide/hierarchical-dependency-injection#moduleinjector) or [@Component.providers](https://angular.io/guide/hierarchical-dependency-injection#component-level-injectors)
* [hierarchical injector](https://angular.io/guide/hierarchical-dependency-injection) : instance of service provided to a given Module/Component will be provided to childs 
  * a [singleton service](https://angular.io/guide/singleton-services) is provided at root level
* [@Injectable](https://angular.io/api/core/Injectable) decorator required on the target service to [inject services into services](https://angular.io/guide/dependency-injection#using-services-in-other-services)
* services ease [cross-component communication](https://angular.io/guide/component-interaction#parent-and-children-communicate-via-a-service) (by using [EventEmitter](https://angular.io/api/core/EventEmitter) or RxJS)

[*Go to top*](#Angular)


## Routing

### Routing configuration
* [Register router and Routes](https://angular.io/guide/router#configuration) in app.module.ts
* [Add `<router-outlet>` in template](https://angular.io/guide/router#router-outlet) where routed components will be rendered
* [Configure route parameters (e.g. id)](https://angular.io/guide/router-tutorial-toh#route-parameters)

[*Go to top*](#Angular)


### Navigation
* Navigating in templates with [routerLink](https://angular.io/api/router/RouterLink) directive and following [properties](https://angular.io/api/router/RouterLink#description): queryParams, fragment
  * Add CSS Class in template with [routeLinkActive](https://angular.io/guide/router#active-router-links) (see also  routerLinkActiveOptions)
* Navigating programmatically with [Router.navigate](https://angular.io/api/router/Router#navigate)(paths: any[], extras: [NavigationExtras](https://angular.io/api/router/NavigationExtras))
  * [NavigationExtras](https://angular.io/api/router/NavigationExtras) used to pass 
  [queryParams](https://angular.io/api/router/UrlCreationOptions#queryParams), 
  [fragment](https://angular.io/api/router/UrlCreationOptions#fragment), 
  [relative route](https://angular.io/api/router/UrlCreationOptions#relativeTo) 
  (e.g. [ActivatedRoute](https://angular.io/api/router/ActivatedRouteSnapshot))

[*Go to top*](#Angular)


### Retrieve route datas
* in ngOnInit with [ActivatedRoute](https://angular.io/api/router/ActivatedRoute).[snapshot](https://angular.io/api/router/ActivatedRoute#snapshot)() -> [ActivatedRouteSnapshot](https://angular.io/api/router/ActivatedRouteSnapshot) (contains params, queryParams, etc.)
* on every route changes within the component by by calling ["subscribe()"](https://angular.io/guide/observables-in-angular#router) with observables of [ActivatedRoute](https://angular.io/api/router/ActivatedRoute): [params](https://angular.io/api/router/ActivatedRoute#params), [queryParams](https://angular.io/api/router/ActivatedRoute#queryParams), [fragment](https://angular.io/api/router/ActivatedRoute#fragment), etc.

[*Go to top*](#Angular)


### Child routes
* [Child (Nested) Routes](https://angular.io/guide/router#nesting-routes):
  * specify [children](https://angular.io/api/router/Route#children) routes in app.module.ts
  * add [`<router-outlet>`](https://angular.io/api/router/RouterOutlet) in the template of the parent component to specify where children component must be renderer

[*Go to top*](#Angular)


### Guards
* Guards are services that implements interfaces like [CanActivate](https://angular.io/api/router/CanActivate)
* Guards are configured into Route, e.g. [Route.canActivate](https://angular.io/api/router/Route#canActivate)
* Examples of guards:
  * [CanActivate: requiring authentication
](https://angular.io/guide/router-tutorial-toh#canactivate-requiring-authentication)
  * [CanActivateChild: guarding child routes](https://angular.io/guide/router-tutorial-toh#canactivatechild-guarding-child-routes)
  * [CanDeactivate: handling unsaved changes](https://angular.io/guide/router-tutorial-toh#candeactivate-handling-unsaved-changes)

[*Go to top*](#Angular)


### Provide static data to route
* provide [Route.data](https://angular.io/api/router/Route#data) in RouterModule configuration
* access data inside Component in ngOnInit from [ActivatedRoute.snapshot.data](https://angular.io/api/router/ActivatedRouteSnapshot#data) or by subscribing to [ActivatedRoute.data](https://angular.io/api/router/ActivatedRoute#data) Observable

[*Go to top*](#Angular)


### Resolve
* [Resolve: pre-fetching component data](https://angular.io/guide/router-tutorial-toh#resolve-pre-fetching-component-data)
* a service Resolver must implements [Resolve](https://angular.io/api/router/Resolve)
* configure [Route.resolve](https://angular.io/api/router/Route#resolve) in RouterModule configuration
* acess data inside Component in ngOnInit from [ActivatedRoute.snapshot.data](https://angular.io/api/router/ActivatedRouteSnapshot#data) or by subscribing to [ActivatedRoute.data](https://angular.io/api/router/ActivatedRoute#data) Observable

[*Go to top*](#Angular)


### Location strategies
* [Location strategies](https://angular.io/guide/router#locationstrategy-and-browser-url-styles)
* productive webserver must be configured so that 404 error are redirected to index.html
* if that's not possible, [HashLocationStrategy
](https://angular.io/guide/router#hashlocationstrategy) must be used as workaround

[*Go to top*](#Angular)


### Miscelleanous
* Use [router.navigate(..., { queryParamsHandling: ...})](https://angular.io/api/router/UrlCreationOptions#queryParamsHandling) to preserve query params when navigating between routes
* [Redirecting and Wildcard routes](https://angular.io/guide/router#setting-up-redirects)
* [Separate Module for Route configuration](https://angular.io/guide/router-tutorial-toh#milestone-2-routing-module)

[*Go to top*](#Angular)


## Observables - RxJS
* [Observables in Angular](https://angular.io/guide/observables-in-angular)
* [Operators](https://angular.io/guide/rx-library#operators) used with pipe() function
* [Subject](https://rxjs.dev/guide/subject) is the new approach to [EventEmitter](https://angular.io/api/core/EventEmitter) for communication between components 
* EventEmitter is always used for event binding (with @Output)
* Subject are better to be used with services
* Subject is an Observable on which we can call next() from outside the observable
* see [RxJS](./RxJS.md) for more informations about RxJS

[*Go to top*](#Angular)


## Forms

Angular provides two different approaches to handling user input through forms. See [comparison](https://angular.io/guide/forms-overview#key-differences) between [reactive](https://angular.io/guide/reactive-forms) and [template-driven](https://angular.io/guide/forms) approach.

### Template-driven forms
With [Template-driven forms](https://angular.io/guide/forms), Angular infers the Form Object ([FormGroup](https://angular.io/api/forms/FormGroup)) from the DOM.

Basic steps to implements template-driven forms:
* import [FormsModule](https://angular.io/api/forms/FormsModule)
* (Angular automatically add an [ngForm](https://angular.io/api/forms/NgForm) directive to the `<form>`)
* add [ngModule](https://angular.io/api/forms/NgModel) directive on `<input>`
* add [ngSubmit](https://angular.io/api/forms/FormGroupDirective#properties) event emitter on `<form>`
* add a [template reference variable `<form #f="ngForm">`](https://angular.io/guide/forms#submit-the-form-with-ngsubmit) to access the FormGroup / form state inside the template
* add a [ViewChild](https://angular.io/api/core/ViewChild) annotation to access the template reference variable of the NgForm inside controller:
```
    @ViewChild('f', { static: false }) signupForm: NgForm;
```
* add [built-in validators](https://angular.io/api/forms/Validators) (`required`, `email`, etc.) on `<input>`
* add styles or *ngIf by using css classes: `ng-untouched`/`ng-touched`, `ng-pristine`/`ng-dirty`, `ng-valid`/`ng-invalid`, see [Angular docs](https://angular.io/guide/forms#create-visual-feedback-for-states)
* custom validator is implemented with [directives](https://angular.io/guide/form-validation#adding-to-template-driven-forms) 
* binding with [ngModel](https://angular.io/api/forms/NgModel) directive:
  * no binding: indicate Angular which input to manage
  * one-way binding: set default value to input, e.g. `<select [ngModel]="defaultQuestion" ...>`
  * two-way binding: variable inside controller instantly updated on user-input
* use [ngModelGroup](https://angular.io/api/forms/NgModelGroup) directive to group several input into a logical group
* call [NgForm.from.patchValue({ key:value })](https://angular.io/api/forms/FormGroup#patchvalue) to override specific form values

[*Go to top*](#Angular)


### Reactive forms
With [Reactive forms](https://angular.io/guide/reactive-forms), Form is created programmatically and synchronised with the DOM.

* import [ReactiveFormsModule](https://angular.io/api/forms/ReactiveFormsModule)
* create a [FormGroup](https://angular.io/guide/reactive-forms#grouping-form-controls) inside component controller
* add [[formGroup]="xxxx"](https://angular.io/api/forms/FormGroupDirective) directive to the `<form>` in the template to oneway bind [FormGroup](https://angular.io/api/forms/FormGroup) of the controller to the template
* add [formControlName](https://angular.io/api/forms/FormControlName) directive to `<input>`s in template
* add [(ngSubmit)="xxx()"](https://angular.io/guide/reactive-forms#grouping-form-controls) event emitter to `<form>` in template 
* Validation directive does not work (e.g. `required`)
* [Validators](https://angular.io/api/forms/Validators) must be added to the 2nd parameter to [FormControl](https://angular.io/api/forms/FormControl)
* control / form state are available in the template by calling get on bind FormGroup, e.g. `<span *ngIf="!signupForm.get('email').valid && signupForm.get('email').touched">...<span>`
* `FormGroup` can contains `FormGroup`
  * add ["formGroupName"="..."](https://angular.io/api/forms/FormGroupName) in template
  * `"FormGroup.get()"` can contains path with . separator
* add [FormArray](https://angular.io/api/forms/FormArray) to `FormGroup`
  * constructor of [FormArray](https://angular.io/api/forms/FormArray) expect an array
  * cast is required when retrieving `FormArray` from `FormGroup`: `<FormArray>formGroup.get('xyz')`
  * add [formArrayName="..."](https://angular.io/api/forms/FormArrayName) directive in template
  * use index of [*ngFor](https://angular.io/api/common/NgForOf) to set the [formControlName](https://angular.io/api/forms/FormControlName)
* [custom validator](https://angular.io/guide/form-validation#custom-validators) are functions in Reactive forms
  * add custom validator to validator array of the FormControl in 2nd parameter
  * `.bind(this)` required if `this` is used inside the validator function
  * validator in error are set on the `.errors` field of the FormControl; can be used in template to customize error message
* [async validator](https://angular.io/guide/form-validation#implementing-a-custom-async-validator) are used e.g. to validate field on the server
  * async validator return Promise or Observable
  * async validator are added in FormControl third argument
  * ng-pending class is set the FormControl while waiting to the async validator result
* FormGroup, FormControl have two observables [valueChanges and statusChanges](https://angular.io/api/forms/AbstractControl#properties)
* [FormGroup.setValue()](https://angular.io/api/forms/FormGroup#setvalue), [.patchValue()](https://angular.io/api/forms/FormGroup#patchvalue) are also available with Reactive forms
* [FormGroup.reset()](https://angular.io/api/forms/FormGroup#reset) could be called on submit to reset form controls (optional arg allow to set default value; e.g. for radiobuttons)

[*Go to top*](#Angular)


## Pipes
* [pipes](https://angular.io/guide/pipes) are used to transform output into templates
* [built-in pipes](https://angular.io/api?type=pipe): [uppercase](https://angular.io/api/common/UpperCasePipe), [async](https://angular.io/api/common/AsyncPipe), [date](https://angular.io/api/common/DatePipe), etc.
  * [async](https://angular.io/api/common/AsyncPipe) pipe wait completion of Promise or Observable to output resolve value
* [parameterize pipe](https://angular.io/guide/pipes#transforming-data-with-parameters-and-chained-pipes) with `:` ; e.g. `{{ birthday | date:"MM/dd/yy" }}`
* [chaining pipes](https://angular.io/guide/pipes#transforming-data-with-parameters-and-chained-pipes) with `|` ; e.g. `{{ birthday | date | uppercase}}`
* [custom pipe](https://angular.io/guide/pipes#creating-pipes-for-custom-data-transformations) is an exported class that implements [PipeTransform](https://angular.io/api/core/PipeTransform) with [Pipe](https://angular.io/api/core/Pipe) declarator (to specify the name in template)
  * custom pipe must be declare in module
  * custom pipe can be parametrize by adding more than one parameter to [transform](https://angular.io/api/core/PipeTransform#transform) function
  * generate pipe with cli: `ng g p xyz`
* pipe can be also applied to *ngFor (e.g. filter); [see example](https://angular.io/guide/pipes#how-change-detection-works)
* [pure](https://angular.io/guide/pipes#detecting-pure-changes-to-primitives-and-object-references) and [impure](https://angular.io/guide/pipes#detecting-impure-changes-within-composite-objects) pipes
  * pure pipes (default): Angular does not re-render pipes after output changes
  * impure pipes: Angular executes an impure pipe during every component change detection cycle
  * make impure pipe: configure `Pipe.`[pure](https://angular.io/api/core/Pipe#pure) property = false
  * impure pipes can be called very often and be a performance issue

[*Go to top*](#Angular)


## Http
* make requests
  * to use [http](https://angular.io/guide/http) import [HttpClientModule](https://angular.io/api/common/http/HttpClientModule)
  * inject [HttpClient](https://angular.io/api/common/http/HttpClient) to controller constructor
  * use HttpClient.[get()](https://angular.io/api/common/http/HttpClient#get)/[post()](https://angular.io/api/common/http/HttpClient#post)/[put()](https://angular.io/api/common/http/HttpClient#put)/[delete()](https://angular.io/api/common/http/HttpClient#delete) / etc.
  * request are sent only by subscribing to [Observable](https://rxjs.dev/api/index/class/Observable) in http methods'result 
  * use `pipe` and [map](https://rxjs.dev/api/operators/map) [rxjs operator](https://rxjs.dev/guide/operators) to convert HttpClient response to required object
  * we can specify the [type of response of HttpClient methods](https://angular.io/guide/http#requesting-a-typed-response)
  * it's a good practise to encapsulate HttpClient calls inside a custom service, [see example](https://angular.io/guide/http#requesting-a-typed-response)
    * [Observable](https://rxjs.dev/api/index/class/Observable) result of HttpClient methods encapsulated into a custom service can also be returned from it
    * [Subject](https://rxjs.dev/api/index/class/Subject) can be used if several components are interested in the response
  * use [mergeMap](https://rxjs.dev/api/operators/mergeMap) or [exhaustMap](https://rxjs.dev/api/operators/exhaustMap) rxjs operators to pipe several http calls; [see example](https://coryrylan.com/blog/angular-multiple-http-requests-with-rxjs)
  * use [forkJoin](https://rxjs.dev/api/index/function/forkJoin) rxjs operator to performs http calls in parallel; [see example](https://coryrylan.com/blog/angular-multiple-http-requests-with-rxjs)
* handling error
  * [Provide a error callback](https://angular.io/guide/http#error-handling) to the [2nd argument of Observable](https://rxjs.dev/api/index/class/Observable#subscribe-) returned when calling subscribe on HttpClient methods
  * use [catchError](https://rxjs.dev/api/operators/catchError) rxjs operator inside pipe, that will return an Observable created with [throwError](https://rxjs.dev/api/index/function/throwError) rxjs function; [see example](https://angular.io/guide/http#getting-error-details)
* headers
  * provide [HttpHeaders](https://angular.io/api/common/http/HttpHeaders) to `headers` field of last arg of HttpClient methods, [see example](https://angular.io/guide/http#adding-and-updating-headers)
* query parameters
  * provide [HttpParams](https://angular.io/api/common/http/HttpParams) to `params` field of last arg of HttpClient methods
  * use [HttpParams.append](https://angular.io/api/common/http/HttpParams#append) method if you have several query params; take care: HttpParams is immutable
  * see [example](https://angular.io/guide/http#configuring-http-url-parameters)
* customize requests
  * access whole response (e.g. http status code) by providing `{ observe: 'response' }` to last arg of HttpClient methods; [see example](https://angular.io/guide/http#reading-the-full-response)
  * [http events can be listened](https://angular.io/guide/http#report-progress) if a fine granular control over request is required (e.g. download progress)
  * `responseType` can be customized, [see example](https://angular.io/guide/http#requesting-non-json-data)
* interceptors
  * interceptor is a service that have to implement [HttpInterceptor](https://angular.io/api/common/http/HttpInterceptor)
  * interceptor is configured in `app.module.ts` as providers under `HTTP_INTERCEPTORS`
  * [see example](https://angular.io/guide/http#intercepting-requests-and-responses)
  * [HttpRequest](https://angular.io/api/common/http/HttpRequest) is immutable but by calling HttpRequest.[clone()](https://angular.io/api/common/http/HttpRequest#clone), interceptor can modify completelly the request (e.g. adding headers)
  * typical usecase: [set default headers](https://angular.io/guide/http#setting-default-headers)
  * response can also be modified by calling `pipe` on the response of `HttpHandler`; e.g. [Caching Request](https://angular.io/guide/http#caching)
  * interceptors are executed [in the order of their definition in module](https://angular.io/guide/http#interceptor-order)

[*Go to top*](#Angular)


## Authentication
* Basic concepts
  * Server validate credentials and deliver a token (e.g. json) to frontend
  * Frontend save the token (e.g. localStorage) and sent it to any subsecent authorized requests
  * Only the server is able to generate the token with a private key and a given algorithm and his therefore secure
* Links
  * [JWT (JSON Web Tokens)](https://jwt.io/)

[*Go to top*](#Angular)


## Dynamic Components

* Dynamic components can be achieve with `ngIf` in templates or by loading component programmatically and pushing into view
* ngIf approach is easier and is the best solution in most cases
* loading component programmatically could be used in some specific use cases (e.g. custom framework)
* Steps to load component programmatically
  * write an [*anchor* directive](https://angular.io/guide/dynamic-component-loader#the-anchor-directive) to get access to the location (view) in template where to insert component
  * add anchor directive into template [added to the template](https://angular.io/guide/dynamic-component-loader#loading-components)
  * add @ViewChild on the anchor directive into controller to access the public property [ViewContainerRef](https://angular.io/api/core/ViewContainerRef)   
  * [ComponentFactoryResolver](https://angular.io/api/core/ComponentFactoryResolver) allow to retrieve a component factory to create specific component
  * [ViewContainerRef.clear()](https://angular.io/api/core/ViewContainerRef#clear) called to remove all views (components)
  * [ViewContainerRef.createComponent()](https://angular.io/api/core/ViewContainerRef#createcomponent) called with the component factory in argument to create the component inside the view
  * [ViewContainerRef.createComponent()](https://angular.io/api/core/ViewContainerRef#createcomponent) return [ComponentRef](https://angular.io/api/core/ComponentRef) that must be stored to pass data later
  * access instance of loaded component with [ComponentRef.instance](https://angular.io/api/core/ComponentRef#instance) to access/set @Input/@Output properties
  * forget not to unsubscribe, e.g. EventEmitter(@Output) before replacing components into view (Subscription to be stored)
  * dynamic loaded components have to be declared to [entryComponents](https://angular.io/api/core/NgModule#entryComponents) in NgModule
    * [entryComponents is deprecated](https://angular.io/guide/entry-components#the-entrycomponents-array)

[*Go to top*](#Angular)


## Optimizations
      
* [Ahead-of-time (AoT) compilation](https://angular.io/guide/aot-compiler)
  * TypeScript compiler compiles TS into JavaScript and is called in the build process
  * Angular compiler compile template into JavaScript DOM instructions
  * Just-in-Time (JiT) compilation: Angular compiler run in the browser (at runtime)
  * Ahead-of-time (AoT) compilation: Angular compiler run in the build process
  * `ng build --prod` will perfom the AoT compilation into `dist/` folder

[*Go to top*](#Angular)


## Deployment
* Use & check [environment variables](https://angular.io/guide/build#configuring-application-environments)
  * `ng build --prod` ensure to use `/environment/environment.prod.ts` instead of `/environment/environment.ts`
  * store key-value in `environment.ts` like API key
  * `import { environment } from '../environments/environment';`
* build app: `ng build --prod`
  * [deploy to GitHub pages with --base-href](https://angular.io/guide/deployment#deploy-to-github-pages)
* deploy to a static website host (without serverside language)
  * it's important to make sure that your server is configured to [always serve the index.html](https://angular.io/guide/deployment#routed-apps-must-fallback-to-indexhtml) file (and not returning 404)
* see [angular docs](https://angular.io/guide/deployment)

[*Go to top*](#Angular)


## Testing
* see mainly [Official Docs](https://angular.io/docs/ts/latest/guide/testing.html)
* isolated tests: unit test without angular bundle (e.g. testing a pipe or a simple service)
* non isolated tests: unit test with angular bundle (e.g. with TestBed)
* [fixture.detectChanges()](https://angular.io/guide/testing-components-scenarios#detectchanges) call is required to perform data binding
* [spy](https://angular.io/guide/testing-components-scenarios#testing-with-a-spy) can be used to mock remote servers
* test asynchronous code
  * [async](https://angular.io/guide/testing-components-scenarios#component-with-async-service) and whenStable() methods are used to test asynchronous code;
  * [whenStable()](https://angular.io/guide/testing-components-scenarios#whenstable) is used to wait that all asynchronous code are finished
  * [fakeAsync](https://angular.io/guide/testing-components-scenarios#async-test-with-fakeasync) and tic methods are an alternative to async
  * [tick](https://angular.io/guide/testing-components-scenarios#the-tick-function) method is then used to say "finish all asynchronous tasks"
    
[*Go to top*](#Angular)

