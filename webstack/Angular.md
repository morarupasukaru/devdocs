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
* ecosystem:
    [RxJS interop with angular signals](https://angular.dev/ecosystem/rxjs-interop) ([RxJS](../archive/webstack/RxJS.md)),
    [service workers](https://angular.dev/ecosystem/service-workers) (offline support, [PWA](../archive/webstack/PWA.md)),
    [web workers](https://angular.dev/ecosystem/web-workers) (background processing),
    [tailwind css with angular](https://angular.dev/guide/tailwind) ([tailwind css](https://tailwindcss.com/) is a utility-first CSS framework),
    [angular material](https://material.angular.io/),
    [NgRx](https://github.com/morarupasukaru/devdocs/blob/main/minor-topics/NgRx.md) (reactive state for angular),
    [NestJS](https://nestjs.com/) (full-stack angular web framework)
* references:
  [history](https://en.wikipedia.org/wiki/Angular_(web_framework)#History),
  [blog](https://blog.angular.dev/),
  [update guide](https://angular.dev/update-guide#),
  [error encyclopedia](https://angular.dev/errors),
  [best-practises.md](https://angular.dev/assets/context/best-practices.md)
* courses:
  [the complete guide to angular](https://www.udemy.com/the-complete-guide-to-angular-2/),
  [angular testing masterclass](https://www.udemy.com/course/angular-testing-course/),
  [angular security masterclass](https://www.udemy.com/course/angular-security/),
  [angular signals in depth](https://www.udemy.com/course/angular-signals/)
  
## interesting topics
* components
  * [smart vs presentational components](https://blog.angular-university.io/angular-2-smart-components-vs-presentation-components-whats-the-difference-when-to-use-each-and-why/)  
    * *presentational components* are only responsible to display some data from provided @Input and 
      returns modified data through @Output
    * *smart components* are responsible to retrieve/update data from services and pass data to presentational components
    * concepts of smart/presentational components are not specific to Angular but could be applied with 
      every frontend technology
  * [input](https://angular.dev/guide/components/inputs) and [output](https://angular.dev/guide/components/outputs) for custom events
  * [@angular/elements](https://angular.dev/guide/elements#) turn angular components as [web components](https://developer.mozilla.org/en-US/docs/Web/Web_Components)
  * [styling](https://angular.dev/guide/components/styling#)
* templates
  * [@defer](https://angular.dev/guide/templates/defer) for deferred loading of views
  * [pipes](https://angular.dev/guide/templates/pipes) that allows you to transform data declaratively in your template
* AI: [AI prompts](https://angular.dev/ai/develop-with-ai) to help LLMs generate correct code that follows Angular best practices
* internationalization: [ngx-translate](http://www.ngx-translate.com/) as alternative to [angular i18n](https://angular.dev/guide/i18n#)
* performance: [skip change detection](https://angular.dev/best-practices/skipping-subtrees) with [OnPush](https://angular.dev/api/core/ChangeDetectionStrategy#OnPush) strategy instead of default
  * see [Angular OnPush Change Detection and Component Design - Avoid Common Pitfalls](https://blog.angular-university.io/onpush-change-detection-how-it-works/)
* angular cli
  * [deployment](https://angular.dev/tools/cli/deployment)
  * [e2e testing](https://angular.dev/tools/cli/end-to-end)
  * [environment-specific configuration](https://angular.dev/tools/cli/environments#configure-environment-specific-defaults)
* state management: [Reactive Async Data with Angular 20 rxResource: Simplified State Management Without RxJS](https://medium.com/@viacheslav.klavdiiev/reactive-async-data-with-angular-20-rxresource-simplified-state-management-without-rxjs-c63fd5533ca4)
* use [HttpContext](https://angular.dev/api/common/http/HttpContext#usage-example) to toggle feature in HttpInterceptor
  
[*Go to parent page*](../README.md)

*Page mainly written in 2019, last update: 09.2025; links checked on 10.09.2025*
