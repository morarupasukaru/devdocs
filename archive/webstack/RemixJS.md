# Remix

[Remix](https://remix.run/) is a [React](ReactJS.md) full stack web framework like [Next.js](NextJS.md)

* Remix vs [Next.js](NextJS.md)
  * Remix: always use server-side rendering; server is called for every request
  * [Next.js](NextJS.md): server-side rendering supported but static site generation is default/recommended
  * Remix is faster than Next.js 
  * more info with [Remix vs Next.js](https://remix.run/blog/remix-vs-next)
* concepts
  * routing 
    * [file-based routing](https://remix.run/docs/en/main/file-conventions/routes) like [Next.js](NextJS.md)
      supporting:
      * [nested routing](https://remix.run/docs/en/main/file-conventions/routes#nested-routes)
      * [dynamic segments](https://remix.run/docs/en/main/file-conventions/routes#dynamic-segments) 
      * [optional segments](https://remix.run/docs/en/main/file-conventions/routes#optional-segments)
      * [nested routes](https://remix.run/docs/en/main/file-conventions/routes#nested-routes)
      * [splat routes](https://remix.run/docs/en/main/file-conventions/routes#splat-routes) 
        "catch-all routes" e.g. to [redirect](https://remix.run/docs/en/main/utils/redirect) to on given url 
      * [pathless routes](https://remix.run/docs/en/main/file-conventions/routes#nested-layouts-without-nested-urls)
        to share e.g. layout, styles over several routes without adding new route segment 
      * [resource routes](https://remix.run/docs/en/main/guides/api-routes#resource-routes)
        to render e.g. PDF documents (non application's UI route)
      * [useSearchParams](https://remix.run/docs/en/main/guides/data-loading#search-params-in-components) 
        hook to access URL search params 
        (based on URL API [URLSearchParams](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams))
      * ...
    * [root page (root.tsx)](https://remix.run/docs/en/main/file-conventions/root)
      containing a [&lt;Outlet /&gt;](https://remix.run/docs/en/main/components/outlet) 
      * add components to root page to make available on all *pages* (e.g. navigation)
    * [Link](https://remix.run/docs/en/main/components/link) to use for anchor tag
      * `..` can be used to got to parent path, (feature of React [Link](https://reactrouter.com/en/main/components/link))
    * [useNavigate](https://remix.run/docs/en/main/hooks/use-navigate) 
      hook used for programmatically navigation 
      (from [React Router v6](https://remix.run/docs/en/v1/other-api/react-router))
  * [&lt;Outlet /&gt;](https://remix.run/docs/en/main/components/outlet)
    to render child routes in parent component
  * styling
    * [route styles](https://remix.run/docs/en/main/styling/css#route-styles)
      for styling of a route/page
    * [surfacing styles](https://remix.run/docs/en/main/styling/css#surfacing-styles)
      for styling a component with individual css file
      * take care: surfacing styles is not using [css module](https://github.com/css-modules/css-modules). css is global and css conflicts can happen
  * data loading/update 
    * [loader](https://remix.run/docs/en/main/route/loaderr)
      server side function provides data to the route when rendering
      * [useLoaderData](https://remix.run/docs/en/main/hooks/use-loader-data)
        hook returns the JSON parsed data from your route loader function
        * useLoaderData hook can be called in any component of a route
      * [useMatches](https://remix.run/docs/en/main/hooks/use-matches) returns 
        all routes matching on the page
        * can be used to access parent route data from nested route 
    * [action](https://remix.run/docs/en/main/route/action)
      server side function handle data mutations on a page e.g. triggered from 
      child [Form](https://remix.run/docs/en/main/components/form#action) component request
      * [useActionData](https://remix.run/docs/en/main/hooks/use-action-data) 
        hook returns the JSON parsed data from your route action; e.g. of form validation errors
        * useActionData hook can be called in any component of a route
      * use [Form](https://remix.run/docs/en/main/components/form) Remix component allow to use
        `delete` method (altough non-standard in HTML) 
    * [useSubmit](https://remix.run/docs/en/main/hooks/use-submit) 
      hook can be used to programmatically submit a form
    * [useFetcher](https://remix.run/docs/en/main/hooks/use-fetcher) 
      hook can be used to programmatically load/submit without subsequent navigations
      (e.g. highly interactive app)
    * [useNavigation](https://remix.run/docs/en/main/hooks/use-navigation)
      hook allow to build pending navigation indicators and optimistic UI on data mutations
    * [Error handling](https://remix.run/docs/en/main/guides/errors) is using 
      [Error-Boundary](https://remix.run/docs/en/main/route/error-boundary)
      ; a React component that renders whenever there is (unexcepted) error anywhere on the route, 
      either during rendering or during data loading
      * e.g. adding Error-Boundary to root.tsx to catch all unexcepted error in single place
      * see [not found (404) handling](https://remix.run/docs/en/main/guides/not-found)
    * javascript/typescript file having ".server." in name are only available on the server 
    * adding .server js/ts filename is a hint to the compiler that file will be only 
      served on the backend
      (see [module constraints](https://remix.run/docs/en/main/guides/constraints#no-module-side-effects))
    * code of Component is run on client and server (for pre-rendering). 
      Put server-side code only in
      [loader](https://remix.run/docs/en/main/route/loader) or
     [action](https://remix.run/docs/en/main/route/action)
  * authentification
    * [createCookieSessionStorage](https://remix.run/docs/en/main/utils/sessions#createcookiesessionstorage)
      to create session cookies
    * protecting routes can be achieved by throwing [redirect](https://remix.run/docs/en/main/utils/redirect) 
      in [loader](https://remix.run/docs/en/main/route/loader);
      see [explanations in FAQ](https://remix.run/docs/en/main/guides/faq#how-can-i-have-a-parent-route-loader-validate-the-user-and-protect-all-child-routes)
  * optimization
    * [meta](https://remix.run/docs/en/main/route/meta)
      export will set meta tags (metadata) for your html document
    * custom response headers can be defined...
      * ...by using [headers](https://remix.run/docs/en/main/route/headers) 
        function to define response headers pro route
      * ...by adding responseHeaders in `entry.server.jsx` that is provided to all responses
    * [disabling JavaScript](https://remix.run/docs/en/main/guides/disabling-javascript) 
      for some static pages prevent to download unnecessary JavaScript files
    * [remix.config.js](https://remix.run/docs/en/main/file-conventions/remix-config)
      to override default Remix project configuration
  * [deploying](https://remix.run/docs/en/main/guides/deployment) 
      Remix app on different platform using 
      [server adapter](https://remix.run/docs/en/main/other-api/adapter)
  * misc
    * [defaultValue](https://reactjs.org/docs/uncontrolled-components.html#default-values) 
      React-specific attribute can be used to set a default value to e.g. input field
* links
  * [Remix.js - The Practical Guide](https://www.udemy.com/course/remix-course/) video course

[*Go to parent page*](README.md)

*(Page mainly written in 12.2022; links checked on 27.02.2024)*
