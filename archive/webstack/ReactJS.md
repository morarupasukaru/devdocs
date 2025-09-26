# React

[React](https://react.dev/) is a client-side JavaScript library for building user interfaces.

* concepts
  * use [create-react-app](https://create-react-app.dev/) to create new react application
  * [JSX](https://react.dev/learn/writing-markup-with-jsx) : _html_ tags in javascript code
  * [component](https://react.dev/learn/your-first-component): provide custom html tag with a javascript function returning displayed content, e.g. html code
  * [props](https://react.dev/learn/passing-props-to-a-component) are input parameters of the javascript function of the component
  * [handling events](https://react.dev/learn/responding-to-events) is very similar to handling events on DOM elements
  * [useState](https://react.dev/reference/react/useState) hook allow to re-render component/ui with new state/value;
    see also [State: A Component's Memory](https://react.dev/learn/state-a-components-memory)
  * [css modules](https://create-react-app.dev/docs/adding-a-css-modules-stylesheet/) for having scoping component styles (require _.module.css_ suffix); see also [css module feature documentation](https://github.com/css-modules/css-modules)
  * [rendering lists](https://react.dev/learn/rendering-lists) use map javascript array function to map data to React tag component (JSX element)
  * Forms
    * [useRef](https://react.dev/reference/react/useRef) hook allow access DOM, e.g. providing access to current form input value 
    * see typical [handleSubmit](https://react.dev/reference/react-dom/components/input#reading-the-input-values-when-submitting-a-form) event form listener:
      ```
      handleSubmit(event) {
        event.preventDefault();
        // ...
      }
      ```
  * [useEffect](https://react.dev/reference/react/useEffect) to execute imperative code that can be fire only when certain values are changed (or once by empty arrays as second argument, `useEffect(..., [])`)   
  * [context](https://react.dev/learn/passing-data-deeply-with-context) provides a way to pass data through the component tree without having to pass props down manually at every level; 
    see also [useContext](https://react.dev/reference/react/useContext) hook
  * [fragments](https://react.dev/reference/react/Fragment) allow a component to return multiple elements
  * [createPortal](https://react.dev/reference/react-dom/createPortal) used to render children into a DOM node that exists outside the DOM hierarchy of the parent component
    * could be usefull to render component corresponding to its HTML semantics instead of nested in the generated HTML code 
* React vs alternative frameworks
  * React: lean and focused component-based UI JavaScript library. Require community packages to build full SPA applicaroin (e.g. routing)
  * [Angular](https://angular.io/): complete component-based UI frameworks that use TypeScript language
  * [Vue](https://vuejs.org/): complete component-based UI frameworks that use TypeScript language; less big and complex than Angular
* libraries
  * [React Router](https://reactrouter.com/en/main) to add routing to React application
    * [useNavigate](https://reactrouter.com/en/main/hooks/use-navigate) hook allow to navigate programmatically
  * [react-markdown](https://remarkjs.github.io/react-markdown/): React component to render markdown
  * [React Syntax Highlighter](https://github.com/react-syntax-highlighter/react-syntax-highlighter)
  : Syntax highlighting React component
  * [React Icons](https://react-icons.github.io/react-icons) for popular icons
* links:
  * [Image Upload](https://academind.com/tutorials/reactjs-image-upload) with React
  * [Next.js & React - The Complete Guide](https://www.udemy.com/course/nextjs-react-the-complete-guide/) video course
  * [React - The Complete Guide](https://www.udemy.com/course/react-the-complete-guide-incl-redux/) video course

[*Go to parent page*](README.md)

*(Page mainly written in december 2022; links checked on 26.02.2024)*
