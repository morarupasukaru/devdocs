# Next.js

[Next.js](https://nextjs.org/) is a framework to ease development of [React](ReactJS.md) 
web applications.

* concepts
  * [file-based routing](#file-based-routing) infer the routes of pages from the folder structure
  * [pre-rendering & client-side rendering](#pre-rendering--client-side-rendering)
  * [API routes](#api-routes) to create an API endpoint as a Node.js serverless function
  * [deployment & configuration](#deployment--configuration)
  * [authentification](https://nextjs.org/docs/pages/building-your-application/authentication) with third-party lib [next-auth](https://authjs.dev/)
* misc
  * use [create-next-app](https://github.com/vercel/next.js/tree/canary/packages/create-next-app) to create new Next.js application
  * [static file serving](https://nextjs.org/docs/pages/building-your-application/optimizing/static-assets): files under /public are serve statically by Next.js
  * [Head](https://nextjs.org/docs/pages/api-reference/components/head) component allow to add meta and <head> tags
  * [page/_app.js](https://nextjs.org/docs/pages/building-your-application/routing/custom-app) custom app can override the default App, e.g. to add default <Head> to be available to all pages
  * [pages/_document.js](https://nextjs.org/docs/pages/building-your-application/routing/custom-document) custom document can override the default Document (whole HTML document), e.g. to add lang to html tag
  * [Image](https://nextjs.org/docs/pages/api-reference/components/image#required-props) component must be used instead of `<img>` to enable [image optimization](https://nextjs.org/docs/basic-features/image-optimization) like lazy loading and providing multiple version of the images depend on the browser 
  * [building forms with Next.js](https://nextjs.org/docs/pages/building-your-application/data-fetching/forms-and-mutations#part-6-form-submission-with-javascript-enabled)
* links
  * [Next.js & React - The Complete Guide](https://www.udemy.com/course/nextjs-react-the-complete-guide/) video course
  * [Remix](https://remix.run/): alternative to Next.js but always with server-side rendering. Framework is more recent, better, etc. 

[*Go to parent page*](README.md)


## file-based routing

[File-based routing](https://nextjs.org/docs/pages/building-your-application/routing)
is the Next.js feature that infer the routes of pages from the folder structure

* useRouter hook allow to access value of 
  [dynamic routes](https://nextjs.org/docs/pages/building-your-application/routing/dynamic-routes)
* [catch all segments](https://nextjs.org/docs/pages/building-your-application/routing/dynamic-routes#catch-all-segments) 
  is a dynamic route that support non-fixed number of dynamic values in url
* use [Link](https://nextjs.org/docs/pages/api-reference/components/link) component to add 
  [Linking between pages](https://nextjs.org/docs/pages/building-your-application/routing/linking-and-navigating)
* navigating [programmatically/imperatively](https://nextjs.org/docs/pages/building-your-application/routing/linking-and-navigating#imperative-routing) 
  but using [router.push(...)](https://nextjs.org/docs/pages/api-reference/functions/use-router#routerpush) 
  or [router.replace(...)](https://nextjs.org/docs/pages/api-reference/functions/use-router#routerreplace)
* add [custom 404 page](https://nextjs.org/docs/pages/building-your-application/routing/custom-error#404-page) by adding `pages/404.js`

[*Go to top*](#nextjs)


## pre-rendering & client-side rendering

* disadvantage with normal SPA:
  * user has to wait the loaded data (ui is rendered and then has to fetch additional dynamic data)
  * search engine optimization does not support SPA
* [pre-rendering](https://nextjs.org/docs/pages/building-your-application/rendering)
  used by Next.js generates HTML for pages in advance
  * when the page is loaded by the browser, JavaScript make it fully interactive (hydration)
* Next.js support two forms of pre-rendering
  * [static generation](https://nextjs.org/docs/pages/building-your-application/rendering/static-site-generation) :
    the HTML is generated at build time and will be reused on each request (recommended)
  * [server-side rendering](https://nextjs.org/docs/pages/building-your-application/rendering/server-side-rendering) (SSR) :
    the HTML is generated on each request
* static generation is recommended for performance reason (can be stored in CDN)
* Next.js pre-render by default pages without dynamic data
* Next.js pre-render mode is defined at page level and therefore is quite flexible
* [client-side rendering](https://nextjs.org/docs/pages/building-your-application/data-fetching/client-side) (CSR) 
  is used to hydrate pre-render pages
* static generation with [getStaticProps](https://nextjs.org/docs/pages/building-your-application/data-fetching/get-static-props)
  and [getStaticPaths](https://nextjs.org/docs/pages/building-your-application/data-fetching/get-static-paths)
  * Next.js will pre-render _at build time_ (static generation) a page having getStaticProps using the props returned by getStaticProps
    * sourcecode of getStaticProps is not send to client and can contain critical data (as long as critical data are not provided in returned props)
  * [incremental static generation](https://nextjs.org/docs/pages/building-your-application/data-fetching/incremental-static-regeneration) (ISR) allow to re-generate a page on request at most every X seconds; 
  see [revalidate](https://nextjs.org/docs/pages/api-reference/functions/get-static-props#revalidate) property of getStaticProps return values
    * see also [notfound](https://nextjs.org/docs/pages/api-reference/functions/get-static-props#notfound) 
      and [redirect](https://nextjs.org/docs/pages/api-reference/functions/get-static-props#redirect) properties of getStaticProps return values
  * [context](https://nextjs.org/docs/pages/api-reference/functions/get-static-props#context-parameter) parameter is provided to getStaticProps; e.g. `context.params` contains _dynamic_ route parameters
  * [dynamic routes](https://nextjs.org/docs/pages/building-your-application/routing/dynamic-routes) are not pre-render by default
  * [getStaticPaths](https://nextjs.org/docs/pages/building-your-application/data-fetching/get-static-paths) define a list of paths to be statically generated
  * getStaticPaths can return paths of a dynamic route for specific ids if data are available at pre-render time
  * [fallback](https://nextjs.org/docs/pages/api-reference/functions/get-static-paths#fallback-false) of getStaticPaths return values is usefull to avoid to pre-render to many pages or unfrequent read pages
* server-side rendering (SSR)
  with [getServerSideProps](https://nextjs.org/docs/pages/api-reference/functions/get-server-side-props)
  * SSR allow to pre-render the page on each request on the server
  * SSR is useful if data changes often (e.g. fetch data from db required for every request)
  * SSR allow to access to incoming request (e.g. cookies)
    * [context](https://nextjs.org/docs/pages/api-reference/functions/get-server-side-props#context-parameter) parameter of 
      [getServerSideProps](https://nextjs.org/docs/pages/api-reference/functions/get-server-side-props) allow access to Node.js request & response  
  * getServerSideProps and [getStaticProps](https://nextjs.org/docs/pages/building-your-application/data-fetching/get-static-props)/[getStaticPaths](https://nextjs.org/docs/pages/building-your-application/data-fetching/get-static-paths) should not be used on the same page
* [client-side rendering](https://nextjs.org/docs/pages/building-your-application/data-fetching/client-side) (CSR) can perform with
  * [useEffect](https://nextjs.org/docs/pages/building-your-application/data-fetching/client-side#client-side-data-fetching-with-useeffect) 
  hook as standard React component OR with
  * [useSWR](https://nextjs.org/docs/pages/building-your-application/data-fetching/client-side#client-side-data-fetching-with-swr) hook from [SWR](https://swr.vercel.app/) (recommended)
    *  SWR handles caching, revalidation, focus tracking, refetching on intervals, and more

[*Go to top*](#nextjs)


## API routes

[API Routes](https://nextjs.org/docs/pages/building-your-application/routing/api-routes) to create an API endpoint as a Node.js serverless function
* pages/api folder contains handler functions of API routes
* [dynamic API routes](https://nextjs.org/docs/pages/building-your-application/routing/api-routes#dynamic-api-routes) are equivalent as 
  dynamic routes
* see example of [API routes with REST](https://github.com/vercel/next.js/tree/canary/examples/api-routes-rest)
* don't perform REST requests to API routes for pre-render pages but share logic to access data; e.g. by exporting some helper functions
  * ... but of course, pages with client-side rendering can perform REST requests to API routes to get data 

[*Go to top*](#nextjs)


## deployment & configuration

* [deployment](https://nextjs.org/docs/pages/building-your-application/deploying) options
  * standard build with `next build` that require Node.js server
  * [full static build](https://nextjs.org/docs/advanced-features/static-html-export) with `next export` to produce static app. no Node.js server required
    * API routes, service-side page, page revalidation, etc. won't be supported
* see [next.config.js](https://nextjs.org/docs/pages/api-reference/next-config-js) on how to configure [environment variables](https://nextjs.org/docs/pages/building-your-application/configuring/environment-variables) for development, production or other _phases_

[*Go to top*](#nextjs)

*(Page mainly written in december 2022; links checked on 27.02.2024)*
