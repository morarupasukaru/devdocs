# Svelte

[Svelte](https://svelte.dev/) ease development of SPA web applications and provide an interesting
alternative to popular framework like Angular.

* Svelte is a compiler that compiles components writen an enhanced JavaScript at build time into vanilla JavaScript
* Svelte along with Sapper or SvelteKit are an alternative to frameworks like Angular
* advantages of Svelte vs Angular
  * **very small and optimized JavaScript is build**
  * [no (emulated) virtual/shadom DOM](https://svelte.dev/blog/virtual-dom-is-pure-overhead)
  * [quick learn curve (based on JS/HTML/CSS syntax)](https://svelte.dev/blog/write-less-code)
  * CSS is component scoped
  * interesting concepts to have a look as web developer
* disadvantages
  * fewer features as in Angular
  * quite new and no big companies behind
  * risk of changes / unwanted migrations to do
  * examples of success stories are missing (popular companies use Svelte but without concrete examples)
* follow [official tutorial](https://svelte.dev/tutorial/basics) to learn Svelte (no summary is required here)
* [SvelteKit](https://kit.svelte.dev/) (or [Sapper](https://sapper.svelte.dev/) is deprecated)
    are web applications framework based on Svelte
  * Sapper/SvelteKit provide routing and server-side rendering (require Node.JS server)
  * prerendering on server side is done only with first HTTP request (for site scrawler)
  * rendering is done after first HTTP request only in SPA
  * screens are preloaded when user move mouse hover links to speed-up navigation 
  * server-side rendering require a Node.JS server
  * alternative: pre-render web pages with Sapper and provide them as static bundle (at build-time like JAMStack); 
    see [exporting](https://sapper.svelte.dev/docs#Exporting)
* tools
  * [rollup.js](https://rollupjs.org/guide/en/) is a module bundler for JavaScript that can be used with Svelte
* references
  * [online sandbox](https://svelte.dev/repl/hello-world)
  * [examples](https://svelte.dev/examples#hello-world) from [Svelte website](https://svelte.dev/)
  * course: [Svelte.js - The Complete Guide (incl. Sapper.js)](https://www.udemy.com/sveltejs-the-complete-guide/)

[*Go to parent page*](README.md)

*(Page mainly written in april 2021; links checked on 19.02.2024)*
