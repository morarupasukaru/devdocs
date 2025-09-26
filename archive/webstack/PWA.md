# Progressive Web App

[Progressive Web App (PWA)](https://web.dev/explore/progressive-web-apps) is web application that work like desktop application (fast, installable, with offline capabilities) based on [offline first](https://offlinefirst.org/) design 

* PWA is a bundle of technologies
  * [Web app Manifests](#Application-Manifest) make web applications installable
  * [Service workers](#Service-Workers) proxy requests between web applications and network
  * [Cache API](#Cache-static-data-with-Cache-API) 
    is used to provide a cache of HTTP requests/responses of static data
  * [IndexedDB](#Cache-dynamic-data-with-IndexedDB) 
    is used to provide a cache of dynamic data; e.g. from REST APIs
  * [Background Sync](#Background-Sync) defer tasks to be run in a service worker until
    the user has a stable network connection 
    (e.g. sending saved POST requests saved temporary in IndexedDB)
  * [Web Push Notifications](#Web-Push-Notifications) allow web applications to notify messages to user/device to go back to the web page with new content
  * [Responsive Design](CSS.md) makes web applications look like native apps
  * [Media Streams API](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API)
    allow web applications to stream audio and video with device camera and microphone; 
    see [guide](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API/Constraints)
  * [Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API) 
    to access user location; 
    see [guide](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API/Using_the_Geolocation_API)
* [PWA with Angular](#PWA-with-Angular)
* tools
  * [Workbox](https://developer.chrome.com/docs/workbox) 
    ease implementation of PWA features like caching (hide complex
    aspect through easier API / JavaScript libs)
  * [Lighthouse](https://developers.google.com/web/tools/lighthouse/) 
    Chrome DevTools to audit for performance, accessibility, PWA, SEO of websites
  * [android studio](https://developer.android.com/studio) 
    to test PWA on emulated device
* links    
  * [remote debug Android devices](https://developer.chrome.com/docs/devtools/remote-debugging/) 
    to test PWA on real android device
* courses
  * [Progressive Web Apps (PWA) - The Complete Guide](https://www.udemy.com/course/progressive-web-app-pwa-the-complete-guide/)
  * [Angular Progressive Web Apps (PWA) MasterClass](https://www.udemy.com/course/angular-pwa-course/)
  * [The complete guide to angular](https://www.udemy.com/the-complete-guide-to-angular-2/) include a module about Service Workers

[*Go to parent page*](README.md)

## Application Manifest

[Web app Manifests](https://developer.mozilla.org/en-US/docs/Web/Manifest)
make web applications installable like native application on a homescreen of a device
* **prerequisite**: require a running service worker
* links
  * [Web App Manifest Explanation by Google](https://web.dev/articles/add-manifest)
  * [How to provide your own in-app install experience](https://web.dev/articles/customize-install) 
    to make web application installable
  * [Can I use: Add to home screen](https://caniuse.com/web-app-manifest) 
* major manifest properties:
  * [name](https://developer.mozilla.org/en-US/docs/Web/Manifest/name): 
    long name of the web application
  * [short_name](https://developer.mozilla.org/en-US/docs/Web/Manifest/short_name): 
    short name of the web application; e.g. displayed on phone home screen
  * [start_url](https://developer.mozilla.org/en-US/docs/Web/Manifest/start_url): 
    start URL of the web application (could be overwridden)
  * [scope](https://developer.mozilla.org/en-US/docs/Web/Manifest/scope):
    restricts which web pages are displayed inside PWA context. 
    If the user navigates outside the scope, it reverts to a normal web page inside a browser 
    tab or window
  * [display](https://developer.mozilla.org/en-US/docs/Web/Manifest/display):
    specify how much of browser UI is shown to the user; e.g. use `standalone` to make web app 
    like native application
  * [background_color](https://developer.mozilla.org/en-US/docs/Web/Manifest/background_color):
    background color while loading and a splashscreen
  * [theme_color](https://developer.mozilla.org/en-US/docs/Web/Manifest/theme_color):
    define theme color used for several ui elements
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

* links
  * [Safari supported Meta Tags](https://developer.apple.com/library/archive/documentation/AppleApplications/Reference/SafariHTMLRef/Articles/MetaTags.html)
  * [Don’t use iOS meta tags irresponsibly in your Progressive Web Apps](https://firt.dev/ios-meta/)
* major meta tags:
  * `<meta name="apple-mobile-web-app-capable" content="yes">`: 
    enable web application as mobile web application
  * `<meta name="apple-mobile-web-app-status-bar-style" content="black">`: 
    somewhat equivalent to 
    [theme_color](https://developer.mozilla.org/en-US/docs/Web/Manifest/theme_color)
  * `<meta name="apple-mobile-web-app-title" content="Applicatin name">`: 
    equivalent to 
    [short_name](https://developer.mozilla.org/en-US/docs/Web/Manifest/short_name)
  * `<link rel="apple-touch-icon" href="..." size="..x..">`: 
    define the used icon for homescreen like 
    [icons](https://developer.mozilla.org/en-US/docs/Web/Manifest/icons)

[*Go to top*](#Progressive-Web-App)


## Service Workers

[Service workers](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker) 
proxy requests between web applications and network (e.g. for caching).

* links
  * [MDN guide](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API/Using_Service_Workers)
  * [Service Workers: an Introduction](https://developer.chrome.com/docs/workbox/service-worker-overview/)
  * [Are Service Workers Ready? - Check Browser Support](https://jakearchibald.github.io/isserviceworkerready/)
* concepts
  * JavaScript's application run in a single thread
  * [Web workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers) 
    are executed in another thread; in background. 
    They perform tasks without interfering with the user interface
  * [Service workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API) 
    are a special types of Web workers
  * Service workers only work with https (and localhost as exception)
  * Service workers support only http requests made with
    [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API).
    [XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest) is not supported
* install lifecycle
  * frontend javascript (in window context) 
    [register a service worker](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API/Using_Service_Workers#registering_your_worker)
  * browser will **install** the service worker asynchronously and sent a `install` event to installed service worker on completion
    * install of a service worker happens not with every registration, 
      but the first time or if the code of service worker changes (`sw.js`)
  * browser decide when the installed/updated service worker is **activated**
    * default: if existing version is running, user has to close tab and then the new version is activated
    * when a service worker is activated a `activate` event to the service worker is sent
  * it means that with default behaviours, user has to close/reload the application several times 
    to have a new version of service worker working on the application
* service workers re-acts on dedicated events
  * [install](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/install_event#examples) event;
    e.g. to download static assets in caches
  * [activate](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/activate_event#examples) event;
    e.g. cleanup old versions of caches
  * [fetch](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/fetch_event)
    events from requests made with [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API);
    e.g. access/update caches depending on cache strategies
  * `sync` events made by [Background Synchronization API](https://developer.mozilla.org/en-US/docs/Web/API/Background_Synchronization_API)
  * `push` events made by push notifications
* tips  
  * Offline can be simulated in Chrome DevTools > Application > Service Workers >
    select "Offline"
  * use [self](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/self) 
    in service worker code to access the global scope 
    ([self](https://developer.mozilla.org/en-US/docs/Web/API/Window/self) exists also for Window)
  * [ServiceWorkerRegistration.update()](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/update) 
    attemps to update new version of a service worker
    * update() could be triggered regularly with 
      [setInterval()](https://developer.mozilla.org/en-US/docs/Web/API/setInterval) every minute
  * use of [skipWaiting()](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/skipWaiting#example) and [Clients.claim()](https://developer.mozilla.org/en-US/docs/Web/API/Clients/claim#example)
    allow to use an activated service worker on clients (tabs) without having to reload the page
    * changing default behaviour can produce subtle bugs; e.g. if pending save operation is waiting for available network or if there is breaking changes in APIs
  * call [importScripts()](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/importScripts)
    to imports external js file in service workers (e.g. 3rd-party library like 
    [idb](https://github.com/jakearchibald/idb#readme))

[*Go to top*](#Progressive-Web-App)


## Cache static data with Cache API

[Cache API](https://developer.mozilla.org/en-US/docs/Web/API/Cache) 
is used to provide a cache of HTTP requests/responses of **static data** (e.g. application assets) with GET HTTP requests
* links
  * [Got any Cache? Basic Service Worker Caching](https://www.afasterweb.com/2016/12/31/got-any-cache-basic-service-worker-caching/) and [Upgrading Your Service Worker Cache](https://www.afasterweb.com/2017/01/31/upgrading-your-service-worker-cache/) (tutorial)
  * [Cache and return requests](https://developer.chrome.com/docs/workbox/service-worker-overview/#cache_and_return_requests) (tutorial)
  * [The offline cookbook](https://jakearchibald.com/2014/offline-cookbook/) (caching strategies; great reference)
  * [Storage for the web](https://web.dev/articles/storage-for-the-web) (checkout available storage quota)
  * [Service worker and caching from other origins](https://filipbech.github.io/2017/02/service-worker-and-caching-from-other-origins)
  * [MDN ServiceWorker Cookbook](https://github.com/mdn/serviceworker-cookbook) (examples)
  * [Service Worker Recipes](https://github.com/GoogleChrome/samples/tree/gh-pages/service-worker) (examples)
* concepts
  * caches are generally created to store application assets and provide offline mode
  * Cache API is available for frontend javascript and service workers
  * Cache API is not designed to requests/responses of REST API because caches is based on the URL only
    (cache cannot be based on request parameters, like a transaction-id, or request payload)
    * see [Caching Dynamic data](#cache-dynamic-data-with-indexeddb) for caches of REST API
  * Cache API differs from
    [HTTP Caching](https://developer.mozilla.org/en-US/docs/Web/HTTP/Caching)  
    by providing a way to service workers and frontend javascript to implements caching strategies
    * caches of a web-application for a given scope can be shared between 
      frontend javascript and service workers
  * api: [caches](https://developer.mozilla.org/en-US/docs/Web/API/caches) 
    global read-only property returns 
    [CacheStorage](https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage); 
    an interface to manage [Cache](https://developer.mozilla.org/en-US/docs/Web/API/Cache)
* *pre-caching* is used to cache assets ahead of time during; e.g. 
  [install event of service worker](https://jakearchibald.com/2014/offline-cookbook/#on-install---as-a-dependency) 
* *cache versioning* require versioned cache name and 
  *clean-up* of old versions typically during
  [activate event of service worker](https://jakearchibald.com/2014/offline-cookbook/#on-activate)
* *runtime/dynamic caching* or cache assets on demand during
  * [user interactions](https://jakearchibald.com/2014/offline-cookbook/#on-user-interaction)
    (from frontend javascript event-listener)
  * [fetch event of service worker](https://jakearchibald.com/2014/offline-cookbook/#on-network-response)
* [generic fallback](https://jakearchibald.com/2014/offline-cookbook/#generic-fallback) to returns an offline version of the asset (e.g. offline.html)
* major caching strategies
  * [cache only](https://jakearchibald.com/2014/offline-cookbook/#cache-only)
    strategy to be used for static data
  * [network only](https://jakearchibald.com/2014/offline-cookbook/#network-only) 
    strategy to be used for non-offline request (e.g. REST API)
  * [cache, falling back to network](https://jakearchibald.com/2014/offline-cookbook/#cache-falling-back-to-network) 
    strategy to be used to mix *cache only* for static data (in the cache) and *network only* (not present in the cache)
  * [cache then network](https://jakearchibald.com/2014/offline-cookbook/#cache-then-network) 
    strategy to be used for resources updating frequently (e.g. articles)
    * "something is provided quickly to user and cache is updated aftwerwards"
    * cache API used from frontend javascript & service workers
  * etc. (see [The offline cookbook](https://jakearchibald.com/2014/offline-cookbook/))
* [different caching strategies](https://jakearchibald.com/2014/offline-cookbook/#putting-it-together) 
  can be mixed together 
  * choosen strategy can depend on request URL or content type  
  
[*Go to top*](#Progressive-Web-App)


## Cache dynamic data with IndexedDB

[IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API) 
is a transactional Key-Value database in the browser and is used to store dynamic data
(e.g. response of GET requests of REST APIs) 
* links
  * [MDN guide](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API/Using_IndexedDB) and 
    [IndexedDB key characteristics](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API/Basic_Terminology)
  * see [idb](https://github.com/jakearchibald/idb#readme), [idb-keyval](https://github.com/jakearchibald/idb-keyval), [Dexie.js](https://dexie.org/) libraries to simplify the quite complex IndexedDB API
  * [Best Practices for Using IndexedDB](https://web.dev/articles/indexeddb-best-practices)
* concepts
  * [Cache API](https://developer.mozilla.org/en-US/docs/Web/API/Cache) vs 
    [IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API):
    * Cache API caches HTTP requests / responses
      * Cache API cannot cache dynamic data from REST APIs because it does not know the sequences of 
      the calls and does know not what to do in error cases
    * IndexedDB caches Key-Value pairs under control of the web application
      * (e.g. version of data can be part of the key, transformed json can be stored as value)  
  * [IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API) vs 
    [localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage):
    * IndexedDB can be accessed from normal JS and Service Workers; localStorage is available only in normal JS
    * IndexedDB can store much more data as localStorage
  * [caching strategies](https://jakearchibald.com/2014/offline-cookbook) 
    can also be used with [IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API) to cache GET REST APIs request
  * [IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API) in conjunction with Background sync allow to support offline capabilities with "update" REST APIs requests
  * **take care**: caching dynamic data is complex and produce subtle bugs; see [Best Practices for Using IndexedDB](https://web.dev/articles/indexeddb-best-practices)

[*Go to top*](#Progressive-Web-App)


## Background Sync

[Background Synchronization API](https://developer.mozilla.org/en-US/docs/Web/API/Background_Synchronization_API) 
can be used to defer tasks to be run in a service worker until the user has a stable network 
connection (e.g. sending saved POST requests saved temporary in IndexedDB).

[Web Periodic Background Synchronization API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Periodic_Background_Synchronization_API)
allows web applications to make any fetches/updates, at a periodic time interval.

* links
  * [Introducing Background Sync](https://developer.chrome.com/blog/background-sync/)
  * [ServiceWorker: A Basic Guide to BackgroundSync](https://ponyfoo.com/articles/backgroundsync)
  * [Background Sync – PWA’s Backbone](https://www.encora.com/insights/background-sync-pwas-backbone?excellarate-is-now-encora)
  * [Supercharge Your Website Using PWA: Background Sync](https://dev.to/ruppysuppy/supercharge-your-website-using-pwa-background-sync-1m23)

[*Go to top*](#Progressive-Web-App)

## Web Push Notifications

Web Push Notifications allow web applications to notify messages 
to user/device to go back to the web page with new content.

* links
  * [Web Push Book](https://web-push-book.gauntface.com/); a really nice reference
  * [Web Push Notifications - Timely, relevant, and precise](https://web.dev/articles/push-notifications-overview)
  * MDN: [Notification API](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API)
    and [guide](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API/Using_the_Notifications_API); [Push API](https://developer.mozilla.org/en-US/docs/Web/API/Push_API)
  * VAPID for server identification
    * [Using VAPID with WebPush](https://blog.mozilla.org/services/2016/04/04/using-vapid-with-webpush/)
    * [Web Push Interoperability Wins](https://developer.chrome.com/blog/web-push-interop-wins/)
  * backend library [web-push](https://github.com/web-push-libs/web-push) for Node.js or [webpush-java](https://github.com/web-push-libs/webpush-java)
  * [ServiceWorker Cookbook](https://github.com/mdn/serviceworker-cookbook) with web push examples
* concepts
  * [Notification API](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API) 
    lets a web app send notifications that are displayed *outside the webpage* at the system level; 
    even if the application is idle or in the background
    * notifications can be trigger from 
      [frontend javascript](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API/Using_the_Notifications_API#creating_a_notification) 
      or from [service workers](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/showNotification#examples)
      (e.g. to support web push notification)
    * web application [request user to enable notifications](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API/Using_the_Notifications_API#requesting_permission)
    * do not depend on notification to display important information. 
      Notifications might be available on the device or accepted by user
    * apperance of [Notification](https://developer.mozilla.org/en-US/docs/Web/API/Notification#properties) 
      are set with properties like
      [icon](https://developer.mozilla.org/en-US/docs/Web/API/Notification/icon),
      [image](https://developer.mozilla.org/en-US/docs/Web/API/Notification/image),
      [lang](https://developer.mozilla.org/en-US/docs/Web/API/Notification/lang),
      [actions](https://developer.mozilla.org/en-US/docs/Web/API/Notification/actions),
      [data](https://developer.mozilla.org/en-US/docs/Web/API/Notification/data),
      etc.
    * [service workers can listen notification click](https://developer.mozilla.org/en-US/docs/Web/API/NotificationEvent#example), custom [actions](https://developer.mozilla.org/en-US/docs/Web/API/Notification/actions)
      or [notification close](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/notificationclose_event#example)
  * [Push API](https://developer.mozilla.org/en-US/docs/Web/API/Push_API)
    allow web push notifications
    * web push notifications can be displayed even if web app/browser is closed (depending on the browser)
    * web push notifications required a running service worker
    * web app 
      [re-use](https://developer.mozilla.org/en-US/docs/Web/API/PushSubscription#example) or 
      [subscribe](https://developer.mozilla.org/en-US/docs/Web/API/PushManager/subscribe#examples) 
      new [PushSubscription](https://developer.mozilla.org/en-US/docs/Web/API/PushSubscription) 
      for a given browser-device to service worker
      * userVisibleOnly and applicationServerKey options of 
        [PushManager.subscribe()](https://developer.mozilla.org/en-US/docs/Web/API/PushManager/subscribe#syntax)
        allow securing notifications
    * [VAPID](https://blog.mozilla.org/services/2016/04/04/using-vapid-with-webpush/) is 
        provided to `applicationServerKey` to identify subscription
      * VAPID can be generated with [webpush-java](https://github.com/web-push-libs/webpush-java#cli) or [web-push](https://github.com/web-push-libs/web-push#command-line)
    * push subscription is related to a push server owned by browser vendor  
      * every browser vendor has a specific push server (e.g. handled by google for chrome)  
    * push subscription can be stored on the web app backend server and can be used to 
    send notifications
    * backend need also library to be able to push notifications;
      e.g. [web-push](https://github.com/web-push-libs/web-push) for Node.js or
      [webpush-java](https://github.com/web-push-libs/webpush-java)
    * notification from web app backend will be sent to browser vendor push server and
      browser vendor push server will forward the notification as "push" event to service worker
      of the corresponding browser-device
    * "push" events of service worker are displayed to user
      with [Notification API](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API)

[*Go to top*](#Progressive-Web-App)


## PWA with Angular

* [Service Workers](https://angular.io/guide/service-worker-intro)
  * see [Create a Progressive Web App with the Angular CLI](https://web.dev/articles/creating-pwa-with-angular-cli) and [Precaching with the Angular service worker](https://web.dev/articles/precaching-with-the-angular-service-worker):
    * Configure Service Workers in an Angular project: `ng add @angular/pwa`
    * Angular/PWA generate a service worker based on the `ngsw-config.json`
    * we can specify in `ngsw-config.json`
      * which files or urls should be prefetched by the generated service worker
      * caches to be used for rest APIs
      * service-worker can be configured to fetch data from the network and use cache data in case of timeout; see [strategy of cacheconfig](https://angular.io/guide/service-worker-config#strategy)
    * to disable quick service worker on production; set `serviceWorker` to false in `angular-cli.json` and serve a new version of the application in production (user still have to load the application twice)
  * use [SwUpdate](https://angular.io/api/service-worker/SwUpdate#swupdate) service to [detect and install new version of the application](https://angular.io/guide/service-worker-communications#swupdate-service)
* [Application Shell](https://angular.io/guide/app-shell) to display an initial static page while the application is loaded
  * Angular application is pre-rendered with [Angular Universal](https://angular.io/guide/universal) under the hood but without having a running Angular Universal server.
* [Push Notifications](https://angular.io/guide/service-worker-notifications) with 
  [SwPush](https://angular.io/api/service-worker/SwPush#usage-notes) service


[*Go to top*](#Progressive-Web-App)

*(Page mainly written in spring 2022; links checked on 01.03.2024)*
