# React

[React](https://reactjs.org/) is a client-side JavaScript library for building user interfaces.

* concepts
  * use [create-react-app](https://create-react-app.dev/) to create new react application
  * [JSX](https://reactjs.org/docs/introducing-jsx.html) : _html_ tags in javascript code
  * [component](https://reactjs.org/docs/components-and-props.html#function-and-class-components): provide custom html tag with a javascript function returning displayed content, e.g. html code
  * [props](https://reactjs.org/docs/components-and-props.html) are input parameters of the javascript function of the component
  * [handling events](https://reactjs.org/docs/handling-events.html) is very similar to handling events on DOM elements
  * [useState](https://reactjs.org/docs/hooks-reference.html#usestate) hook allow to re-render component/ui with new state/value;
    see also [Using the State Hook](https://reactjs.org/docs/hooks-state.html)
  * [css modules](https://create-react-app.dev/docs/adding-a-css-modules-stylesheet/) for having scoping component styles (require _.module.css_ suffix); see also [css module feature documentation](https://github.com/css-modules/css-modules)
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
  * [fragments](https://reactjs.org/docs/fragments.html) allow a component to return multiple elements
* third-party add-on
  * [React Router](https://reactrouter.com/en/main) to add routing to React application
    * [useHistory](https://v5.reactrouter.com/web/api/Hooks/usehistory) hook allow to navigate programmatically
* React vs alternative frameworks
  * React: lean and focused component-based UI JavaScript library. Require community packages to build full SPA applicaroin (e.g. routing)
  * [Angular](https://angular.io/): complete component-based UI frameworks that use TypeScript language
  * [Vue](https://vuejs.org/): complete component-based UI frameworks that use TypeScript language; less big and complex than Angular
* links:
  * [Image Upload](https://academind.com/tutorials/reactjs-image-upload) with React
  * [Next.js & React - The Complete Guide](https://www.udemy.com/course/nextjs-react-the-complete-guide/) video course
  * [React - The Complete Guide](https://www.udemy.com/course/react-the-complete-guide-incl-redux/) video course

[*Go to parent page*](../README.md)

*(Page mainly written in december 2022)*