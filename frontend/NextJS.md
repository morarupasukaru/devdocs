# Next.js

[Next.js](https://nextjs.org/) is a framework to ease development of [React](./ReactJS.md) 
web applications.

* concepts
  * [File-based routing](#File-based-Routing) infer the routes of pages from the folder structure
  * server-side page (pre-)rendering
  * file-based routing
  * build fullstack react apps (nodejs backend)
* basics & foundations
  * file-based routing
  * server-side page (pre-)rendering & data fetching
  * combine standard react with Next.js
  * API routes & fullstack capabilities
* advanced concepts
  * optimization
  * deployment & configuration
  * authentification
* links
  * [Remix](https://remix.run/): alternative to Next.js but always with server-side rendering. Framework is more recent, better, etc. 
  * [Next.js & React - The Complete Guide](https://www.udemy.com/course/nextjs-react-the-complete-guide/) video course

[*Go to parent page*](../README.md)

*(Page mainly written in december 2022)*

## File-based routing

[File-based routing](https://nextjs.org/docs/routing/introduction)
is the Next.js feature that infer the routes of pages from the folder structure

* [useRouter](https://nextjs.org/docs/routing/dynamic-routes) hook allow to access value of [dynamic routes](https://nextjs.org/docs/routing/introduction#dynamic-route-segments)
* [catch all routes](https://nextjs.org/docs/routing/dynamic-routes#catch-all-routes) is a dynamic route that support non fixed number of dynamic values in url
* use [Link](https://nextjs.org/docs/api-reference/next/link) componet to add [Linking between pages](https://nextjs.org/docs/routing/introduction#linking-between-pages)
* navigating [programmatically/imperatively](https://nextjs.org/docs/routing/imperatively) but using [router.push(...)](https://nextjs.org/docs/api-reference/next/router#routerpush) or [router.replace(...)](https://nextjs.org/docs/api-reference/next/router#routerreplace)
* add [custom 404 page](https://nextjs.org/docs/advanced-features/custom-error-page#404-page) by adding `pages/404.js`

[*Go to top*](#nextjs)
