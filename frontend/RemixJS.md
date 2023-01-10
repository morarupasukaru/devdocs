# React

[Remix](https://remix.run/) is a [React](./ReactJS.md) full stack web framework like [Next.js](./NextJS.md)

* concepts
  * [file-based routing](https://remix.run/docs/en/v1/file-conventions/routes-files) like [Next.js](./NextJS.md)
  * [root page (root.tsx)](https://remix.run/docs/en/v1/file-conventions/root#root-route) 
    containing a [&lt;Outlet /&gt;](https://remix.run/docs/en/v1/components/outlet) 
    * add components to root page to make available on all *pages* (e.g. navigation)
  * [&lt;Outlet /&gt;](https://remix.run/docs/en/v1/components/outlet)
    to render child routes in parent component
  * [route styles](https://remix.run/docs/en/v1/guides/styling#route-styles)
    for styling of a route/page
  * [surfacing styles](https://remix.run/docs/en/v1/guides/styling#surfacing-styles)
    for styling a component with individual css file
    * take care: surfacing styles is not using [css module](https://github.com/css-modules/css-modules). css is gobal and css conflicts can happen
* Remix vs [Next.js](./NextJS.md)
  * Remix: always use server-side rendering; server is called for every request
  * [Next.js](./NextJS.md): server-side rendering supported but static site generation is default/recommended
* links
  * [Remix.js - The Practical Guide](https://www.udemy.com/course/remix-course/) video course

[*Go to parent page*](../README.md)

*(Page mainly written in december 2022)*
