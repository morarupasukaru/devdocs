# Angular

[Angular](https://angular.dev/) is a [TypeScript](TypeScript.md) framework to build 
[single-page applications](https://en.wikipedia.org/wiki/Single-page_application) (SPA).

* [tutorials](https://angular.dev/tutorials)
* [main concepts](https://angular.dev/essentials) : components, signals, templates, dependency injection
* in-depth guides:
  [signals](https://angular.dev/guide/signals),
  [components](https://angular.dev/guide/components),
  [templates](https://angular.dev/guide/templates),
  [directives](https://angular.dev/guide/directives),
  [dependency injection / services](https://angular.dev/guide/di),
  [routing](https://angular.dev/guide/routing),
  [forms](https://angular.dev/guide/forms),
  [HTTP client](https://angular.dev/guide/http),
  [server-side & hybrid rendering](https://angular.dev/guide/performance),
  [testing](https://angular.dev/guide/testing),
  [internationalization](https://angular.dev/guide/i18n),
  [animations](https://angular.dev/guide/animations),
  [drag'n drop](https://angular.dev/guide/drag-drop)
* devtools:
  [angular cli](https://angular.dev/tools/cli),
  [how to use & create libraries](https://angular.dev/tools/libraries),
  [browser devtools extension](https://angular.dev/tools/devtools)
* best-practises:
  [angular coding style guide](https://angular.dev/style-guide),
  [security](https://angular.dev/best-practices/security),
  [accessibility](https://angular.dev/best-practices/a11y),
  [error handling](https://angular.dev/best-practices/error-handling),
  [performance](https://angular.dev/best-practices/runtime-performance)
* ecosystem
  * [RxJS interop with Angular signals](https://angular.dev/ecosystem/rxjs-interop); see also [RxJS](RxJS.md) for reactive programming using observables that makes it easier to compose asynchronous 
    or callback-based code
  * [service workers & PWA](https://angular.dev/ecosystem/service-workers) for basic caching utility for simple offline support; see also [Progressive Web App](PWA.md)
  * [web workers](https://angular.dev/ecosystem/web-workers) for background processing
  * [tailwind css with Angular](https://angular.dev/guide/tailwind); [Tailwind CSS](https://tailwindcss.com/) is a utility-first CSS framework
  * [Angular Material](https://material.angular.io/) for components suite based on [Material Design](https://m3.material.io/)
  * TODO
  * [NgRx](https://github.com/morarupasukaru/devdocs/blob/main/minor-topics/NgRx.md) used to manage application state
  * [NestJS](https://nestjs.com/) is a full-stack angular web framework for [server-side](https://web.dev/articles/rendering-on-the-web)
    applications with [Node.js](https://nodejs.org/en/)
  * [TypeScript](TypeScript.md)
* references
  * [angular versions](https://en.wikipedia.org/wiki/Angular_(web_framework)#History): 2 (9.2016) to 20 (05.2025)
  * [angular blog](https://blog.angular.dev/)
  * [angular update guide](https://angular.dev/update-guide#)
  * [error encyclopedia](https://angular.dev/errors)
* courses
  * [The complete guide to angular](https://www.udemy.com/the-complete-guide-to-angular-2/)
  * [Angular material, angularfire & NgRx](https://www.udemy.com/angular-full-app-with-angular-material-angularfire-ngrx/)
  * [Angular styling & animations](https://www.udemy.com/angular-styling-animations-for-angular-2-and-angular-4/)
  * [Angular Testing Masterclass](https://www.udemy.com/course/angular-testing-course/) : nice course containing helpfull explanation about asynchronous testing
  * [Angular Security Masterclass](https://www.udemy.com/course/angular-security/)

[*Go to parent page*](../README.md)

----

## Hints:
* components: [smart vs presentational components](https://blog.angular-university.io/angular-2-smart-components-vs-presentation-components-whats-the-difference-when-to-use-each-and-why/)  
  * *presentational components* are only responsible to display some data from provided @Input and 
    returns modified data through @Output
  * *smart components* are responsible to retrieve/update data from services and pass data to presentational components
  * concepts of smart/presentational components are not specific to Angular but could be applied with 
    every frontend technology
* components: [input](https://angular.dev/guide/components/inputs) and [output](https://angular.dev/guide/components/outputs) for custom events
* components: [@angular/elements](https://angular.dev/guide/elements#) turn angular components as [web components](https://developer.mozilla.org/en-US/docs/Web/Web_Components)
* components: [styling](https://angular.dev/guide/components/styling#)
* templates: [@defer](https://angular.dev/guide/templates/defer) for deferred loading of views
* templates: [pipes](https://angular.dev/guide/templates/pipes) that allows you to transform data declaratively in your template
* AI: [AI prompts](https://angular.dev/ai/develop-with-ai) to help LLMs generate correct code that follows Angular best practices
* internationalization: [ngx-translate](http://www.ngx-translate.com/) as alternative to [angular i18n](https://angular.dev/guide/i18n#)
* performance: [skip change detection](https://angular.dev/best-practices/skipping-subtrees) with [OnPush](https://angular.dev/api/core/ChangeDetectionStrategy#OnPush) strategy instead of default
  * see [Angular OnPush Change Detection and Component Design - Avoid Common Pitfalls](https://blog.angular-university.io/onpush-change-detection-how-it-works/)
* testing:
  * [ng-mocks](https://github.com/help-me-mom/ng-mocks) as alternative to spy
  * [shallow-render](https://github.com/getsaf/shallow-render) as alternative to Angular testing with shallow rendering and easy mocking
* angular cli
  * [deployment](https://angular.dev/tools/cli/deployment)
  * [e2e testing](https://angular.dev/tools/cli/end-to-end)
  * [environment-specific configuration](https://angular.dev/tools/cli/environments#configure-environment-specific-defaults)
* observables?
* [Reactive Async Data with Angular 20 rxResource: Simplified State Management Without RxJS](https://medium.com/@viacheslav.klavdiiev/reactive-async-data-with-angular-20-rxresource-simplified-state-management-without-rxjs-c63fd5533ca4)

[*Go to top*](#Angular)

*Page mainly written in 2019, last update: 09.2025; links checked on 10.09.2025*
