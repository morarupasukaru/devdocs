# Angular

[Angular](https://angular.dev/) is a [TypeScript](TypeScript.md) framework to build 
[single-page applications](https://en.wikipedia.org/wiki/Single-page_application) (SPA).

* [tutorials](https://angular.dev/tutorials)
* [main concepts](https://angular.dev/essentials) : components, signals, templates, dependency injection
* in-depth guides:
  [signals](https://angular.dev/guide/signals),
  [components](https://angular.dev/guide/components)
  [templates](https://angular.dev/guide/templates)
  [directives](https://angular.dev/guide/directives)
  [dependency injection / services](https://angular.dev/guide/di)
  [routing](https://angular.dev/guide/routing)
  [forms](https://angular.dev/guide/forms)
  [HTTP client](https://angular.dev/guide/http)
  [server-side & hybrid rendering](https://angular.dev/guide/performance)
  [testing](https://angular.dev/guide/testing)
  [internationalization](https://angular.dev/guide/i18n)
  [animations](https://angular.dev/guide/animations)
  [drag'n drop](https://angular.dev/guide/drag-drop)
* devtools:
  [angular cli](https://angular.dev/tools/cli),
  [how to use & create libraries](https://angular.dev/tools/libraries),
  [browser devtools extension](https://angular.dev/tools/devtools)
* best-practises
  * TODO 
* ecosystem
  * TODO
  * [Angular Elements](https://angular.dev/guide/elements#) turn Angular Components as [Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components)
  * [Progressive Web App](PWA.md) to provide desktop's like applications
  * [Web workers](https://angular.dev/ecosystem/web-workers#) to run computations in a background thread
  * [RxJS](RxJS.md) for reactive programming using observables that makes it easier to compose asynchronous 
    or callback-based code
  * [NgRx](https://github.com/morarupasukaru/devdocs/blob/main/minor-topics/NgRx.md) used to manage application state
  * [Angular Flex-Layout](https://github.com/angular/flex-layout/wiki/API-Documentation) provide layout API (grid-system) using
    [Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
    and [mediaQuery](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)
  * [Angular Material](https://material.angular.io/) is an Angular components suite based on
    [Material Design](https://m3.material.io/) of Google
  * [NestJS](https://nestjs.com/) is a full-stack angular web framework for [server-side](https://web.dev/articles/rendering-on-the-web)
    applications with [Node.js](https://nodejs.org/en/)
* references
  * TODO 
  * [angular versions](https://en.wikipedia.org/wiki/Angular_(web_framework)#History): 2 (9.2016) to 20 (05.2025)
  * [TypeScript](TypeScript.md)
  * [angular update guide](https://angular.dev/update-guide#)
  * [error encyclopedia](https://angular.dev/errors)
* courses
  * [The complete guide to angular](https://www.udemy.com/the-complete-guide-to-angular-2/)
  * [Angular material, angularfire & NgRx](https://www.udemy.com/angular-full-app-with-angular-material-angularfire-ngrx/)
  * [Angular styling & animations](https://www.udemy.com/angular-styling-animations-for-angular-2-and-angular-4/)
  * [Angular Testing Masterclass](https://www.udemy.com/course/angular-testing-course/) : nice course containing helpfull explanation about asynchronous testing
  * [Angular Security Masterclass](https://www.udemy.com/course/angular-security/)

----

interesting topics:
* templates: [@defer](https://angular.dev/guide/templates/defer) for deferred loading of views
* AI: [AI prompts](https://angular.dev/ai/develop-with-ai) to help LLMs generate correct code that follows Angular best practices
* internationalization: [ngx-translate](http://www.ngx-translate.com/) as alternative to [angular i18n](https://angular.dev/guide/i18n#)
* testing:
  * [ng-mocks](https://github.com/help-me-mom/ng-mocks) as alternative to spy
  * [shallow-render](https://github.com/getsaf/shallow-render) as alternative to Angular testing with shallow rendering and easy mocking
* ...
* observables?
* services?
* pipes?
* 
* 
  or 



[*Go to parent page*](../README.md)


## @Component

* Smart vs Presentational components
  * *presentational components* are only responsible to display some data from provided @Input and 
    returns modified data through @Output
  * *smart components* are responsible to retrieve/update data from services and pass data to presentational components
  * concepts of smart/presentational components are not specific to Angular but could be applied with 
    every frontend technology
  * see [Angular Architecture - Smart Components vs Presentational Components](https://blog.angular-university.io/angular-2-smart-components-vs-presentation-components-whats-the-difference-when-to-use-each-and-why/)  
* Improvement Angular performance with OnPush Change Detection strategy
  * angular default [change-detection](https://angular.io/guide/glossary#change-detection) strategy
    compare current and previous state of every bind data in template and update the DOM if necessary
  * alternative is to configure OnPush change detection strategy on some components:
    the change detector runs only when explicitly invoked, when Input changes or new value of observable used
    by async pipe are emmited
  * OnPush Change Detection strategy improve performances
  * OnPush Change Detection strategy can be enabled easily on components using reactive style
    (template accessing data through observables; with RxJS)
  * change detection strategy is defined on [@Component.changeDetection](https://angular.io/api/core/Component#changeDetection) options
  * see [Angular OnPush Change Detection and Component Design - Avoid Common Pitfalls](https://blog.angular-university.io/onpush-change-detection-how-it-works/)

[*Go to top*](#Angular)


## Services

[Services](https://angular.io/guide/architecture-services) are normally classes and provide some feature

* services ease [cross-component communication](https://angular.io/guide/component-interaction#parent-and-children-communicate-using-a-service) 
  by using [EventEmitter](https://angular.io/api/core/EventEmitter) or RxJS
* dependency-injection of services can be done with 
  [@Injectable](https://angular.io/guide/hierarchical-dependency-injection#moduleinjector) decorator on the service itself
  in [@NgModule.providers](https://angular.io/guide/hierarchical-dependency-injection#moduleinjector) or 
  [@Component.providers](https://angular.io/guide/hierarchical-dependency-injection#elementinjector)
* [hierarchical injector](https://angular.io/guide/hierarchical-dependency-injection) : instance of service provided to 
  a given Module/Component will be provided to childs
  (means that several instance of a service could exist in the application; depending on the DI configuration)
* a [singleton service](https://angular.io/guide/singleton-services) has to be provided at root level
* [@Injectable](https://angular.io/api/core/Injectable) decorator is required on the target service to 
  [inject services into services](https://angular.io/guide/creating-injectable-service#injecting-services)

[*Go to top*](#Angular)


## Routing

[Routing](https://angular.io/guide/router) define navigation of screens / components and associated url

* [configure router and Routes](https://angular.io/guide/router#defining-a-basic-route) in app.module.ts
  * [add `<router-outlet>` in template](https://angular.io/guide/router#defining-a-basic-route) where routed components will be rendered
  * [configure route parameters (e.g. id)](https://angular.io/guide/router-tutorial-toh#route-parameters)
  * [redirects and wildcard routes](https://angular.io/guide/router#setting-up-wildcard-routes) can also be configured
  * a good practise is to have a [separate module for route configuration](https://angular.io/guide/router-tutorial-toh#milestone-2-routing-module)
* define navigation in templates with [routerLink](https://angular.io/api/router/RouterLink) directive and 
  following [properties](https://angular.io/api/router/RouterLink#description): queryParams, fragment
  * add CSS class in template with [routerLinkActive](https://angular.io/api/router/RouterLinkActive) 
  (see also [routerLinkActiveOptions](https://angular.io/api/router/RouterLinkActive#properties))
* navigate programmatically with [Router.navigate](https://angular.io/api/router/Router#navigate)(paths: any[], extras: 
  [NavigationExtras](https://angular.io/api/router/NavigationExtras))
  * [NavigationExtras](https://angular.io/api/router/NavigationExtras) is used to pass 
    [queryParams](https://angular.io/api/router/UrlCreationOptions#queryParams), 
    [fragment](https://angular.io/api/router/UrlCreationOptions#fragment), 
    [relative route](https://angular.io/api/router/UrlCreationOptions#relativeTo) 
    (e.g. [ActivatedRoute](https://angular.io/api/router/ActivatedRoute))
  * tip: use [router.navigate(..., { queryParamsHandling: ...})](https://angular.io/api/router/UrlCreationOptions#queryParamsHandling) 
    to preserve query params when navigating between routes
* retrieve route datas in ngOnInit with 
  [ActivatedRoute](https://angular.io/api/router/ActivatedRoute).[snapshot](https://angular.io/api/router/ActivatedRoute#snapshot)() 
  that returns an [ActivatedRouteSnapshot](https://angular.io/api/router/ActivatedRouteSnapshot) 
  (containing params, queryParams, etc.)
* retrieve route datas on every route changes within the component by calling 
  `subscribe()` with observables of 
  [ActivatedRoute](https://angular.io/api/router/ActivatedRoute): 
  [params](https://angular.io/api/router/ActivatedRoute#params), 
  [queryParams](https://angular.io/api/router/ActivatedRoute#queryParams), 
  [fragment](https://angular.io/api/router/ActivatedRoute#fragment), etc.
* specify [child (nested) routes](https://angular.io/guide/router#nesting-routes) by setting
  [children](https://angular.io/api/router/Route#children) routes in app.module.ts
  * add [`<router-outlet>`](https://angular.io/api/router/RouterOutlet) in the template of the parent component to 
    specify where children component must be renderer
* guards are services that implements interfaces like [CanActivate](https://angular.io/api/router/CanActivate) and
  are called before component is rendered
  * guards are configured into Route like e.g. [Route.canActivate](https://angular.io/api/router/Route#canActivate)
  * examples of guards
    * [CanActivate could forbid access without authentication](https://angular.io/guide/router-tutorial-toh#canactivate-requiring-authentication)
    * [CanDeactivate could handle unsaved changes](https://angular.io/guide/router-tutorial-toh#candeactivate-handling-unsaved-changes)
* provide static data in [Route.data](https://angular.io/api/router/Route#data) in RouterModule configuration
  * access data inside Component in ngOnInit from [ActivatedRoute.snapshot.data](https://angular.io/api/router/ActivatedRouteSnapshot#data) 
    or by subscribing to [ActivatedRoute.data](https://angular.io/api/router/ActivatedRoute#data) Observable
* [provide/pre-fetch dynamic data to component](https://angular.io/guide/router-tutorial-toh#resolve-pre-fetching-component-data) with resolvers
  * a Resolver service must implements [Resolve](https://angular.io/api/router/Resolve)
  * configure [Route.resolve](https://angular.io/api/router/Route#resolve) in RouterModule configuration
  * access pre-fetch data inside Component in ngOnInit from 
    [ActivatedRoute.snapshot.data](https://angular.io/api/router/ActivatedRouteSnapshot#data) 
    or by subscribing to [ActivatedRoute.data](https://angular.io/api/router/ActivatedRoute#data) Observable
* define [location strategies](https://angular.io/guide/router#locationstrategy-and-browser-url-styles)
  if default setting are not sufficient
  * productive web-server must be configured so that 404 error are redirected to index.html
  * if that's not possible, [HashLocationStrategy](https://angular.io/guide/router#hashlocationstrategy) 
    must be used as workaround

[*Go to top*](#Angular)


## Other features

### Forms

[Forms](https://angular.io/guide/forms-overview#key-differences) can be written in two different ways in Angular:
[reactive](https://angular.io/guide/reactive-forms) or [template-driven](https://angular.io/guide/forms) approach



### Observables

[Observables](https://angular.io/guide/observables) provided by [RxJS](./RxJS.md) 
is used extensively within Angular to ease writing of asynchronous calls and event handling

* see quick [angular guide about RxJS](https://angular.io/guide/rx-library#the-rxjs-library) or [RxJS summary](./RxJS.md)
* Subject vs EventEmitter
  * [Subject](https://rxjs.dev/guide/subject) is the new approach to 
    [EventEmitter](https://angular.io/api/core/EventEmitter) for communication between components 
  * EventEmitter is always used for event binding (with @Output)
  * Subject are better to be used with services
  * Subject is an Observable on which we can call next() from outside the observable

[*Go to top*](#Angular)


### Pipes

[Pipes](https://angular.io/guide/pipes) are used to transform output into templates

* [built-in pipes](https://angular.io/api?type=pipe): [uppercase](https://angular.io/api/common/UpperCasePipe), 
  [async](https://angular.io/api/common/AsyncPipe), 
  [date](https://angular.io/api/common/DatePipe), etc.
  * note: async pipe unsubscribes automatically to avoid potential memory leaks
* [parameterize pipe](https://angular.io/guide/pipes#transforming-data-with-parameters-and-chained-pipes) with `:` ; e.g. `{{ birthday | date:"MM/dd/yy" }}`
* [chaining pipes](https://angular.io/guide/pipes#transforming-data-with-parameters-and-chained-pipes) with `|` ; e.g. `{{ birthday | date | uppercase}}`
* [custom pipe](https://angular.io/guide/pipes#creating-pipes-for-custom-data-transformations) is an exported class that implements [PipeTransform](https://angular.io/api/core/PipeTransform) with [Pipe](https://angular.io/api/core/Pipe) declarator (to specify the name in template)
* pipe can be also applied to *ngFor (e.g. filter); [see example](https://angular.io/guide/pipes#how-change-detection-works)
* [pure pipes](https://angular.io/guide/pipes#detecting-pure-changes-to-primitives-and-object-references) (default): Angular does not re-render pipes after output changes
* [impure pipes](https://angular.io/guide/pipes#detecting-impure-changes-within-composite-objects): Angular executes an impure pipe during every component change detection cycle
  * make impure pipe: set `Pipe.`[pure](https://angular.io/api/core/Pipe#pure) property = false
  * impure pipes can be called very often and be a performance issue
* typical custom pipe: make an unsafe URL as safe
```typescript
@Pipe({ name: 'safeUrl' })
export class SafeUrlPipe implements PipeTransform {

  constructor(private sanitizer: DomSanitizer) {  }

  transform(url) {
    return this.sanitizer.bypassSecurityTrustResourceUrl(url);
  }
}
```

[*Go to top*](#Angular)


### HttpClient

[HttpClient](https://angular.io/guide/http) provide an API to perform HTTP requests

* use HttpClient methods [get()](https://angular.io/api/common/http/HttpClient#get), 
  [post()](https://angular.io/api/common/http/HttpClient#post),
  [put()](https://angular.io/api/common/http/HttpClient#put),
  [delete()](https://angular.io/api/common/http/HttpClient#delete), etc.
* request are sent only by subscribing to the [Observable](https://rxjs.dev/api/index/class/Observable) 
  of http methods'result 
* use pipe and [map](https://rxjs.dev/api/operators/map) from [RxJS](https://rxjs.dev/guide/operators) 
  to convert response to required object
* [response's type](https://angular.io/guide/http-request-data-from-server#requesting-a-typed-response) can be specified
* good practise: encapsulate HttpClient calls inside a custom service
* use [mergeMap](https://rxjs.dev/api/operators/mergeMap) or [exhaustMap](https://rxjs.dev/api/operators/exhaustMap) 
  RxJS operators [to pipe several http calls](https://coryrylan.com/blog/angular-multiple-http-requests-with-rxjs)
* use [forkJoin](https://rxjs.dev/api/index/function/forkJoin) RxJS operator to 
  [performs http calls in parallel](https://coryrylan.com/blog/angular-multiple-http-requests-with-rxjs)
* [handling request error](https://angular.io/guide/http-handle-request-errors) can be customized
* [headers](https://angular.io/api/common/http/HttpHeaders) can be [provided to http requests](https://angular.io/guide/http#adding-and-updating-headers)
* [query parameters (HttpParams)](https://angular.io/api/common/http/HttpParams) can be [provided to http requests](https://angular.io/guide/http-send-data-to-server#add-and-updating-headers)
  * use [HttpParams.append](https://angular.io/api/common/http/HttpParams#append) method if you have several query params (HttpParams is immutable)
* [HttpInterceptor](https://angular.io/api/common/http/HttpInterceptor) can be used to implicit features like
  * [set default headers in http requests](https://angular.io/guide/http-interceptor-use-cases#set-default-headers)
  * [caching requests](https://angular.io/guide/http-interceptor-use-cases#cache-requests)
  * interceptors are executed [in the order of their definition in module](https://angular.io/guide/http-intercept-requests-and-responses#interceptor-order)
* authentication concepts
  * server validate credentials and deliver a token (e.g. json like [JWT (JSON Web Tokens)](https://jwt.io/)) to frontend
  * frontend save the token (e.g. localStorage) and sent it to any subsequent authorized requests 
    with e.g. [interceptor](https://angular.io/guide/http-intercept-requests-and-responses)
  * only the server is able to generate the token with a private key and a given algorithm and his therefore secure

[*Go to top*](#Angular)


### Styling

[Styling](https://angular.io/guide/component-styles) of angular applications are made with CSS

* application-wide styles can be done by
  1. add `<link rel="stylesheet" href="...">` into `index.html` with CDN url or local file (should be in assets folder)
  2. update `styles.css` (default global angular style)
  3. modify [global style](https://angular.io/guide/workspace-config#styles-and-scripts-configuration) in `angular.json`
    * typical use-case: `styles` link to a css file of a css framework npm module
* component-scoped styles can be done by
  1. use `styles` or [styleUrls](https://angular.io/api/core/Component#styleurls) of `@Component` decorator
  2. add `<style>` or `<link>` to component template
* [View encapsulation](https://angular.io/guide/view-encapsulation) (or also named style isolation): component styles are applied, by default, 
  only within the template of that component
  * Angular emulate [shadow DOM](https://en.wikipedia.org/wiki/Web_Components#Shadow_DOM) by giving a specific 
    attribute value for every html tags of a component; CSS can be applied then by using this attribute in the 
    CSS selector
  * see [style scope](https://angular.io/guide/view-encapsulation)
* default view encapsulation can be overidden by changing [@Component.encapsulation](https://angular.io/api/core/Component#encapsulation)
* special selectors
  * [:host](https://angular.io/guide/component-styles#host) targets the element which host the component
    * function form `:host` component allow to style the host component on given css selector condition 
      (e.g. `:host(.active)`)
  * [:host-context](https://angular.io/guide/component-styles#host-context) style elements inside a component, depending on some condition set outside of it; it's usefull to apply css theme
  * [::ng-deep](https://angular.io/guide/component-styles#deprecated-deep--and-ng-deep) allow to disable [view-encapsulation](https://angular.io/guide/view-encapsulation) for a given css rule; e.g. allow to style a 
    projected element with [<ng-content>](https://angular.io/api/core/ng-content)
    * `:host ::ng-deep input { ... }`: css rule only applied in the projected input element and not an every input of the page
* Directives [ngClass](https://angular.io/api/common/NgClass) and [ngStyle](https://angular.io/api/common/NgStyle) 
  are a common way to dynamic style components
* Angular component selector like `app-xyz { ... }` can be used in css
* [@import](https://angular.io/guide/component-styles#css-imports) can be used to import css files into css file
* Angular [Renderer2](https://angular.io/api/core/Renderer2) is a service to manipulate elements of your app without
  having to touch the DOM directly

[*Go to top*](#Angular)


### Ahead-of-time (AoT) or Just-in-Time (JiT) compilation

[Ahead-of-time (AoT) or Just-in-Time (JiT) compilation](https://angular.io/guide/aot-compiler) happens at runtime (JiT) or during build (AoT)

* TypeScript compiler compiles TS into JavaScript and is called in the build process
* Angular compiler compile template into JavaScript DOM instructions
* Just-in-Time (JiT) compilation is used normally for `ng serve`
* Ahead-of-time (AoT) compilation is used for `ng build`

[*Go to top*](#Angular)


### Deployment

[Deployment](https://angular.io/guide/deployment) to deploy Angular application on remote server

* [configure application environments](https://angular.io/guide/build#configuring-application-environments)
  in `environment.ts` like API key
  * [use environment variables](https://angular.io/guide/build#using-environment-specific-variables-in-your-app):
   `import { environment } from '../environments/environment';`
  * [build your production configuration](https://angular.io/guide/build#configure-target-specific-file-replacements):
    `ng build --prod` ensure to use `/environment/environment.prod.ts` instead of `/environment/environment.ts`
* hints
  * [deploy to GitHub pages with --base-href](https://angular.io/guide/deployment#deploy-to-github-pages)
  * it's important to make sure that your server is configured to 
    [always serve the index.html](https://angular.io/guide/deployment#routed-apps-must-fall-back-to-indexhtml) file (and not returning 404)

[*Go to top*](#Angular)


*Page mainly written in 2019, last update: february 2022; links checked on 04.03.2024*
