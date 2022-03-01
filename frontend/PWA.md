# Progressive Web App

[Progressive Web App (PWA)](https://developers.google.com/web/progressive-web-apps/) is web application that work like desktop application (fast, installable, with offline capabilities) based on [offline first](https://offlinefirst.org/) design 

* PWA is a bundle of technologies
  * [Web app Manifests](#Application-Manifest) make web application installable
  * [Service Workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API) to proxy backend requests
  * **Push Notifications** is used to notify the device/browser even when the   application is loaded using WebAPIs [Push API](https://developer.mozilla.org/en-US/docs/Web/API/Push_API) in conjunction with
      [Notification API](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API) and a running
      [Service Worker](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API);
    see [MDN guide](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API/Using_the_Notifications_API)
    * backend need also library to able to push notifications; e.g [web-push](https://github.com/web-push-libs/web-push) for NodeJS
  * [Background Synchronization API](https://developer.mozilla.org/en-US/docs/Web/API/Background_Synchronization_API) to defer tasks to be   run in a service worker until the user has a stable network connection.
  * Responsive Design (TODO add link to CSS summary)
  * [Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API) to access user location
  * Media API to access device camera and microphone >>> TODO add correct link later
* tools
  * [Lighthouse](https://developers.google.com/web/tools/lighthouse/) 
    Chrome DevTools to audit for performance, accessibility, PWA, SEO of websites
  * [android studio](https://developer.android.com/studio) 
    to test PWA on emulated device
* courses
  * [Progressive Web Apps (PWA) - The Complete Guide](https://www.udemy.com/course/progressive-web-app-pwa-the-complete-guide/)
  * [Angular Progressive Web Apps (PWA) MasterClass](https://www.udemy.com/course/angular-pwa-course/)
  * [The complete guide to angular](https://www.udemy.com/the-complete-guide-to-angular-2/) include a module about Service Workers

[*Go to parent page*](../README.md)

*(Page mainly written in 2019, last update: february 2022)*

## Application Manifest

[Web app Manifests](https://developer.mozilla.org/en-US/docs/Web/Manifest) to provide web app as downloaded native application on a homescreen of a device (require running service worker)

* [Web App Manifest Explanation by Google](https://web.dev/add-manifest/)
* [How to provide your own in-app install experience](https://web.dev/customize-install/) to check pre-requisites required to get browser prompt to install the application
* [Can I use](https://caniuse.com/) for [Add to home screen](https://caniuse.com/web-app-manifest)

Important manifest properties:
* [name](https://developer.mozilla.org/en-US/docs/Web/Manifest/name): 
  long name of the web application
* [short_name](https://developer.mozilla.org/en-US/docs/Web/Manifest/short_name): 
  short name of the web application; e.g. displayed on phone home screen
* [start_url](https://developer.mozilla.org/en-US/docs/Web/Manifest/start_url): 
  start URL of the web application (could be overwridden)
* [scope](https://developer.mozilla.org/en-US/docs/Web/Manifest/scope):
  restricts which web pages are displayed inside PWA context. If the user navigates outside the scope, it reverts to a normal web page inside a browser tab or window
* [display](https://developer.mozilla.org/en-US/docs/Web/Manifest/display):
  specify how much of browser UI is shown to the user; e.g. use `standalone` to make web app like native application
* [background_color](https://developer.mozilla.org/en-US/docs/Web/Manifest/background_color):
  background color while loading and an splashscreen
* [theme_color](https://developer.mozilla.org/en-US/docs/Web/Manifest/theme_color):
  define theme color used for several ui elements
* [lang](https://developer.mozilla.org/en-US/docs/Web/Manifest/lang):
  specifies the primary language
* [orientation](https://developer.mozilla.org/en-US/docs/Web/Manifest/orientation):
  defines the default screen orientation
  * tip: it's better to support both portrait /landscape orientation instead of restrict users
* [icons](https://developer.mozilla.org/en-US/docs/Web/Manifest/icons):
  defines icons that can be used for different context; e.g. on homescreen
* [related_applications](https://developer.mozilla.org/en-US/docs/Web/Manifest/related_applications):
  native applications that user can install as alternative to web application
* ([description](https://developer.mozilla.org/en-US/docs/Web/Manifest/description):
  explain what the application does; e.g. display in browser favorites)

[*Go to top*](#Progressive-Web-App)


### App Manifest alternative for Safari

Safari does not yet App Manifest but meta tags can be used as alternatives.

* `<meta name="apple-mobile-web-app-capable" content="yes">`: enable web application as mobile web application
* `<meta name="apple-mobile-web-app-status-bar-style" content="black">`: somewhat equivalent to [theme_color](https://developer.mozilla.org/en-US/docs/Web/Manifest/theme_color)
* `<meta name="apple-mobile-web-app-title" content="Applicatin name">`: equivalent to [short_name](https://developer.mozilla.org/en-US/docs/Web/Manifest/short_name)
* `<link rel="apple-touch-icon" href="..." size="..x..">`: define the used icon for homescreen like [icons](https://developer.mozilla.org/en-US/docs/Web/Manifest/icons)

Links:
* [Safari supported Meta Tags](https://developer.apple.com/library/archive/documentation/AppleApplications/Reference/SafariHTMLRef/Articles/MetaTags.html)
* [Don’t use iOS meta tags irresponsibly in your Progressive Web Apps](https://firt.dev/ios-meta/)

[*Go to top*](#Progressive-Web-App)


## Service Workers

* Service workers essentially act as proxy servers that sit between web applications, the browser, and the network (when available).
* see [guide](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API/Using_Service_Workers)
* [Web workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers) are executed in another Thread (in background; perform tasks without interfering with the user interface)
* [Service Workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API) are a special types of Web workers
* Offline can be simulated in chrome in devtools > Application > Service Workers > select "Offline"
* JavaScript's application run in a single Thread
* Service workers are decoupled from webpage
* use of [skipWaiting()](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/skipWaiting) and [Clients.claim()](https://developer.mozilla.org/en-US/docs/Web/API/Clients/claim#example) allow to use an activated service worker on clients (tabs) without having to reload the page (could produce subtitle bugs, e.g. with versioning compatiblity of the page)
* [ServiceWorkerRegistration.update()](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/update) attemps to update new version of a service worker (e.g. could be trigger regularly with [setInterval()](https://developer.mozilla.org/en-US/docs/Web/API/setInterval) every minute)
* [Cache](https://developer.mozilla.org/en-US/docs/Web/API/Cache) to provide a cache of HTTP requests/responses (e.g. for offline capability with service workers)

[*Go to top*](#Progressive-Web-App)


## Caching Assets with Service Workers

TODO

[*Go to top*](#Progressive-Web-App)


## Caching Dynamic data with IndexedDB

TODO

[*Go to top*](#Progressive-Web-App)

## Background Sync

TODO

[*Go to top*](#Progressive-Web-App)

## Web Push Notifications

TODO

[*Go to top*](#Progressive-Web-App)

## Media API

TODO

[*Go to top*](#Progressive-Web-App)

## Geolocation

TODO

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
