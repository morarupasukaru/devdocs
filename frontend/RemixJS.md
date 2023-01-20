# Remix

[Remix](https://remix.run/) is a [React](./ReactJS.md) full stack web framework like [Next.js](./NextJS.md)

* concepts
  * routing 
    * [file-based routing](https://remix.run/docs/en/v1/file-conventions/routes-files) like [Next.js](./NextJS.md)
      supporting:
      * [nested routing](https://remix.run/docs/en/v1/guides/routing#what-is-nested-routing)
      * [dynamic routes](https://remix.run/docs/en/v1/file-conventions/routes-files#dynamic-route-parameters) 
      * [optional segments](https://remix.run/docs/en/v1/file-conventions/routes-files#optional-segments)
      * [layout routes](https://remix.run/docs/en/v1/file-conventions/routes-files#layout-routes)
      * [splat routes](https://remix.run/docs/en/v1/file-conventions/routes-files#splat-routes) "catch-all routes"
      * ...
      * see [routing](https://remix.run/docs/en/v1/guides/routing#routing) guide
      * take care: [route file naming convention is changing in v2](https://remix.run/docs/en/v1/file-conventions/route-files-v2)
    * [root page (root.tsx)](https://remix.run/docs/en/v1/file-conventions/root#root-route)
      containing a [&lt;Outlet /&gt;](https://remix.run/docs/en/v1/components/outlet) 
      * add components to root page to make available on all *pages* (e.g. navigation)
    * [Link](https://remix.run/docs/en/v1/components/link) to use for anchor tag
      * `..` can be used to got to parent path, (feature of React [Link](https://reactrouter.com/en/main/components/link))
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
    * [action](https://remix.run/docs/en/v1/route/action)
      server side function handle data mutations on a page e.g. triggered from 
      child [Form](https://remix.run/docs/en/v1/components/form#action) component request
      * [useActionData](https://remix.run/docs/en/v1/hooks/use-action-data) 
        hook returns the JSON parsed data from your route action; e.g. of form validation errors
        * useActionData hook can be called in any component of a route
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
  * [meta](https://remix.run/docs/en/v1/route/meta) 
    export will set meta tags for your html document
* Remix vs [Next.js](./NextJS.md)
  * Remix: always use server-side rendering; server is called for every request
  * [Next.js](./NextJS.md): server-side rendering supported but static site generation is default/recommended
* links
  * https://stateful.com/blog/remix-react-framework
  * [Remix.js - The Practical Guide](https://www.udemy.com/course/remix-course/) video course

[*Go to parent page*](../README.md)

*(Page mainly written in 12.2022 - 01.2023)*
