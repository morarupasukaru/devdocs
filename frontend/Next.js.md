# NEXT.js

[NEXT.js](https://nextjs.org/) is a framework to ease development of [React](https://reactjs.org/) 
web applications.

* key features
  * server-side page (pre-)rendering
  * file-based routing
  * build fullstack react apps (nodejs backend)
* basics & foundations
  * file-based routing
  * server-side page (pre-)rendering & data fetching
  * combine standard react with NextJS
  * API routes & fullstack capabilities
* advanced concepts
  * optimization
  * deployment & configuration
  * authentification
* summaries & refreshers
  * ReactJS refresher
  * NextJS summary

# React.JS

[React](https://reactjs.org/) is a client-side JavaScript library for building user interfaces.

* concepts
  * use [create-react-app](https://create-react-app.dev/) to create new react application
  * [JSX](https://reactjs.org/docs/introducing-jsx.html) : _html_ tags in javascript code
  * [component](https://reactjs.org/docs/components-and-props.html#function-and-class-components): provide custom html tag with a javascript function returning displayed content, e.g. html code
  * [props](https://reactjs.org/docs/components-and-props.html) are input parameters of the javascript function of the component
  * [handling events](https://reactjs.org/docs/handling-events.html) is very similar to handling events on DOM elements
  * [useState](https://reactjs.org/docs/hooks-reference.html#usestate) hook allow to re-render component/ui with new state/value;
    see also [Using the State Hook](https://reactjs.org/docs/hooks-state.html)
  * [css modules](https://create-react-app.dev/docs/adding-a-css-modules-stylesheet/) for having scoping component styles; see also [css module feature documentation](https://github.com/css-modules/css-modules)
  * [basic list component](https://reactjs.org/docs/lists-and-keys.html#basic-list-component) use map javascript array function to map data to React tag component (JSX element)
  * [wrapper component](https://reactjs.org/docs/composition-vs-inheritance.html#containment) by using children prop
  * Forms
    * [useRef](https://reactjs.org/docs/hooks-reference.html#useref) hook allow access DOM, e.g. providing access to current form input value 
    * see typical [handleSubmit](https://reactjs.org/docs/forms.html#controlled-components) event form listener:
      ```
      handleSubmit(event) {
        event.preventDefault();
        // ...
      }
      ```
  * [useEffect](https://reactjs.org/docs/hooks-reference.html#conditionally-firing-an-effect) to execute imperative code that can be fire only when certain values are changed (or once by empty arrays as second argument, `useEffect(..., [])`); see also [Using the Effect Hook](https://reactjs.org/docs/hooks-effect.html)    
  * [context](https://reactjs.org/docs/context.html) provides a way to pass data through the component tree without having to pass props down manually at every level; 
    see also [useContext](https://reactjs.org/docs/hooks-reference.html#usecontext) hook
* third-party add-on
  * [React Router](https://reactrouter.com/en/main) to add routing to React application
    * [useHistory](https://v5.reactrouter.com/web/api/Hooks/usehistory) hook allow to navigate programmatically
* React alternatives
 * React: lean and focused component-based UI JavaScript library. Require community packages to build full SPA applicaroin (e.g. routing)
 * [Angular](https://angular.io/): complete component-based UI frameworks that use TypeScript language
 * [Vue](https://vuejs.org/): complete component-based UI frameworks that use TypeScript language; less big and complex than Angular
 * [Remix](https://remix.run/): similar to Next.JS but always with server-side rendering and more recent, better, etc. 

# Links

* [Remix](https://remix.run/) is a full stack web framework that lets you focus on the user interface and work back through web standards to deliver a fast, slick, and resilient user experience. People are gonna love using your stuff.
* React
  * [Image Upload](https://academind.com/tutorials/reactjs-image-upload) with React

[*Go to parent page*](../README.md)

*(Page mainly written in december 2022)*