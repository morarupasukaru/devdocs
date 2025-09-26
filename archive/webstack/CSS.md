# Cascading Style Sheets

[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) 
(Cascading Style Sheets) is a language to style and present HTML.

* [Concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference#Concepts) 
  * [syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/Syntax) and
    [comments](https://developer.mozilla.org/en-US/docs/Web/CSS/Comments)
  * [cascade](https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade),
    [inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/inheritance) and
    [specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)
  * [values, units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units), 
    [functional notation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Functions)
    and [data types](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Types) like
      [length](https://developer.mozilla.org/en-US/docs/Web/CSS/length),
      [percentage](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)
  * [shorthand properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Shorthand_properties)
  * [at-rules](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule) like
    [@import](https://developer.mozilla.org/en-US/docs/Web/CSS/@import),
    [@media](https://developer.mozilla.org/en-US/docs/Web/CSS/@media),
    [@supports](https://developer.mozilla.org/en-US/docs/Web/CSS/%40supports),
    [@keyframes](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes) or
    [@font-face](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face)
    * see [google fonts](https://fonts.google.com/) to easy embed font (@font-face used internally)
    * [web safe fonts](https://www.cssfontstack.com/)
  * [CSS variables](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)
  * [media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries)
  * [selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors) and
    [combinators](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Combinators)
  * [initial](https://developer.mozilla.org/en-US/docs/Web/CSS/initial_value),
    [computed](https://developer.mozilla.org/en-US/docs/Web/CSS/computed_value),
    [used](https://developer.mozilla.org/en-US/docs/Web/CSS/used_value),
    [actual](https://developer.mozilla.org/en-US/docs/Web/CSS/actual_value) values
  * [box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model)
    and [margin collapsing](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing)
    * hints
      * use `* { box-sizing: border-box; }` to ease lay out elements (see [box-sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing))
      * use [display](https://developer.mozilla.org/en-US/docs/Web/CSS/display) to sets whether an element is treated as a [block, inline or inline-block](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flow_layout)
      * see [inline](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements) vs
        [block-level](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements) HTML elements
      * see [Understanding the CSS box model for inline elements](https://hacks.mozilla.org/2015/03/understanding-inline-box-model/)
  * [containing block](https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_block)
  * [stacking](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context)
    and [block formatting](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context) contexts
  * [replaced elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Replaced_element)
  * [layouts](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout) like
    * [normal flow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flow_Layout)
    * [flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout), see also:
      * guides: [other MDN guide](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox),
        [a complete guide to flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/),
        [flexbox: basics & container](https://academind.com/tutorials/flexbox-basics-container) / 
        [flex-Items](https://academind.com/tutorials/flexbox-flex-items)
      * [flexbox froggy](https://flexboxfroggy.com/) learning game
    * [grids](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout), see also:
      * articles: [relationship of grid layout to other layout methods](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Relationship_of_Grid_Layout#:~:text=already%20be%20using.-,Grid%20and%20flexbox,columns%20at%20the%20same%20time.)
        and [grid vs flexbox](https://academind.com/tutorials/css-grid-vs-flexbox)
      * [a complete guide to css grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
      * [gridgarden](https://github.com/thomaspark/gridgarden/) learning game
    * [floats](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats) with [float](https://developer.mozilla.org/en-US/docs/Web/CSS/float) and [clear](https://developer.mozilla.org/en-US/docs/Web/CSS/clear) properties
    * [positioned layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning),
      see also [position property's article](https://academind.com/tutorials/the-position-property) 
  * [pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) css property
    [:active](https://developer.mozilla.org/en-US/docs/Web/CSS/:active),
    [:hover](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover),
    [:focus](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus),
    [a:link](https://developer.mozilla.org/en-US/docs/Web/CSS/:link),
    [a:visited](https://developer.mozilla.org/en-US/docs/Web/CSS/:visited),
    [:first-child](https://developer.mozilla.org/en-US/docs/Web/CSS/:first-child),
    [:last-child](https://developer.mozilla.org/en-US/docs/Web/CSS/:last-child),
    [:nth-child](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child),
    [:optional](https://developer.mozilla.org/en-US/docs/Web/CSS/:optional),
    [:required](https://developer.mozilla.org/en-US/docs/Web/CSS/:required),
    [:enabled](https://developer.mozilla.org/en-US/docs/Web/CSS/:enabled),
    [:disabled](https://developer.mozilla.org/en-US/docs/Web/CSS/:disabled),
    [:indeterminate](https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate),
    [:checked](https://developer.mozilla.org/en-US/docs/Web/CSS/:checked),
    [:not(...)](https://developer.mozilla.org/en-US/docs/Web/CSS/:not)
    * hint: use `:not()` with caution to exclude certain elements; it's better to write "positive" rules
  * [pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
  * [!important](https://developer.mozilla.org/en-US/docs/Web/CSS/important) not be used if possible, see [When Using !important is The Right Choice](https://css-tricks.com/when-using-important-is-the-right-choice/)
  * properties like
    * layout properties:
      [box-sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing),
      [min-width](https://developer.mozilla.org/en-US/docs/Web/CSS/min-width),
      [max-width](https://developer.mozilla.org/en-US/docs/Web/CSS/max-width),
      [min-height](https://developer.mozilla.org/en-US/docs/Web/CSS/min-height),
      [max-height](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height),
      [z-index](https://developer.mozilla.org/en-US/docs/Web/CSS/z-index),
      [position](https://developer.mozilla.org/en-US/docs/Web/CSS/position),
      [display](https://developer.mozilla.org/en-US/docs/Web/CSS/display),
      [margin](https://developer.mozilla.org/en-US/docs/Web/CSS/margin),
      [padding](https://developer.mozilla.org/en-US/docs/Web/CSS/padding),
      [justify-content](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content),
      [align-items](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items),
      [flex](https://developer.mozilla.org/en-US/docs/Web/CSS/flex),
      [flex-flow](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-flow),
      [order](https://developer.mozilla.org/en-US/docs/Web/CSS/order),
      [align-self](https://developer.mozilla.org/en-US/docs/Web/CSS/align-self),
      [align-content](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content),
      [visibility](https://developer.mozilla.org/en-US/docs/Web/CSS/visibility),
      [overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)
      * hint: `margin: auto` [horizontally center](https://developer.mozilla.org/en-US/docs/Web/CSS/margin#horizontal_centering) the element within its container
    * [font](https://developer.mozilla.org/en-US/docs/Web/CSS/font) shorthand property
    * text formatting:
      [text-align](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align),
      [vertical-align](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align),
      [letter-spacing](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing),
      [word-spacing](https://developer.mozilla.org/en-US/docs/Web/CSS/word-spacing),
      [line-height](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height),
      [text-indent](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent),
      [text-decoration](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration),
      [text-transform](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform)
    * others visual properties:
      [color](https://developer.mozilla.org/en-US/docs/Web/CSS/color),
      [background](https://developer.mozilla.org/en-US/docs/Web/CSS/background),
      [border](https://developer.mozilla.org/en-US/docs/Web/CSS/border),
      [border-radius](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius),
      [box-shadow](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow),
      [text-shadow](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow),
      [transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform),
      [filter](https://developer.mozilla.org/en-US/docs/Web/CSS/filter),
      [outline](https://developer.mozilla.org/en-US/docs/Web/CSS/outline)
    * animation properties:
      * [transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition) 
        used by [CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions) 
        module to create gradual transitions between the values of specific CSS properties
      * [animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
        used by [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) module
        that lets you animate the values of CSS properties over time, using [@keyframes](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)
      * see [animatable CSS properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) by CSS Transitions/Animations modules
* [CSSOM](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Object_Model)
  to manipulate CSS from JavaScript
  * [DocumentOrShadowRoot.styleSheets](https://developer.mozilla.org/en-US/docs/Web/API/DocumentOrShadowRoot/styleSheets)
    * [styleSheets[i].cssRules](https://developer.mozilla.org/en-US/docs/Web/API/CSSRuleList),
      [cssRules[i].cssText](https://developer.mozilla.org/en-US/docs/Web/API/CSSRule/cssText),
      [cssRules[i].selectorText](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleRule/selectorText)
  * [HTMLElement.style](https://developer.mozilla.org/en-US/docs/Web/API/ElementCSSInlineStyle/style),
    [HTMLElement.style.cssText](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/cssText)
  * [Element.className](https://developer.mozilla.org/en-US/docs/Web/API/Element/className),
    [Element.classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)
  * [CSSStyleSheet.insertRule()](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/insertRule),
    [CSSStyleSheet.deleteRule()](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/deleteRule)
* Other concepts
  * [Responsive design](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design)
    that allows websites work on different screen widths, resolutions, etc.
    * guides: [responsive web design basics](https://web.dev/articles/responsive-web-design-basics),
      [learn responsive design](https://web.dev/learn/design/),
      [responsive images](https://web.dev/articles/responsive-images),
      [responsive images in CSS](https://css-tricks.com/responsive-images-css/),
      [using media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
    * see [viewport](https://developer.mozilla.org/en-US/docs/Web/HTML/Viewport_meta_tag) HTML meta tag should be normally
      `<meta name="viewport" content="width=device-width, initial-scale=1" />`
  * [Mobile-first design](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Responsive/Mobile_first#google_searches_and_mobile_preference)
    to design websites for mobile (small screens) first and adapt then to desktop (larger screens)
  * [BEM (Block Element Modifier)](http://getbem.com/) as methodology to name/organize elements; 
    * see also [BEM 101](https://css-tricks.com/bem-101/)
    * see [BEM introduction](https://getbem.com/introduction/)
  * [CSS Modules](https://github.com/css-modules/css-modules) is a process in a build step that changes class names and selectors to be scoped 
  * [vendor prefix](https://developer.mozilla.org/en-US/docs/Glossary/Vendor_Prefix)
    * see [What CSS to prefix?](http://shouldiprefix.com/),
    * see [autoprefixer](https://github.com/postcss/autoprefixer) tool
* Preprocessor languages with [Sass](https://sass-lang.com/) ease development of CSS with features like:
    * [variables](https://sass-lang.com/documentation/variables) allow defining constants to reduce repetition
    * [nesting](https://sass-lang.com/guide/#nesting) and [nested properties](https://sass-lang.com/documentation/style-rules/declarations/#nesting)
      reduce repetition of same selectors
    * [maps](https://sass-lang.com/documentation/values/maps/#look-up-a-value) to have key-value pairs (e.g. colors)
      * other [helper functions](https://sass-lang.com/documentation/modules/) in modules like [map](https://sass-lang.com/documentation/modules/map/)
    * [partials](https://sass-lang.com/guide/#partials) contain little snippets of CSS that you can include in other Sass files (not generated into a CSS file)
    * [operators](https://sass-lang.com/guide/#operators) like +, -, *, etc.
    * [@media](https://sass-lang.com/documentation/at-rules/css/#media) allow nest media query (to keep media query close to impacted elements)
    * [inheritance](https://sass-lang.com/guide/#inheritance) with [@extend](https://sass-lang.com/documentation/at-rules/extend/) to share logic
    * [mixins](https://sass-lang.com/guide/#mixins) to groups CSS declarations that you want to reuse throughout your site
    * [parent Selector](https://sass-lang.com/documentation/style-rules/parent-selector/#advanced-nesting) `&` to refer to the outer selector in nesting
    * [scss](https://sass-lang.com/documentation/syntax/#scss) syntax as css (for .scss files) or [indented syntax](https://sass-lang.com/documentation/syntax/#the-indented-syntax) s (for .sass files)
    * [Less](https://lesscss.org/) (based on Javascript) is an alternative to [Sass](https://sass-lang.com/) (based on Ruby)
* Tutorials
  * [CSS basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics) 
    of [Getting started with the web](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web) (MDN)
  * [learn to style HTML using CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS) (MDN) 
  * [styling web forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Styling_web_forms),
    [advanced form styling](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling),
    [ui pseudo-classes](https://developer.mozilla.org/en-US/docs/Learn/Forms/UI_pseudo-classes) (MDN)
  * [beginner](https://htmldog.com/guides/css/beginner/), 
    [intermediate](https://htmldog.com/guides/css/intermediate/),
    [advanced](https://htmldog.com/guides/css/advanced/) tutorials (htmldog)
  * [getting started CSS](https://academind.com/tutorials/css-beginner-s-guide/) (academind)
  * [CSS - The Complete Guide 2023](https://www.udemy.com/course/css-the-complete-guide-incl-flexbox-grid-sass/) video course
  * [Advanced CSS and Sass: Flexbox, Grid, Animations and More!](https://www.udemy.com/course/advanced-css-and-sass/) video course
* Links
  * [CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference) ([MDN](https://developer.mozilla.org/en-US/))
  * [State of CSS 2022](https://2022.stateofcss.com/en-US)
    for summary of used tools, features, etc.
  * [State of CSS 2022](https://web.dev/blog/state-of-css-2022)
    for actual css features
  * [Web Almanac](https://almanac.httparchive.org/en/2022/) with reports of most used features of websites on the web
  * [Vanilla CSS vs Frameworks](https://academind.com/tutorials/vanilla-css-vs-frameworks)
* Tools / Frameworks / Libs
  * css frameworks:
    [Bootstrap](https://getbootstrap.com/),
    [Materialize](https://materializecss.com/),
    [Pure.css](https://purecss.io/),
    [Picnic CSS](https://picnicss.com/),
    [Skeleton](http://getskeleton.com/)
  * utility frameworks like [tailwind css](https://tailwindcss.com/) as compromise to css frameworks (no control) and vanilla css (all to do)
  * polyfills load on demand with [Modernizr](https://modernizr.com/)
    * see [HTML5 Cross Browser Polyfills](https://github.com/Modernizr/Modernizr/wiki/HTML5-Cross-Browser-Polyfills)
  * manual check of browser support with [caniuse](https://caniuse.com/)
  * css validation:
    [stylelint](https://stylelint.io/),
    [w3c CSS validation service](https://jigsaw.w3.org/css-validator/)
  * css minification:
    [purgecss](https://purgecss.com/),
    [clean-css](https://github.com/jakubpawlowicz/clean-css)
  * reset-library like [Normalize.css](https://necolas.github.io/normalize.css/) to makes browsers render all elements the same

[*Go to parent page*](README.md)

*(Page started in 2020; links checked on 04.03.2024)*
