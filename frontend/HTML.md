# Hypertext Markup Language

[HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) (Hypertext Markup Language) defines the 
meaning and structure of web content. 
"Hypertext" refers to links that connect web pages to one another, either within a single website or 
between websites.

* [Basic HTML example](#Basic-HTML-example)
* [HTML elements](#HTML-elements)
* Tutorials 
  * [basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics), 
    [tutorials](https://developer.mozilla.org/en-US/docs/Learn/HTML), 
    [tables](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables), 
    [forms](https://developer.mozilla.org/en-US/docs/Learn/Forms)
  * [beginner](https://www.htmldog.com/guides/html/beginner/), 
    [intermediate](https://www.htmldog.com/guides/html/intermediate/), 
    [advanced](https://www.htmldog.com/guides/html/advanced/) tutorials
  * [getting started HTML5](https://academind.com/learn/html/beginner-s-guide/), see also 
    [part 2: CSS](https://academind.com/learn/css/beginner-s-guide/), 
    [part 3: JavaScript](https://academind.com/learn/javascript/javascript-beginner-s-guide/)
* Topics
  * [Block vs inline elements](#Block-vs-inline-elements)
  * [Quirks vs standards mode](#Quirks-vs-standards-mode)
  * [iframe](#iframe)
  * [Web Components](#Web-Components)
  * [Responsive images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)
  * [Vector graphics](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Adding_vector_graphics_to_the_Web)
  * [`lang` attribute](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#Setting_the_primary_language_of_the_document)
  * [`data-*` attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes)
  * [Optimizations of HTML loading](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Author_fast-loading_HTML_pages)
  * [Accessibility](./Accessibility.md)
  * [Favicon](#Favicon)
  * [HTML Validation](#HTML-Validation)
  * [HTML Minification](#HTML-Minification)
* References
  * [HTML Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference)
  * [Elements reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
  * [Attributes reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes)
  * [Global attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes) (common to all HTML elements)
  * [Link types](https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types)
  * [Date formats](https://developer.mozilla.org/en-US/docs/Web/HTML/Date_and_time_formats)
  * [Special characters](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started#Entity_references_Including_special_characters_in_HTML) (like `?&amp;` for &)

*(Page mainly written in september 2020)*

[*Go to parent page*](../README.md)


## Basic HTML example

``` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My test page</title>
  </head>
  <body>
    <!-- a comment -->
    <p>This is my page</p>
  </body>
</html>
```

Notes:
* `<!DOCTYPE html>`: is required to ensure that the browser will work in [standard mode](#Quirks-vs-standards-mode)
* [`<meta charset="utf-8">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta): 
  declares the document's character encoding, UTF-8 is the only valid encoding for HTML5
* [`<title>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title): set title of the 
  page (displayed in browser's title bar or a page's tab)
* see also [Anatomy of an HTML document](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started#Anatomy_of_an_HTML_document)

[*Go to top*](#Hypertext-Markup-Language)


## HTML elements

List of most important [HTML elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Element) by categories:
* *roots*
  * [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html): 
    root element of an HTML document
  * [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body): 
    represents the content of an HTML document
* [metadata](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Document_metadata)
  * [`<head>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head): 
    container of `title` and other metadata tags
  * [`<title>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title): 
    defines the document's title that is shown in a browser's title bar or a page's tab.
  * [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link): 
    used to link to stylesheets and favicon
  * [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style): 
    contains style information for a document, or part of a document
  * [`<base>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base): 
    specifies the base URL to use for all relative URLs
  * [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta): 
    represents metadata such as
    * charset: `<meta charset="utf-8">`
    * page description: `<meta name="description" content="...">`
    * [viewport](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta/name): 
      gives hints about the size of the initial size of the viewport. Used by mobile devices only.
* [content sectioning](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Content_sectioning)
  * [`<h1>` - `<h6>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements): 
    represent six levels of section headings
  * [`<main>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/main): 
    represents main content of `<body>`
  * [`<nav>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav): 
    represents a section with navigation links
  * [`<header>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header): 
    represents introductory  for its nearest element
  * [`<footer>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer): 
    represents a footer for its nearest element
  * [`<aside>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/aside): 
    used mainly for sidebars
* [text content](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Text_content)
  * [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div): 
    generic container for flow content
  * [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul): 
    represents an unordered list of items
  * [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li): 
    represent an item in a list
  * [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p): 
    represents a paragraph
* [inline text semantics](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Inline_text_semantics)
  * [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a): 
    anchor element, with its [href](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#href) 
    attribute, creates a hyperlink (e.g. to a 
    [document fragment](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#Linking_to_an_element_on_the_same_page))
  * [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span): 
    generic inline container for phrasing content, which does not inherently represent anything
* [image and multimedia](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Image_and_multimedia)
  * [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img): 
    embeds an image into the document
* [embedded content](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Embedded_content)
  * [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe): 
    represents a nested [browsing context](https://developer.mozilla.org/en-US/docs/Glossary/browsing_context), 
    embedding another HTML page into the current one
* [scripting](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Scripting)
  * [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script): 
    used to embed executable code or data; typically JavaScript
* [table content](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Table_content)
  * [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table): 
    represents tabular data
  * [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr): 
    defines a row of cells in a table. row's cells can a mix of `<td>` (data cell) and `<th>` (header cell)
  * [`<th>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/th): 
    defines a cell as header of a group of table cells
  * [`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td): 
    defines a cell of a table that contains data
* [forms](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Forms)
  * [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form): 
    represents a document section containing interactive controls for submitting information
  * [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button): 
    represents a clickable button
  * [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input): 
    is used to create interactive controls for web-based forms in order to accept data from the user
  * [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label): 
    represents a caption for an item in a user interface
  * [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select): 
    represents a control that provides a menu of options
  * [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option): 
    is used to define an item of a 
    [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), 
    [`<optgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/optgroup) or 
    [`<datalist>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/datalist)
  * [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea): 
    represents a multi-line plain-text editing control
* [web components](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Web_Components)
  * [`<template>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template): 
    is a mechanism for holding HTML that is not to be rendered immediately when a page is loaded 
    but may be instantiated subsequently during runtime using JavaScript
  * [`<slot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/slot): 
    is a placeholder inside a web component that you can fill with your own markup

[*Go to top*](#Hypertext-Markup-Language)


## Block vs inline elements

HTML elements are usually "inline" or "block-level" elements:
* [inline elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements) 
  occupies only the space bounded by the tags that define it. 
* [block-level elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements) 
  occupies the entire space of its parent element (container), thereby creating a "block."

[*Go to top*](#Hypertext-Markup-Language)


## Quirks vs standards mode
* In quirks mode, layout emulates nonstandard behavior in Navigator 4 and Internet Explorer 5.
* In full standards mode, the behavior is the behavior described by the HTML and CSS specifications.

To ensure that your page uses full standards mode with HTML5, add `<!DOCTYPE html>` that the first 
line of the doc (without comment before it). 

see [Quirks Mode and Standards Mode](https://developer.mozilla.org/en-US/docs/Web/HTML/Quirks_Mode_and_Standards_Mode)

[*Go to top*](#Hypertext-Markup-Language)


## iframe

[`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) represents a 
nested [browsing context](https://developer.mozilla.org/en-US/docs/Glossary/browsing_context), 
embedding another HTML page into the current one.
* [Tutorial about iframes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Other_embedding_technologies#Iframes_in_detail)
* see [Broadcast Channel API - Channel Messaging API](./WebAPIs.md#Broadcast-Channel-API---Channel-Messaging-API) 
  in WebAPIs

[*Go to top*](#Hypertext-Markup-Language)


## Web Components

[Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components) are custom web elements

* Concepts
  * [Custom elements](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements), 
    see also [google article](https://developers.google.com/web/fundamentals/web-components/customelements)
    * [Autonomous custom elements](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements#Autonomous_custom_elements)
    * [Customized built-in elements](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements#Customized_built-in_elements)
  * [Shadow DOM](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM), 
    see also [google article](https://developers.google.com/web/fundamentals/web-components/shadowdom)
  * [HTML templates](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_templates_and_slots)
    * [slots](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_templates_and_slots#Adding_flexibility_with_slots) 
      are placeholders inside your component that users can fill with their own markup, 
      see also [google article](https://developers.google.com/web/fundamentals/web-components/shadowdom#slots)
    * named slots are specific holes in your shadow DOM that users reference by name
* Basics
  * Web Components vs Frameworks: Web components are just components; there is no routing, state management, etc.
    * a whole single page application cannot be developed with web components without external libraries
  * browser support is available [www.webcomponents.org](https://www.webcomponents.org/) or 
    [caniuse.com](https://caniuse.com/?search=components)
  * [polyfills](https://www.webcomponents.org/polyfills) are available for browser without native support
  * light DOM means normal DOM
  * example of autonomous custom elements, `index.html`:
```
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
```
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
    * see also [Styling distributed nodes](https://developers.google.com/web/fundamentals/web-components/shadowdom#stylinglightdom)
    * only first-level element of the slot can be styled from within the shadow DOM
    * child elements of the slot must be styled from the light DOM
  * [:host](https://developer.mozilla.org/en-US/docs/Web/CSS/:host) selector is used to style 
    element that hosts the component in the shadow DOM
  * [:host()](https://developer.mozilla.org/en-US/docs/Web/CSS/:host()) selector is used to style 
    element that hosts the component in the shadow DOM if a css selector on the host component matches in the light DOM
  * [:host-context()](https://developer.mozilla.org/en-US/docs/Web/CSS/:host-context()) selector 
    looks for a CSS class in any ancestor of the component host element, up to the document root in the light DOM
  * [CSS variables](https://developer.mozilla.org/en-US/docs/Web/CSS/--*) and 
    [var()](https://developer.mozilla.org/en-US/docs/Web/CSS/var()#Using_a_custom_property_set_on_root) 
    CSS function can be used to customized styles of web components or provide themes
     * excepted CSS variables of web components / themes must documented
     * a CSS variable is defined in the light DOM, e.g.
  ```
  :root {
      --main-bg-color: pink;
  }
  ```
     * value of the CSS variable is read in the style of shadom DOM, e.g.
  ```
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
  * [defining an element's JavaScript API](https://developers.google.com/web/fundamentals/web-components/customelements#jsapi): 
    to abstract complexity, an API based on public methods & properties of the class of a web component can be defined 
  * slots can be queries in web component with following css query:
  ```
  const slots = this.shadowRoot.querySelectorAll('slot'); // or with id
  ```
  * [`slotchange`](https://developers.google.com/web/fundamentals/web-components/shadowdom#slots) 
    event fires when a slot's distributed nodes changes
  * [slot.assignedNodes()](https://developers.google.com/web/fundamentals/web-components/shadowdom#slotnodes) : 
    find which elements the slot is rendering
* Event
  * event listener can be configured in javascript of the DOM
```  
    const webElement = document.querySelector('my-component');
    webElement.addEventListener('custom', () => {
        console.log('custom event happened');
    });
```  
  * event can be dispatch fro web component in two ways:
     * [custom events](https://developers.google.com/web/fundamentals/web-components/shadowdom#customevents) 
       can be used to inform event to users of web components
     * alternative is to dispatch event on host element self; event in that case will be fire in 
       the light DOM
```
    class MyComponent extends HTMLElement {
       ... 
       dispatchEvent() {
           const customEvent = new Event('custom');
           this.dispatchEvent(customEvent);
       }
       ...
```

[*Go to top*](#Hypertext-Markup-Language)


## Favicon

Favicon ("favorites icon") is displayed in the browser's address bar.

* [Tutorial about favicon](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#Adding_custom_icons_to_your_site)
* [Cheat-sheet](https://github.com/audreyfeldroy/favicon-cheat-sheet)
* Tool [realfavicongenerator](https://realfavicongenerator.net/) and the [FAQ](https://realfavicongenerator.net/faq#.X28FlWgzZPY)

[*Go to top*](#Hypertext-Markup-Language)


## HTML Validation

* [Tutorial about HTML Validation](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Debugging_HTML#HTML_validation)
* Example of tools
  * [w3c HTML validation service](https://validator.w3.org/)
  * [Nu Html Checker](https://validator.github.io/validator/) 
    (see [grunt-html](https://www.npmjs.com/package/grunt-html) 
    for a [grunt](https://gruntjs.com/) integration)

*Tools are becoming quick obsolete, please find appropriate tools during development*

[*Go to top*](#Hypertext-Markup-Language)


## HTML Minification

* Example of tools
  * [html-minifier](https://github.com/kangax/html-minifier) 
    (see [grunt-contrib-htmlmin](https://www.npmjs.com/package/grunt-contrib-htmlmin) 
    for a [grunt](https://gruntjs.com/) integration)

*Tools are becoming quick obsolete, please find appropriate tools during development*

[*Go to top*](#Hypertext-Markup-Language)
