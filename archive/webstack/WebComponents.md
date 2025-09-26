# Web Components

[Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components) is used to develop custom web elements

* [Native Web Components](#Native-Web-Components)
* [Stencil](Stencil.md) is a compiler that generates Web Components in plain JavaScript
* [Angular Elements](https://angular.io/guide/elements) turn Angular Components as [Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components)

[*Go to parent page*](README.md)


## Native Web Components

* Concepts
    * [Custom elements](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements),
      see also [google article](https://web.dev/articles/custom-elements-v1/)
        * [Autonomous custom elements](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements#Autonomous_custom_elements)
        * [Customized built-in elements](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements#Customized_built-in_elements)
    * [Shadow DOM](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM),
      see also [google article](https://web.dev/articles/shadowdom-v1/)
    * [HTML templates](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_templates_and_slots)
        * [slots](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_templates_and_slots#Adding_flexibility_with_slots)
          are placeholders inside your component that users can fill with their own markup,
          see also [google article](https://web.dev/articles/shadowdom-v1/#slots)
        * named slots are specific holes in your shadow DOM that users reference by name
* Basics
    * Web Components vs Frameworks: Web components are just components; there is no routing, state management, etc.
        * a whole single page application cannot be developed with web components without external libraries
    * browser support is available [www.webcomponents.org](https://www.webcomponents.org/) or
      [caniuse.com](https://caniuse.com/?search=components)
    * [polyfills](https://www.webcomponents.org/polyfills) are available for browser without native support
    * light DOM means normal DOM
    * example of autonomous custom elements, `index.html`:
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Web Components</title>
    <script src="info-toggle.js"></script>

  </head>
  <body>
    <info-toggle is-visible="true">test</info-toggle>
    <info-toggle></info-toggle>
  </body>
</html>
```
* `info-toggle.js`:
```javascript
class InfoToggle extends HTMLElement {
    constructor() {
        super();
        this._isVisible = false;
        this.attachShadow({mode: 'open'});
        this.shadowRoot.innerHTML = `
            <style>
                #info-box {
                    display: none;
                }
            </style>
            <button>Show</button>
            <p id="info-box">
                <slot>default value</slot>
            </p>
        `;

        this._toggleButton = this.shadowRoot.querySelector('button');
        this._infoBox = this.shadowRoot.querySelector('#info-box');
        this._toggleButton.addEventListener('click', this._toggleInfoBox.bind(this));
    }

    connectedCallback() {
        // access to light DOM and attributes
        if (this.hasAttribute('is-visible')) {
            if (this.getAttribute('is-visible') === 'true') {
                this._toggleInfoBox();
            }
        }
    }

    disconnectedCallback() {
        // clean up
        this._toggleButton.removeEventListener('click', this._toggleInfoBox);
    }
    
    _toggleInfoBox() {
        this._isVisible = !this._isVisible;
        this._infoBox.style.display = this._isVisible ? 'block' : 'none';
        this._toggleButton.textContent = this._isVisible ? 'Hide' : 'Show';
    }
}

customElements.define('info-toggle', InfoToggle);
```
* Styling
    * slot content defined in DOM can be styled in light DOM itself
    * [::slotted()](https://developer.mozilla.org/en-US/docs/Web/CSS/::slotted) CSS pseudo-element
      is used to style slot content from shadow DOM
        * see also [Styling distributed nodes](https://web.dev/articles/shadowdom-v1#styling_distributed_nodes)
        * only first-level element of the slot can be styled from within the shadow DOM
        * child elements of the slot must be styled from the light DOM
    * [:host](https://developer.mozilla.org/en-US/docs/Web/CSS/:host) selector is used to style
      element that hosts the component in the shadow DOM
    * [:host()](https://developer.mozilla.org/en-US/docs/Web/CSS/:host()) selector is used to style
      element that hosts the component in the shadow DOM if a css selector on the host component matches in the light DOM
    * [:host-context()](https://developer.mozilla.org/en-US/docs/Web/CSS/:host-context) selector
      looks for a CSS class in any ancestor of the component host element, up to the document root in the light DOM
    * [CSS variables](https://developer.mozilla.org/en-US/docs/Web/CSS/--*) and
      [var()](https://developer.mozilla.org/en-US/docs/Web/CSS/var()#Using_a_custom_property_set_on_root)
      CSS function can be used to customized styles of web components or provide themes
        * excepted CSS variables of web components / themes must document
        * a CSS variable is defined in the light DOM, e.g.
  ```css
  :root {
      --main-bg-color: pink;
  }
  ```
    * value of the CSS variable is read in the style of shadom DOM, e.g.
  ```css
  :host {
      background-color: var(--main-bg-color, blue); /* fallback value blue as second parameter */
  }
  ```
* [Life cycle callbacks](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements#Using_the_lifecycle_callbacks)
    * constructor: performs basic initialization
    * `connectedCallback()`: called every time the element is inserted into the DOM. Useful for
      running setup code (e.g. fetching resources)
    * `disconnectedCallback()`: called every time the element is removed from the DOM. Useful for
      running clean up code.
    * `attributeChangedCallback()`: called when an observed attribute
      (defined in a static get `observedAttributes` method) has been added, removed, updated, or replaced
* Tips
    * It's a good practise to keep shadow & light DOM updates inside a single `_render()` method
      that acts differently depending on states
    * [defining an element's JavaScript API](https://web.dev/articles/custom-elements-v1/#defining_an_elements_javascript_api):
      to abstract complexity, an API based on public methods & properties of the class of a web component can be defined
    * slots can be queries in web component with following css query:
  ```javascript
  const slots = this.shadowRoot.querySelectorAll('slot'); // or with id
  ```
    * [`slotchange`](https://developers.google.com/web/fundamentals/web-components/shadowdom#slots)
      event fires when a slot's distributed nodes changes
    * [slot.assignedNodes()](https://web.dev/articles/shadowdom-v1/#what_elements_are_being_rendering_in_a_slot) :
      find which elements the slot is rendering
* Event
    * event listener can be configured in javascript of the DOM
```javascript
    const webElement = document.querySelector('my-component');
    webElement.addEventListener('custom', () => {
        console.log('custom event happened');
    });
```  
* event can be dispatch from web component in two ways:
    * [custom events](https://web.dev/articles/shadowdom-v1/#using_custom_events)
      can be used to inform event to users of web components
    * alternative is to dispatch event on host element self; event in that case will be fire in
      the light DOM
```javascript
    class MyComponent extends HTMLElement {
       ... 
       dispatchEvent() {
           const customEvent = new Event('custom');
           this.dispatchEvent(customEvent);
       }
       ...
```

[*Go to top*](#Web-Components)

*(Page mainly written in september 2020; links checked on 19.02.2024)*
