# Progressive Web App

[Progressive Web App (PWA)](https://developers.google.com/web/progressive-web-apps/) is web application that work like desktop application (fast, installable, with offline capabilities) based on [offline first](https://offlinefirst.org/) design and depends on ...
* [Service Workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API) to proxy backend requests
* [Web app Manifests](https://developer.mozilla.org/en-US/docs/Web/Manifest) to provide web app as downloaded native application on a homescreen of a device (require running service worker)
* **Push Notifications** is used to notify the device/browser even when the application is loaded using WebAPIs [Push API](https://developer.mozilla.org/en-US/docs/Web/API/Push_API) in conjunction with
      [Notification API](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API) and a running
      [Service Worker](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API);
  see [MDN guide](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API/Using_the_Notifications_API)
  * backend need also library to able to push notifications; e.g [web-push](https://github.com/web-push-libs/web-push) for NodeJS

[*Go to parent page*](../README.md)

*(Page mainly written in 2019, last update: february 2022)*


## Service Workers

* Service workers essentially act as proxy servers that sit between web applications, the browser, and the network (when available).
* [Web workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers) are executed in another Thread (in background; perform tasks without interfering with the user interface)
* [Service Workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API) are a special types of Web workers
* Offline can be simulated in chrome in devtools > Application > Service Workers > select "Offline"
* JavaScript's application run in a single Thread
* Service workers are decoupled from webpage
* use of [skipWaiting()](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/skipWaiting) and [Clients.claim()](https://developer.mozilla.org/en-US/docs/Web/API/Clients/claim#example) allow to use an activated service worker on clients (tabs) without having to reload the page (could produce subtitle bugs, e.g. with versioning compatiblity of the page)
* [ServiceWorkerRegistration.update()](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/update) attemps to update new version of a service worker (e.g. could be trigger regularly with [setInterval()](https://developer.mozilla.org/en-US/docs/Web/API/setInterval) every minute)
* [Cache](https://developer.mozilla.org/en-US/docs/Web/API/Cache) to provide a cache of HTTP requests/responses (e.g. for offline capability with service workers)

[*Go to top*](#Progressive-Web-App)


## PWA with Angular


* [Service Workers](https://angular.io/guide/service-worker-intro)
  * [Create a Progressive Web App with the Angular CLI](https://web.dev/creating-pwa-with-angular-cli/):
    * Configure Service Workers in an Angular project: `ng add @angular/pwa`
    * Angular/PWA generate a service worker based on the `ngsw-config.json`
    * we can specify in `ngsw-config.json`
      * which files or urls should be prefetch by the generated service worker
      * caches to be used for rest APIs
      * service-worker can be configured to fetch data from the network and use cache data in case of timeout; see [strategy of cacheconfig](https://angular.io/guide/service-worker-config#strategy)
    * to disable quick service worker on production; set `serviceWorker` to false in `angular-cli.json` and serve a new version of the application in production (user still have to load the application twice)
  * use [SwUpdate](https://angular.io/api/service-worker/SwUpdate#swupdate) service to [detect and install new version of the application](https://angular.io/guide/service-worker-communications#swupdate-service)
* [Application Shell](https://angular.io/guide/app-shell) to display an initial static page while the application is loaded
  * Angular application is pre-rendered with [Angular Universal](https://angular.io/guide/universal) under the hood but without having a running Angular Universal server.
* [Push Notifications](https://angular.io/guide/service-worker-notifications) with 
  [SwPush](https://angular.io/api/service-worker/SwPush#usage-notes) service


[*Go to top*](#Progressive-Web-App)


##  Courses
* [Progressive Web Apps (PWA) - The Complete Guide](https://www.udemy.com/course/progressive-web-app-pwa-the-complete-guide/)
* [Angular Progressive Web Apps (PWA) MasterClass](https://www.udemy.com/course/angular-pwa-course/)
* [The complete guide to angular](https://www.udemy.com/the-complete-guide-to-angular-2/) include a module about Service Workers

[*Go to top*](#Progressive-Web-App)
