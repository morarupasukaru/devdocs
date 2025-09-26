# Hypertext Markup Language

[HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) (Hypertext Markup Language) defines the 
meaning and structure of web content. 
"Hypertext" refers to links that connect web pages to one another, either within a single website or 
between websites.

* [Basic HTML example](#Basic-HTML-example)
* Most important [HTML elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Element) by categories:
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
      * [viewport](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta/name#standard_metadata_names_defined_in_other_specifications):
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
    * see [tutorial about iframes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Other_embedding_technologies#Iframes_in_detail)
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
    * see [Web Components](WebComponents.md) in devdocs
* Topics
  * Block vs inline elements:
    * HTML elements are usually "inline" or "block-level" elements:
      * [inline elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements)
      occupies only the space bounded by the tags that define it.
    * [block-level elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements)
      occupies the entire space of its parent element (container), thereby creating a "block."
  * [Quirks Mode and Standards Mode](https://developer.mozilla.org/en-US/docs/Web/HTML/Quirks_Mode_and_Standards_Mode)
    * In quirks mode, layout emulates nonstandard behavior in Navigator 4 and Internet Explorer 5.
    * In full standards mode, the behavior is the behavior described by the HTML and CSS specifications.
    * **tip**: to ensure that your page uses full standards mode with HTML5, add `<!DOCTYPE html>` 
      that the first line of the doc (without comment before it).
  * [Responsive images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)
  * [Vector graphics](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Adding_vector_graphics_to_the_Web)
  * [`lang` attribute](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#Setting_the_primary_language_of_the_document)
  * [`data-*` attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes)
  * [Optimizations of HTML loading](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Author_fast-loading_HTML_pages)
  * [Favicon](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#Adding_custom_icons_to_your_site) ("favorites icon") is displayed in the browser's address bar
    * see [Cheat-sheet](https://github.com/audreyfeldroy/favicon-cheat-sheet), [realfavicongenerator](https://realfavicongenerator.net/) and its [FAQ](https://realfavicongenerator.net/faq#.X28FlWgzZPY)
  * [HTML Validation](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Debugging_HTML#HTML_validation) 
    * with [w3c HTML validation service](https://validator.w3.org/)
      or [Nu Html Checker](https://validator.github.io/validator/)
      (see [grunt-html](https://www.npmjs.com/package/grunt-html)
      for [grunt](https://gruntjs.com/))
  * HTML minification 
    * with [html-minifier](https://github.com/kangax/html-minifier) 
      (see [grunt-contrib-htmlmin](https://www.npmjs.com/package/grunt-contrib-htmlmin) 
      for [grunt](https://gruntjs.com/))
* References
  * [HTML Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference)
  * [Elements reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
  * [Attributes reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes)
  * [Global attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes) (common to all HTML elements)
  * [Link types](https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types)
  * [Date formats](https://developer.mozilla.org/en-US/docs/Web/HTML/Date_and_time_formats)
  * [Special characters](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started#Entity_references_Including_special_characters_in_HTML) (like `?&amp;` for &)
* Tutorials 
  * [basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics), 
    [tutorials](https://developer.mozilla.org/en-US/docs/Learn/HTML), 
    [tables](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables), 
    [forms](https://developer.mozilla.org/en-US/docs/Learn/Forms)
  * [beginner](https://htmldog.com/guides/html/beginner/), 
    [intermediate](https://htmldog.com/guides/html/intermediate/), 
    [advanced](https://htmldog.com/guides/html/advanced/) tutorials
    (from [htmldog](https://htmldog.com/))
  * [getting started HTML5](https://academind.com/tutorials/html-beginner-s-guide), see also 
    [part 2: CSS](https://academind.com/tutorials/css-beginner-s-guide), 
    [part 3: JavaScript](https://academind.com/tutorials/javascript-beginner-s-guide)

[*Go to parent page*](../../README.md)


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
* `<!DOCTYPE html>`: is required to ensure that the browser will work in [standard mode](https://developer.mozilla.org/en-US/docs/Web/HTML/Quirks_Mode_and_Standards_Mode)
* [`<meta charset="utf-8">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta): 
  declares the document's character encoding, UTF-8 is the only valid encoding for HTML5
* [`<title>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title): set title of the 
  page (displayed in browser's title bar or a page's tab)
* see also [Anatomy of an HTML document](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started#Anatomy_of_an_HTML_document)

[*Go to parent page*](README.md)

*(Page mainly written in september 2020; links checked on 03.03.2024)*
