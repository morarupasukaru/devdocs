# Cascading Style Sheets

[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) 
(Cascading Style Sheets) is a language to style and present HTML.

* [Concepts](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference#Concepts) 
  * [syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/Syntax)
  * [cascade](https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade)
  * [inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/inheritance)
  * [specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)
  * [shorthand properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Shorthand_properties)
  * [at-rules](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule) and
    [@import](https://developer.mozilla.org/en-US/docs/Web/CSS/@import)
  * [values, units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)
    and [functional notation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Functions)
  * [selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors) TODO
  * [media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries)
  * [actual](https://developer.mozilla.org/en-US/docs/Web/CSS/actual_value) vs
    [computed](https://developer.mozilla.org/en-US/docs/Web/CSS/computed_value) vs
    [initial](https://developer.mozilla.org/en-US/docs/Web/CSS/initial_value) vs
    [resolved](https://developer.mozilla.org/en-US/docs/Web/CSS/resolved_value) vs
    [specified](https://developer.mozilla.org/en-US/docs/Web/CSS/specified_value) vs
    [used](https://developer.mozilla.org/en-US/docs/Web/CSS/used_value) values
  * layout
    * [block formatting context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context)
    * [box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model)
    * [containing block](https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_block)
    * [layout modes](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_mode):
      [normal flow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flow_Layout),
      [table layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Table),
      [float layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats),
      [positioned layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning),
      [multi-column layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Columns),
      [flexible box layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout),
      [grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
      * see also [Relationship of grid layout to other layout methods](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Relationship_of_Grid_Layout#:~:text=already%20be%20using.-,Grid%20and%20flexbox,columns%20at%20the%20same%20time.)
    * [margin collapsing](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing)
    * [replaced elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Replaced_element)
    * [stacking context](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context)
    * [visual formatting model](https://developer.mozilla.org/en-US/docs/Web/CSS/Visual_formatting_model)
  * [comments](https://developer.mozilla.org/en-US/docs/Web/CSS/Comments)
  * animations
    * [css transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions)
      is a module of CSS that lets you create gradual transitions between the values of specific CSS properties
    * [css animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations)
      is a module of CSS that lets you animate the values of CSS properties over time, using keyframes
      * see [animatable CSS properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties)
  * popular [pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes):
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
    [:checked](https://developer.mozilla.org/en-US/docs/Web/CSS/:checked)
  * [pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
  * [combinators](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Combinators)
  * popular CSS properties:
    * layout properties:
      [box-sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing),
      [min-width](https://developer.mozilla.org/en-US/docs/Web/CSS/min-width),
      [max-width](https://developer.mozilla.org/en-US/docs/Web/CSS/max-width),
      [min-height](https://developer.mozilla.org/en-US/docs/Web/CSS/min-height),
      [max-height](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height)
      [length](https://developer.mozilla.org/en-US/docs/Web/CSS/length),
      [percentage](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage),
      [z-index](https://developer.mozilla.org/en-US/docs/Web/CSS/z-index),
      [position](https://developer.mozilla.org/en-US/docs/Web/CSS/position),
      [top](https://developer.mozilla.org/en-US/docs/Web/CSS/top),
      [right](https://developer.mozilla.org/en-US/docs/Web/CSS/right),
      [bottom](https://developer.mozilla.org/en-US/docs/Web/CSS/bottom),
      [left](https://developer.mozilla.org/en-US/docs/Web/CSS/left),
      [display](https://developer.mozilla.org/en-US/docs/Web/CSS/display),
      [margin](https://developer.mozilla.org/en-US/docs/Web/CSS/margin),
      [padding](https://developer.mozilla.org/en-US/docs/Web/CSS/padding),
      [flex-direction;](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction),
      [justify-content](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content),
      [align-items](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items),
      [flex](https://developer.mozilla.org/en-US/docs/Web/CSS/flex),
      [flex-wrap](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-wrap),
      [flex-flow](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-flow),
      [order](https://developer.mozilla.org/en-US/docs/Web/CSS/order),
      [align-self](https://developer.mozilla.org/en-US/docs/Web/CSS/align-self),
      [align-content](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content)
    * font properties:
      [font](https://developer.mozilla.org/en-US/docs/Web/CSS/font),
      [font-size](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size),
      [font-family](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family),
      [font-weight](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight),
      [font-style](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style),
      [font-face](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face)
      * see [google fonts](https://fonts.google.com/) allow to easy embed font (@font-face is used internally in downloaded google css)
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
      [background-color](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color),
      [background-image](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image),
      [border](https://developer.mozilla.org/en-US/docs/Web/CSS/border),
      [border-radius](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius),
      [box-shadow](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow),
      [text-shadow](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow),
    * animation properties:
      [transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform),
      [transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition),
      [animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation),
      [@keyframes](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)
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
  * [Mobile-first design](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Responsive/Mobile_first#google_searches_and_mobile_preference)
    to design websites for mobile (small screens) first and adapt then to desktop (larger screens)
  * Preprocessor languages [Sass](https://sass-lang.com/) or [Less](https://lesscss.org/)
    alternatives to vanilla CSS with additional features like
    * [variables](https://sass-lang.com/documentation/variables) allow defining constants to reduce repetition
    * [nesting](https://sass-lang.com/documentation/style-rules#nesting) reduce repetition of same selectors
  * [BEM - Block Element Modifier](http://getbem.com/) as methodology to name/organize elements
* Tools / Frameworks / Libs
  * frameworks:
    [Bootstrap](https://getbootstrap.com/),
    [Materialize](https://materializecss.com/),
    [Pure.css](https://purecss.io/),
    [Picnic CSS](https://picnicss.com/),
    [Skeleton](http://getskeleton.com/)
  * utility frameworks: [tailwind css](https://tailwindcss.com/)
  * icons:
    [Feather](https://feathericons.com/),
    [Line Awesome](https://icons8.com/line-awesome),
    [fontawesome](https://fontawesome.com/),
    [Material Design Icons](https://materialdesignicons.com/),
    [Noun Project](https://thenounproject.com/)
  * embedded fonts: [google fonts](https://fonts.google.com/)
  * feature detection: [Modernizr](https://modernizr.com/)
  * css validation:
    [stylelint](https://stylelint.io/),
    [w3c CSS validation service](https://jigsaw.w3.org/css-validator/)
  * css minification:
    [purgecss](https://purgecss.com/),
    [clean-css](https://github.com/jakubpawlowicz/clean-css)
  * css normalize: [Normalize.css](https://necolas.github.io/normalize.css/)
* Links
  * [CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference) from [MDN](https://developer.mozilla.org/en-US/)
  * [State of CSS 2021](https://2021.stateofcss.com/en-US/technologies)
    for summary of used tools, features, etc.
  * [State of CSS 2022](https://web.dev/state-of-css-2022/)
    for actual css features (google article)
  * [Web Almanac](https://almanac.httparchive.org/en/2021/) with reports of most used features of websites on the web
  * [Vanilla CSS vs Frameworks](https://academind.com/learn/css/understanding-css/vanilla-css-vs-frameworks/)
    article
* Tutorials
  * general
    * [beginner](https://htmldog.com/guides/css/beginner/), 
      [intermediate](https://htmldog.com/guides/css/intermediate/),
      [advanced](https://htmldog.com/guides/css/advanced/) tutorials
    * [getting started CSS](https://academind.com/learn/css/beginner-s-guide/) 
  * [learn CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS) MDN courses
    * [CSS first steps](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps)
    * [CSS building blocks](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks)
    * [Styling text](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text)
    * [CSS layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout)
    * [Styling web forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Styling_web_forms),
      [Advanced form styling](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling),
      [UI pseudo-classes](https://developer.mozilla.org/en-US/docs/Learn/Forms/UI_pseudo-classes)
    * [Using CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
  * layout 
    * [The Position Property](https://academind.com/learn/css/understanding-css/the-position-property/) article
    * flexbox
      * [CSS Grid vs Flexbox](https://academind.com/tutorials/css-grid-vs-flexbox) article
      * see [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) (from [CSS-TRICKS](https://css-tricks.com/))
      * see [Basic concepts of flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox) and other guides (from [MDN](https://developer.mozilla.org/en-US/))
      * [Flexbox: Basics & Container](https://academind.com/learn/css/understanding-css/flexbox-basics-container/), [part 2](https://academind.com/learn/css/understanding-css/flexbox-flex-items/) (from [academind](https://academind.com/))
      * [Flexbox CSS In 20 Minutes](https://www.youtube.com/watch?v=JJSoEo8JSnc&list=PLillGF-RfqbZTASqIqdvm1R5mLrQq79CU&index=4) (from (TraversyMedia)[https://www.traversymedia.com/])
      * [Flexbox Froggy](https://flexboxfroggy.com/) game for learning CSS flexbox
    * [gridgarden](https://github.com/thomaspark/gridgarden/) game for learning CSS grid layout
  * [responsive design](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design)
    * [Responsive web design basics](https://web.dev/responsive-web-design-basics/)
    * [Learn Responsive Design](https://web.dev/learn/design/)
    * [Responsive images](https://web.dev/responsive-images/)
    * [Using media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
    * [Responsive Images in CSS](https://css-tricks.com/responsive-images-css/)
    * [Responsive Web Design](https://learn.shayhowe.com/advanced-html-css/responsive-web-design/)
    * [viewport meta tag](https://developer.mozilla.org/en-US/docs/Web/HTML/Viewport_meta_tag)
      gives hint about the size of the initial size of the
      [viewport](https://developer.mozilla.org/en-US/docs/Glossary/viewport)
  * video courses
    * [CSS - The Complete Guide 2022](https://www.udemy.com/course/css-the-complete-guide-incl-flexbox-grid-sass/)
    * [Advanced CSS and Sass: Flexbox, Grid, Animations and More!](https://www.udemy.com/course/advanced-css-and-sass/)

*(Page started in 2020; in progress)*

[*Go to parent page*](../README.md)
