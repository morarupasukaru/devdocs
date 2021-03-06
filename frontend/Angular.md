# Angular

[Angular](https://angular.io/) is a [TypeScript](TypeScript.md) framework to build 
[Single-page applications](https://en.wikipedia.org/wiki/Single-page_application) (SPA).

* [Angular concepts](https://angular.io/guide/architecture)
  * [Angular CLI](#Angular-CLI) is a command-line tool to create project, components, deploy application 
     locally, etc.
  * [@NgModule](#NgModule) bundle a set of components together
  * [@Component](#Component) is a decorator used to identify a class as a component
  * [Templates](https://angular.io/guide/template-syntax) in Angular represent the view written in HTML with 
    additional features like dynamic changes
  * [Directives](#Directives) allow to add features to elements in the DOM
  * [Data bindings](#Data-bindings) ease [components interaction](https://angular.io/guide/component-interaction#component-interaction) 
    in different use cases
  * [Services](#Services) are normally classes and provide some feature
  * [Routing](#Routing) define navigation of screens / components and associated url
* Other features
  * [Forms](#Forms) can be written in two different ways in Angular:
    [reactive](#reactive-forms) or [template-driven](#template-driven-forms) approach
  * [Observables](#Observables) provided by [RxJS](./RxJS.md) 
    is used extensively within Angular to ease writing of asynchronous calls and event handling
  * [Pipes](#Pipes) are used to transform output into templates
  * [HttpClient](#HttpClient) provide an API to perform HTTP requests
  * [Styling](#Styling) of angular applications are made with CSS
  * [Animations](#Animations) provided by Angular is based on CSS features but provide a specific DSL language
  * [Dynamic Components](#Dynamic-Components) allow to load new components at runtime
  * [Ahead-of-time (AoT) or Just-in-Time (JiT) compilation](#ahead-of-time-aot-or-just-in-time-jit-compilation) happens at runtime (JiT) or during build (AoT)
  * [Deployment](#Deployment) to deploy Angular application on remote server
  * [Testing](#Testing) to write and run unit tests
  * [Angular Elements](https://angular.io/guide/elements) turn Angular Components as [Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components)
  * [Service Workers & PWA](#service-workers--pwa) provide a way to have offline web applications
    and are used to make a [Progressive Web App (PWA)](https://developers.google.com/web/progressive-web-apps/)
  * [Angular Universal](#Angular-Universal) provide
    [Server-side Rendering](https://developers.google.com/web/updates/2019/02/rendering-on-the-web)
    (pre-render web-pages on the server on the fly) with [ExpressJS](https://expressjs.com/) 
    (a web framework for [Node.js](https://nodejs.org/en/))
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
  * [NgRx and Redux](#NgRx-and-Redux) are used to manage application state
  * [Angular Flex-Layout](#Angular-Flex-Layout) provide layout API using 
    [Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
    and [mediaQuery](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)
  * [Angular Material](#Angular-Material) is an Angular components suite based on 
    [Google Material Design specifications](https://material.io/design/)
  * [AngularFire](https://github.com/angular/angularfire) is an Angular connector library to 
    [Firebase](https://firebase.google.com/) (Backend-as-a-Service (BaaS); no service-side code required)
  * [NestJS](#NestJS) is a web framework for [Node.js](https://nodejs.org/en/) and can used in 
    [Angular Universal](#Angular-Universal) instead of 
    [ExpressJS](https://expressjs.com/) to provide
    [Server-side Rendering](https://developers.google.com/web/updates/2019/02/rendering-on-the-web)

[*Go to parent page*](../README.md)

*(Page mainly written in 2019, last update: july 2020)*


## Angular concepts

#### Angular CLI

[Angular CLI](https://cli.angular.io/) is a command-line tool to create project, components, deploy application 
locally, etc.
* [installation](https://angular.io/cli#installing-angular-cli) of Angular CLI
* [how-to create project and deploy app locally](https://angular.io/cli#basic-workflow)
* see [Issue](https://github.com/angular/angular-cli/issues/9160) and [Skipping Tests In Angular CLI](https://tutorialsforangular.com/2019/12/31/skipping-tests-in-angular-cli/) to create a Angular project without testing
[*Go to top*](#Angular)


#### @NgModule

[@NgModule](https://angular.io/guide/architecture#modules) bundle a set of components together

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

[*Go to top*](#Angular)


#### @Component

[@Component](https://angular.io/guide/architecture#components) is a decorator used to identify a class as a component

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


#### Directives

[Directives](https://angular.io/guide/built-in-directives) allow to add features to elements in the DOM

* [types of directives](https://angular.io/guide/attribute-directives#directives-overview): 
  [structural](https://angular.io/guide/structural-directives) and 
  [attribute](https://angular.io/guide/attribute-directives) directives
* built-in structural directives: 
  [ngIf](https://angular.io/api/common/NgIf), 
  [ngStyle](https://angular.io/api/common/NgStyle), 
  [ngClass](https://angular.io/api/common/NgClass), 
  [ngFor](https://angular.io/api/common/NgForOf), 
  [ngSwitch](https://angular.io/guide/structural-directives#inside-ngswitch-directives)
* tips: 
  * [ng-if else](https://angular.io/api/common/NgIf#showing-an-alternative-template-using-else); 
    alternative is to write two ngIf
  * [getting index of ng-for](https://angular.io/api/common/NgForOf#description)
  * [AngularJS ngShow](https://docs.angularjs.org/api/ng/directive/ngShow) can be simulated in Angular by using 
    property binding `[hidden]="condition"` on 
    [hidden](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/hidden) html attribute
* see explanation of [`*` structural directive's prefix](https://angular.io/guide/structural-directives#asterisk) 
* [build custom attribute directive](https://angular.io/guide/attribute-directives#build-a-simple-attribute-directive)
  * by using [Renderer2](https://angular.io/api/core/Renderer2)
  * [@HostListener](https://angular.io/api/core/HostListener) to listen host event
  * [@HostBinding](https://angular.io/api/core/HostBinding) to bind host properties
  * [@Input to pass values to directive](https://angular.io/guide/attribute-directives#pass-values-into-the-directive-with-an-input-data-binding)
  * [Use alias to avoid extra attribute](https://angular.io/guide/attribute-directives#bind-to-an-input-alias)
* [build custom structural directive](https://angular.io/guide/structural-directives#write-a-structural-directive)

[*Go to top*](#Angular)


#### Data bindings

Data bindings ease [components interaction](https://angular.io/guide/component-interaction#component-interaction) 
in different use cases

* [String interpolation](https://angular.io/guide/interpolation): `{{ data }}` (one-way binding from controller to view)
* [Property binding](https://angular.io/guide/property-binding): `[property]="data"` (one-way binding from controller to view)
* [Event binding](https://angular.io/guide/event-binding): `(event)="expression"` (one-way binding from view to controller)
* [Two-way binding](https://angular.io/guide/two-way-binding): `[(property)]="data"` (two-way binding between view and controller)
  (two-way binding is a syntactic sugar for a property binding and an event binding)
* [ngModel](https://angular.io/guide/built-in-directives#ngModel) directive allow two-way binding for form's inputs 
* custom property and event bindings
  * Binding custom properties with [@Input](https://angular.io/api/core/Input#usage-notes)
  * Binding custom events with [@Output](https://angular.io/guide/inputs-outputs#configuring-the-child-component-1)
  * use [Alias on @Input/@Output](https://angular.io/guide/attribute-directives#bind-to-an-input-alias) to have 
    different public name than class property
  * Components communication with @Input & @Output is good if component are not far for themselves (e.g. parent-child)
* a [template reference variable](https://angular.io/guide/template-reference-variables) is a reference to a 
  DOM element available within in template (could replace bindings with custom properties)
* [@ViewChild](https://angular.io/guide/component-interaction#parent-calls-an-viewchild) allow to access template 
  reference element as [ElementRef](https://angular.io/api/core/ElementRef) in controller
  (e.g. input field value readable with ElementRef.nativeElement.value)
* ng-content allow to project content into a reusable component (e.g. tabs component)
  * see following [article](https://medium.com/claritydesignsystem/ng-content-the-hidden-docs-96a29d70d11b) 
    (ng-content is officially not documented; [issue](https://github.com/angular/angular/issues/17983))
  * [@ContentChild](https://angular.io/api/core/ContentChild) allow to access reference of the ng-content element 
    as [ElementRef](https://angular.io/api/core/ElementRef) from injected component ts file
* [ng-container](https://angular.io/guide/structural-directives#ng-container-to-the-rescue) is a grouping element 
  that doesn't interfere with styles or layout because Angular doesn't put it in the DOM
* [lifecycle hooks](https://angular.io/guide/lifecycle-hooks#lifecycle-hooks)
  * [@ViewChild](https://angular.io/api/core/ViewChild) properties are available on
    [ngAfterViewInit](https://angular.io/api/core/AfterViewInit#ngafterviewinit)
  * [@ContentChild](https://angular.io/api/core/ContentChild) properties are available on 
    [ngAfterContentInit](https://angular.io/api/core/AfterContentInit#ngaftercontentinit)
  * see article [Everything you need to know about the `ExpressionChangedAfterItHasBeenCheckedError` error](https://indepth.dev/everything-you-need-to-know-about-the-expressionchangedafterithasbeencheckederror-error/), [page 2](https://indepth.dev/everything-you-need-to-know-about-the-expressionchangedafterithasbeencheckederror-error/)

[*Go to top*](#Angular)


#### Services

[Services](https://angular.io/guide/architecture-services) are normally classes and provide some feature

* services ease [cross-component communication](https://angular.io/guide/component-interaction#parent-and-children-communicate-via-a-service) 
  by using [EventEmitter](https://angular.io/api/core/EventEmitter) or RxJS
* dependency-injection of services can by done with 
  [@Injectable](https://angular.io/guide/hierarchical-dependency-injection#moduleinjector) decorator on the service itself
  in [@NgModule.providers](https://angular.io/guide/hierarchical-dependency-injection#moduleinjector) or 
  [@Component.providers](https://angular.io/guide/hierarchical-dependency-injection#component-level-injectors)
* [hierarchical injector](https://angular.io/guide/hierarchical-dependency-injection) : instance of service provided to 
  a given Module/Component will be provided to childs
  (means that several instance of a service could exist in the application; depending on the DI configuration)
* a [singleton service](https://angular.io/guide/singleton-services) has to be provided at root level
* [@Injectable](https://angular.io/api/core/Injectable) decorator is required on the target service to 
  [inject services into services](https://angular.io/guide/dependency-injection#using-services-in-other-services)

[*Go to top*](#Angular)


#### Routing

[Routing](https://angular.io/guide/router) define navigation of screens / components and associated url

* [configure router and Routes](https://angular.io/guide/router#configuration) in app.module.ts
  * [add `<router-outlet>` in template](https://angular.io/guide/router#router-outlet) where routed components will be rendered
  * [configure route parameters (e.g. id)](https://angular.io/guide/router-tutorial-toh#route-parameters)
  * [redirects and wildcard routes](https://angular.io/guide/router#setting-up-redirects) can also be configured
  * a good practise is to have a [separate module for route configuration](https://angular.io/guide/router-tutorial-toh#milestone-2-routing-module)
* define navigation in templates with [routerLink](https://angular.io/api/router/RouterLink) directive and 
  following [properties](https://angular.io/api/router/RouterLink#description): queryParams, fragment
  * add CSS class in template with [routeLinkActive](https://angular.io/guide/router#active-router-links) 
  (see also routerLinkActiveOptions)
* navigate programmatically with [Router.navigate](https://angular.io/api/router/Router#navigate)(paths: any[], extras: 
  [NavigationExtras](https://angular.io/api/router/NavigationExtras))
  * [NavigationExtras](https://angular.io/api/router/NavigationExtras) is used to pass 
    [queryParams](https://angular.io/api/router/UrlCreationOptions#queryParams), 
    [fragment](https://angular.io/api/router/UrlCreationOptions#fragment), 
    [relative route](https://angular.io/api/router/UrlCreationOptions#relativeTo) 
    (e.g. [ActivatedRoute](https://angular.io/api/router/ActivatedRouteSnapshot))
  * tip: use [router.navigate(..., { queryParamsHandling: ...})](https://angular.io/api/router/UrlCreationOptions#queryParamsHandling) 
    to preserve query params when navigating between routes
* retrieve route datas in ngOnInit with 
  [ActivatedRoute](https://angular.io/api/router/ActivatedRoute).[snapshot](https://angular.io/api/router/ActivatedRoute#snapshot)() 
  that returns an [ActivatedRouteSnapshot](https://angular.io/api/router/ActivatedRouteSnapshot) 
  (containing params, queryParams, etc.)
* retrieve route datas on every route changes within the component by calling 
  ["subscribe()"](https://angular.io/guide/observables-in-angular#router) with observables of 
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
* [provide/pre-fetch dynamic data to component](https://angular.io/guide/router-tutorial-toh#resolve-pre-fetching-component-data)
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

#### Forms

[Forms](https://angular.io/guide/forms-overview#key-differences) can be written in two different ways in Angular:
[reactive](https://angular.io/guide/reactive-forms) or [template-driven](https://angular.io/guide/forms) approach


##### Template-driven forms

[Template-driven forms](https://angular.io/guide/forms): Angular infers the Form Object ([FormGroup](https://angular.io/api/forms/FormGroup)) from the DOM

* import [FormsModule](https://angular.io/api/forms/FormsModule)
* (Angular automatically add an [ngForm](https://angular.io/api/forms/NgForm) directive to the `<form>`)
* add [ngModule](https://angular.io/api/forms/NgModel) directive on `<input>`
* add [ngSubmit](https://angular.io/api/forms/FormGroupDirective#properties) event emitter on `<form>`
* add a [template reference variable `<form #f="ngForm">`](https://angular.io/guide/forms#submit-the-form-with-ngsubmit) 
  to access the FormGroup / form state inside the template
* add a [ViewChild](https://angular.io/api/core/ViewChild) annotation to access the template reference variable 
  of the NgForm inside controller:
  ```
    @ViewChild('f', { static: false }) signupForm: NgForm;
  ```
* add [built-in validators](https://angular.io/api/forms/Validators) (`required`, `email`, etc.) on `<input>`
* add styles or *ngIf by using css classes: `ng-untouched`/`ng-touched`, `ng-pristine`/`ng-dirty`, 
  `ng-valid`/`ng-invalid`, see [Angular docs](https://angular.io/guide/forms#create-visual-feedback-for-states)
* custom validator is implemented with [directives](https://angular.io/guide/form-validation#adding-to-template-driven-forms) 
* binding with [ngModel](https://angular.io/api/forms/NgModel) directive:
  * no binding: indicate Angular which input to manage
  * one-way binding: set default value to input, e.g. `<select [ngModel]="defaultQuestion" ...>`
  * two-way binding: variable inside controller instantly updated on user-input
* use [ngModelGroup](https://angular.io/api/forms/NgModelGroup) directive to group several input into a logical group
* call [NgForm.from.patchValue({ key:value })](https://angular.io/api/forms/FormGroup#patchvalue) to override specific form values

[*Go to top*](#Angular)


##### Reactive forms

[Reactive forms](https://angular.io/guide/reactive-forms): Form is created programmatically and synchronised with the DOM

* import [ReactiveFormsModule](https://angular.io/api/forms/ReactiveFormsModule)
* create a [FormGroup](https://angular.io/guide/reactive-forms#grouping-form-controls) inside component controller
* add [[formGroup]="xxxx"](https://angular.io/api/forms/FormGroupDirective) directive to the `<form>` in the template 
  to one-way bind [FormGroup](https://angular.io/api/forms/FormGroup) of the controller to the template
* add [formControlName](https://angular.io/api/forms/FormControlName) directive to `<input>`s in template
* add [(ngSubmit)="xxx()"](https://angular.io/guide/reactive-forms#grouping-form-controls) event emitter to `<form>` in template 
* validation directive does not work (e.g. `required`)
* [Validators](https://angular.io/api/forms/Validators) must be added to the 2nd parameter to 
  [FormControl](https://angular.io/api/forms/FormControl)
* control and form states are available in the template by calling get on bind FormGroup, e.g. 
  `<span *ngIf="!signupForm.get('email').valid && signupForm.get('email').touched">...<span>`
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
* [async validator](https://angular.io/guide/form-validation#implementing-a-custom-async-validator) are used e.g. 
  to validate field on the server
  * async validator return Promise or Observable
  * async validator are added in FormControl third argument
  * ng-pending class is set the FormControl while waiting to the async validator result
* FormGroup, FormControl have two observables [valueChanges and statusChanges](https://angular.io/api/forms/AbstractControl#properties)
* [FormGroup.setValue()](https://angular.io/api/forms/FormGroup#setvalue), 
  [.patchValue()](https://angular.io/api/forms/FormGroup#patchvalue) are also available with Reactive forms
* [FormGroup.reset()](https://angular.io/api/forms/FormGroup#reset) could be called on submit to reset form 
  controls (optional arg allow to set default value; e.g. for radiobuttons)

[*Go to top*](#Angular)


#### Observables

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


#### Pipes

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
```
@Pipe({ name: 'safeUrl' })
export class SafeUrlPipe implements PipeTransform {

  constructor(private sanitizer: DomSanitizer) {  }

  transform(url) {
    return this.sanitizer.bypassSecurityTrustResourceUrl(url);
  }
}
```

[*Go to top*](#Angular)


#### HttpClient

[HttpClient](https://angular.io/guide/http) provide an API to perform HTTP requests

* use HttpClient methods [get()](https://angular.io/api/common/http/HttpClient#get), 
  [post()](https://angular.io/api/common/http/HttpClient#post),
  [put()](https://angular.io/api/common/http/HttpClient#put),
  [delete()](https://angular.io/api/common/http/HttpClient#delete), etc.
* request are sent only by subscribing to the [Observable](https://rxjs.dev/api/index/class/Observable) 
  of http methods'result 
* use pipe and [map](https://rxjs.dev/api/operators/map) from [RxJS](https://rxjs.dev/guide/operators) 
  to convert response to required object
* [response's type](https://angular.io/guide/http#requesting-a-typed-response) can be specified
* good practise: encapsulate HttpClient calls inside a custom service, [see example](https://angular.io/guide/http#requesting-a-typed-response)
* use [mergeMap](https://rxjs.dev/api/operators/mergeMap) or [exhaustMap](https://rxjs.dev/api/operators/exhaustMap) 
  RxJS operators [to pipe several http calls](https://coryrylan.com/blog/angular-multiple-http-requests-with-rxjs)
* use [forkJoin](https://rxjs.dev/api/index/function/forkJoin) RxJS operator to 
  [performs http calls in parallel](https://coryrylan.com/blog/angular-multiple-http-requests-with-rxjs)
* [handling request error](https://angular.io/guide/http#handling-request-errors) can be customized
* [headers](https://angular.io/api/common/http/HttpHeaders) can be [provided to http requests](https://angular.io/guide/http#adding-and-updating-headers)
* [query parameters (HttpParams)](https://angular.io/api/common/http/HttpParams) can be [provided to http requests](https://angular.io/guide/http#configuring-http-url-parameters)
  * use [HttpParams.append](https://angular.io/api/common/http/HttpParams#append) method if you have several query params (HttpParams is immutable)
* [HttpInterceptor](https://angular.io/api/common/http/HttpInterceptor) can be used to implicit features like
  * [set default headers in http requests](https://angular.io/guide/http#setting-default-headers)
  * [caching requests](https://angular.io/guide/http#caching)
  * interceptors are executed [in the order of their definition in module](https://angular.io/guide/http#interceptor-order)
* authentication concepts
  * server validate credentials and deliver a token (e.g. json like [JWT (JSON Web Tokens)](https://jwt.io/)) to frontend
  * frontend save the token (e.g. localStorage) and sent it to any subsequent authorized requests 
    with e.g. [interceptor](https://angular.io/guide/http#intercepting-requests-and-responses)
  * only the server is able to generate the token with a private key and a given algorithm and his therefore secure

[*Go to top*](#Angular)


#### Styling

[Styling](https://angular.io/guide/component-styles) of angular applications are made with CSS

* application-wide styles can be done by
  1. add `<link rel="stylesheet" href="...">` into `index.html` with CDN url or local file (should be in assets folder)
  2. update `styles.css` (default global angular style)
  3. modify [global style](https://angular.io/guide/workspace-config#styles-and-scripts-configuration) in `angular.json`
    * typical use-case: `styles` link to a css file of a css framework npm module
* component-scoped styles can be done by
  1. use `styles` or [styleUrls](https://angular.io/api/core/Component#styleurls) of `@Component` decorator
  2. add `<style>` or `<link>` to component template
* [View encapsulation](https://angular.io/guide/view-encapsulation): component styles are applied, by default, 
  only within the template of that component
  * Angular emulate [shadow DOM](https://en.wikipedia.org/wiki/Web_Components#Shadow_DOM) by giving a specific 
    attribute value for every html tags of a component; CSS can be applied then by using this attribute in the 
    CSS selector
  * see [style scope](https://angular.io/guide/component-styles#style-scope)
* default view encapsulation can be overidden by changing [@Component.encapsulation](https://angular.io/api/core/Component#encapsulation)
* special selectors
  * [:host](https://angular.io/guide/component-styles#host) targets the element which host the component
    * function form `:host` component allow to style the host component on given css selector condition 
      (e.g. `:host(.active)`)
  * [:hostcontext](https://angular.io/guide/component-styles#host-context) style elements inside a component, 
    depending on some condition set outside of it
* Directives [ngClass](https://angular.io/api/common/NgClass) and [ngStyle](https://angular.io/api/common/NgStyle) 
  are common way to dynamic style components
* Angular component selector like `app-xyz { ... }` can be used in css
* [@import](https://angular.io/guide/component-styles#css-imports) can be used to import css files into css file
* Angular [Renderer2](https://angular.io/api/core/Renderer2) is a service to manipulate elements of your app without
  having to touch the DOM directly

[*Go to top*](#Angular)


#### Animations

[Animations](https://angular.io/guide/animations) provided by Angular is based on CSS features but provide a specific DSL language

* CSS Transitions/CSS Animations vs Angular Animations
  * allow to style an animation on one step; to keep all the stuff in angular world
  * angular animation allow to animate element added on the fly in the DOM (e.g. with *ngIf); its very difficult to manage it with CSS Animations
  * complex animation should be done in Angular Animations
  * infinite animation should be done with CSS Transitions/CSS Animations (not well done in Angular Animations)
* concepts
  * [trigger](https://angular.io/guide/animations#triggering-the-animation) encapsulates a named animation; the transitions between states included in its definition when a change occurs
  * [state](https://angular.io/guide/animations#animation-state-and-styles) define styles related to a given named state
  * [transition](https://angular.io/guide/animations#transitions-and-timing) define animation between styles of state
* see [animatable CSS properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) (evolves over time)
* advanced topics
  * [animations transitions and triggers](https://angular.io/guide/transition-and-triggers)
    * [wildcard state (*)](https://angular.io/guide/transition-and-triggers#wildcard-state) means any state
    * [void state](https://angular.io/guide/transition-and-triggers#void-state) means state when element is not in the DOM
    * [:enter and :leave aliases](https://angular.io/guide/transition-and-triggers#enter-and-leave-aliases) for `void => *` and `* => void` transitions
    * [use wildcards with styles](https://angular.io/guide/transition-and-triggers#using-wildcards-with-styles) to use current style value
  * use [animation callbacks](https://angular.io/guide/transition-and-triggers#animation-callbacks) to be informed when animation start/end
  * [complex animation sequences](https://angular.io/guide/complex-animation-sequences) with 
    [query()](https://angular.io/guide/complex-animation-sequences#animate-multiple-elements-using-query-and-stagger-functions) 
    allow to find and animate inner elements; see also [query](https://angular.io/api/animations/query) in reference
  * [route transition animations](https://angular.io/guide/route-animations)
  * [AnimationBuilder](https://angular.io/api/animations/AnimationBuilder) allow to produce animation programmatically
* tip: animations works on block element but per default Angular Component are inline-block element. 
  Don't forget to add:
  ```
  :host {
    display: block;
  }
  ```

[*Go to top*](#Angular)


#### Dynamic Components

[Dynamic Components](https://angular.io/guide/dynamic-component-loader) allow to load new components at runtime

* dynamic components can be achieve with [ngIf](https://angular.io/api/common/NgIf) in templates or 
  by loading component programmatically and pushing into view
* ngIf approach is easier and is the best solution in most cases
* loading component programmatically could be used in some specific use cases (e.g. custom framework)

[*Go to top*](#Angular)


#### Ahead-of-time (AoT) or Just-in-Time (JiT) compilation

[Ahead-of-time (AoT) or Just-in-Time (JiT) compilation](https://angular.io/guide/aot-compiler) happens at runtime (JiT) or during build (AoT)

* TypeScript compiler compiles TS into JavaScript and is called in the build process
* Angular compiler compile template into JavaScript DOM instructions
* Just-in-Time (JiT) compilation is used normally for `ng serve`
* Ahead-of-time (AoT) compilation is used for `ng build`

[*Go to top*](#Angular)


#### Deployment

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
    [always serve the index.html](https://angular.io/guide/deployment#routed-apps-must-fallback-to-indexhtml) file (and not returning 404)

[*Go to top*](#Angular)


#### Testing

[Testing](https://angular.io/guide/testing) to write and run unit tests

* isolated tests: [Jasmine](https://jasmine.github.io/) unit test without angular bundle
  * [testing services](https://angular.io/guide/testing-services#testing-services)
  * [testing pipes](https://angular.io/guide/testing-pipes)
* non isolated tests: unit test with [TestBed](https://angular.io/guide/testing-services#angular-testbed)
  to have angular dependency injection
  * e.g. [testing component DOM](https://angular.io/guide/testing-components-basics#component-dom-testing)
* hints:
  * [fixture.detectChanges()](https://angular.io/guide/testing-components-scenarios#detectchanges) call is required to perform data binding
  * [spy](https://angular.io/guide/testing-components-scenarios#testing-with-a-spy) can be used to mock remote servers
  * testing asynchronous code
    * [async](https://angular.io/guide/testing-components-scenarios#component-with-async-service) and whenStable() methods are used to test asynchronous code;
    * [whenStable()](https://angular.io/guide/testing-components-scenarios#whenstable) is used to wait that all asynchronous code are finished
    * [fakeAsync](https://angular.io/guide/testing-components-scenarios#async-test-with-fakeasync) and tick methods are an alternative to async
    * [tick](https://angular.io/guide/testing-components-scenarios#the-tick-function) method is then used to say "finish all asynchronous tasks"

[*Go to top*](#Angular)


#### Service Workers & PWA

[Service Workers & PWA](https://angular.io/guide/service-worker-intro) provide a way to have offline web applications
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

[*Go to top*](#Angular)


#### Angular Universal

[Angular Universal](https://angular.io/guide/universal) provide 
[Server-side Rendering](https://developers.google.com/web/updates/2019/02/rendering-on-the-web)
(pre-render web-pages on the server on the fly) with [ExpressJS](https://expressjs.com/) (a web framework for [Node.js](https://nodejs.org/en/))

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

[*Go to top*](#Angular)


## Ecosystem

#### NgRx and Redux

[NgRx](https://ngrx.io/) and [Redux](https://redux.js.org/) used to manage application state

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

[*Go to top*](#Angular)


#### Angular Flex-Layout

[Angular Flex-Layout](https://github.com/angular/flex-layout/wiki/API-Documentation) provide layout API using 
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

[*Go to top*](#Angular)


#### Angular Material

[Angular Material](https://material.angular.io/) is an Angular components suite based on 
[Google Material Design specifications](https://material.io/design/)

* [Getting Started with Angular Material](https://material.angular.io/guide/getting-started)
* Angular Material is based on two packages:
  * [component dev kit](https://material.angular.io/cdk/categories)(CDK) to develop a component suite (@angular/cdk)
  * [component suite](https://material.angular.io/components/categories) based on Material Design (@angular/material)
* see list of [Material Icons](https://material.io/resources/icons/?style=baseline)
* Angular Material provide no grid system; 
  use [Angular Flex-Layout](https://github.com/angular/flex-layout/wiki/API-Documentation)

[*Go to top*](#Angular)


#### NestJS

[NestJS](https://nestjs.com/) is a web framework for [Node.js](https://nodejs.org/en/) and can used in 
[Angular Universal](#Angular-Universal) instead of 
[ExpressJS](https://expressjs.com/) to provide
[Server-side Rendering](https://developers.google.com/web/updates/2019/02/rendering-on-the-web)

* Angular Universal with NestJS vs Angular Universal with ExpressJS:
  * default Angular Universal only pre-render HTML webpage
  * NestJS allow to build REST APIs
  * NestJS is a server-side framework that borrow a lot from Angular and use TypeScript
  * Angular + NestJS is a full-stack
* use [nestjs/ng-universal](https://github.com/nestjs/ng-universal) to integrate NestJS to Angular Universal 
* see [NestJS docs](https://docs.nestjs.com/) 

[*Go to top*](#Angular)
