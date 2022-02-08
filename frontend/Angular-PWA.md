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
