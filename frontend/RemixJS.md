# Remix

[Remix](https://remix.run/) is a [React](./ReactJS.md) full stack web framework like [Next.js](./NextJS.md)

* Remix vs [Next.js](./NextJS.md)
  * Remix: always use server-side rendering; server is called for every request
  * [Next.js](./NextJS.md): server-side rendering supported but static site generation is default/recommended
  * Remix is faster than Next.js 
  * more info with [Remix vs Next.js](https://remix.run/blog/remix-vs-next)
* concepts
  * routing 
    * [file-based routing](https://remix.run/docs/en/v1/file-conventions/routes-files) like [Next.js](./NextJS.md)
      supporting:
      * [nested routing](https://remix.run/docs/en/v1/guides/routing#what-is-nested-routing)
      * [dynamic routes](https://remix.run/docs/en/v1/file-conventions/routes-files#dynamic-route-parameters) 
      * [optional segments](https://remix.run/docs/en/v1/file-conventions/routes-files#optional-segments)
      * [layout routes](https://remix.run/docs/en/v1/file-conventions/routes-files#layout-routes)
      * [splat routes](https://remix.run/docs/en/v1/file-conventions/routes-files#splat-routes) 
        "catch-all routes" e.g. to [redirect](https://remix.run/docs/en/v1/utils/redirect) to on given url 
      * [pathless layout routes](https://remix.run/docs/en/v1/file-conventions/routes-files#pathless-layout-routes)
        to share e.g. layout, styles over several routes without adding new route segment 
      * [resource routes](https://remix.run/docs/en/v1/guides/api-routes#resource-routes)
        to render e.g. PDF documents (non application's UI route)
      * [useSearchParams](https://remix.run/docs/en/v1/guides/data-loading#search-params-in-components) 
        hook to access URL search params 
        (based on URL API [URLSearchParams](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams))
      * ...
      * see [routing](https://remix.run/docs/en/v1/guides/routing#routing) guide
      * take care: [route file naming convention is changing in v2](https://remix.run/docs/en/v1/file-conventions/route-files-v2)
    * [root page (root.tsx)](https://remix.run/docs/en/v1/file-conventions/root#root-route)
      containing a [&lt;Outlet /&gt;](https://remix.run/docs/en/v1/components/outlet) 
      * add components to root page to make available on all *pages* (e.g. navigation)
    * [Link](https://remix.run/docs/en/v1/components/link) to use for anchor tag
      * `..` can be used to got to parent path, (feature of React [Link](https://reactrouter.com/en/main/components/link))
    * [useNavigate](https://reactrouter.com/en/6.7.0/hooks/use-navigate) 
      hook used for programmatically navigation 
      (from [React Router v6](https://remix.run/docs/en/v1/other-api/react-router))
  * [&lt;Outlet /&gt;](https://remix.run/docs/en/v1/components/outlet)
    to render child routes in parent component
  * styling
    * [route styles](https://remix.run/docs/en/v1/guides/styling#route-styles)
      for styling of a route/page
    * [surfacing styles](https://remix.run/docs/en/v1/guides/styling#surfacing-styles)
      for styling a component with individual css file
      * take care: surfacing styles is not using [css module](https://github.com/css-modules/css-modules). css is gobal and css conflicts can happen
  * data loading/update 
    * [loader](https://remix.run/docs/en/v1/route/loader)
      server side function provides data to the route when rendering
      * [useLoaderData](https://remix.run/docs/en/v1/hooks/use-loader-data)
        hook returns the JSON parsed data from your route loader function
        * useLoaderData hook can be called in any component of a route
      * [useMatches](https://remix.run/docs/en/v1/hooks/use-matches) returns 
        all routes matching on the page
        * can be used to access parent route data from nested route 
    * [action](https://remix.run/docs/en/v1/route/action)
      server side function handle data mutations on a page e.g. triggered from 
      child [Form](https://remix.run/docs/en/v1/components/form#action) component request
      * [useActionData](https://remix.run/docs/en/v1/hooks/use-action-data) 
        hook returns the JSON parsed data from your route action; e.g. of form validation errors
        * useActionData hook can be called in any component of a route
      * use [Form](https://remix.run/docs/en/v1/components/form#method) Remix component allow to use
        `delete` method (altough non-standard in HTML) 
    * [useSubmit](https://remix.run/docs/en/v1/hooks/use-submit) 
      hook can be used to programmatically submit a form
    * [useFetcher](https://remix.run/docs/en/v1/hooks/use-fetcher) 
      hook can be used to programmatically load/submit without subsequent navigations
      (e.g. highly interactive app)
    * [useTransition](https://remix.run/docs/en/v1/hooks/use-transition)
      hook allow to build pending navigation indicators and optimistic UI on data mutations
    * [Error handling](https://remix.run/docs/en/v1/guides/errors) is using 
      [Error-Boundary](https://remix.run/docs/en/v1/route/error-boundary)
      ; a React component that renders whenever there is (unexcepted) error anywhere on the route, 
      either during rendering or during data loading
      * e.g. adding Error-Boundary to root.tsx to catch all unexcepted error in single place
    * [CatchBoundary](https://remix.run/docs/en/v1/route/catch-boundary)
      is a React component that renders whenever an action or loader throws a Response 
      (expected errors)
      * see [not found (404) handling](https://remix.run/docs/en/v1/guides/not-found)
    * javascript/typescript file having ".server." in name are only available on the server 
    * adding .server js/ts filename is a hint to the compiler that file will be only 
      served on the backend
      (see [module constraints](https://remix.run/docs/en/v1/guides/constraints#no-module-side-effects))
    * code of Component is run on client and server (for pre-rendering). 
      Put server-side code only in
      [loader](https://remix.run/docs/en/v1/route/loader) or
     [action](https://remix.run/docs/en/v1/route/action)
  * authentification
    * [createCookieSessionStorage](https://remix.run/docs/en/v1/utils/sessions#createcookiesessionstorage)
      to create session cookies
    * protecting routes can be achieved by throwing [redirect](https://remix.run/docs/en/v1/utils/redirect) 
      in [loader](https://remix.run/docs/en/v1/route/loader);
      see [explanations in FAQ](https://remix.run/docs/en/v1/pages/faq#how-can-i-have-a-parent-route-loader-validate-the-user-and-protect-all-child-routes)
  * optimization
    * [meta](https://remix.run/docs/en/v1/route/meta)
      export will set meta tags (metadata) for your html document
    * custom response headers can be defined...
      * ...by using [headers](https://remix.run/docs/en/v1/route/headers) 
        function to define response headers pro route
      * ...by adding responseHeaders in `entry.server.jsx` that is provided to all responses
    * [disabling JavaScript](https://remix.run/docs/en/v1/guides/disabling-javascript) 
      for some static pages prevent to download unnecessary JavaScript files
    * [remix.config.js](https://remix.run/docs/en/v1/file-conventions/remix-config)
      to override default Remix project configuration
  * [deploying](https://remix.run/docs/en/v1/guides/deployment) 
      Remix app on different platform using 
      [server adapter](https://remix.run/docs/en/v1/other-api/adapter)
  * misc
    * [defaultValue](https://reactjs.org/docs/uncontrolled-components.html#default-values) 
      React-specific attribute can be used to set a default value to e.g. input field
* links
  * [Remix.js - The Practical Guide](https://www.udemy.com/course/remix-course/) video course

[*Go to parent page*](../README.md)

*(Page mainly written in 12.2022 - 01.2023; links checked on TODO)*