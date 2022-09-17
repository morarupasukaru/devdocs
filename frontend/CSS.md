# Cascading Style Sheets

[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) 
(Cascading Style Sheets) is a language to style and present HTML.

* [Language](#language)
* [CSSOM (CSS Object Model)](#cssom-css-object-model)
  to manipulate CSS from JavaScript
* Other concepts
  * [Responsive design](#responsive-design)
    that allows websites work on different screen widths, resolutions, etc.
  * [Mobile-first design](#mobile-first-design)
    to design websites for mobile (small screens) first and adapt then to desktop (larger screens)
  * Preprocessor languages [Sass](#Sass) or [Less](https://lesscss.org/)
    as alternatives to vanilla CSS
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
  * https://almanac.httparchive.org/en/2021/
* Tutorials
  * [beginner](https://htmldog.com/guides/css/beginner/), 
    [intermediate](https://htmldog.com/guides/css/intermediate/)
   [advanced](https://htmldog.com/guides/css/advanced/)
  * [getting started CSS](https://academind.com/learn/css/beginner-s-guide/) 
  * [Vanilla CSS vs Frameworks](https://academind.com/learn/css/understanding-css/vanilla-css-vs-frameworks/)
    article
  * [CSS - The Complete Guide 2022](https://www.udemy.com/course/css-the-complete-guide-incl-flexbox-grid-sass/) 
    [udemy](https://www.udemy.com/) course
  * [Advanced CSS and Sass: Flexbox, Grid, Animations and More!](https://www.udemy.com/course/advanced-css-and-sass/)
    [udemy](https://www.udemy.com/) course
  * [The Position Property](https://academind.com/learn/css/understanding-css/the-position-property/) article
  * [gridgarden](https://github.com/thomaspark/gridgarden/) game for learning CSS grid layout
  * flexbox
    * [CSS Grid vs Flexbox](https://academind.com/tutorials/css-grid-vs-flexbox) article
    * see [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) (from [CSS-TRICKS](https://css-tricks.com/))
    * see [Basic concepts of flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox) and other guides (from [MDN](https://developer.mozilla.org/en-US/))
    * [Flexbox: Basics & Container](https://academind.com/learn/css/understanding-css/flexbox-basics-container/), [part 2](https://academind.com/learn/css/understanding-css/flexbox-flex-items/) (from [academind](https://academind.com/))
    * [Flexbox CSS In 20 Minutes](https://www.youtube.com/watch?v=JJSoEo8JSnc&list=PLillGF-RfqbZTASqIqdvm1R5mLrQq79CU&index=4) (from (TraversyMedia)[https://www.traversymedia.com/])
    * [Flexbox Froggy](https://flexboxfroggy.com/) game for learning CSS flexbox

*(Page started in 2020; in progress)*

[*Go to parent page*](../README.md)


# Language

TODO move to top section after reducing size on section

* Concepts
  * [Syntax and semantics](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference#Concepts)
    * [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/Syntax)
    * [At-rules](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule)
      * [@import](https://developer.mozilla.org/en-US/docs/Web/CSS/@import)
    * [Cascade](https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade)
    * [Comments](https://developer.mozilla.org/en-US/docs/Web/CSS/Comments)
    * [CSS Descriptor](https://developer.mozilla.org/en-US/docs/Glossary/Descriptor_(CSS))
    * [Inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/inheritance)
    * [Shorthand properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Shorthand_properties)
    * [Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)
    * [Value definition syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/Value_definition_syntax)
    * [CSS values and units](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Values_and_Units)
    * [CSS Functional Notation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Functions)
    * [CSS selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)
      * [Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference#Selectors)
    * [Media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries)
  * Values
    * [Actual value](https://developer.mozilla.org/en-US/docs/Web/CSS/actual_value)
    * [Computed value](https://developer.mozilla.org/en-US/docs/Web/CSS/computed_value)
    * [Initial value](https://developer.mozilla.org/en-US/docs/Web/CSS/initial_value)
    * [Resolved value](https://developer.mozilla.org/en-US/docs/Web/CSS/resolved_value)
    * [Specified value](https://developer.mozilla.org/en-US/docs/Web/CSS/specified_value)
    * [Used value](https://developer.mozilla.org/en-US/docs/Web/CSS/used_value)
  * Layout
    * [Block formatting context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context)
    * [Box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model)
    * [Containing block](https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_block)
    * [Layout mode](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_mode)
      * [Normal flow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flow_Layout)
      * [Table layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Table)
      * Float layout
      * [Positioned layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning)
      * [Multi-column layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Columns)
      * [Flexible box layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout)
      * [Grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
        * see also [Relationship of grid layout to other layout methods](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Relationship_of_Grid_Layout#:~:text=already%20be%20using.-,Grid%20and%20flexbox,columns%20at%20the%20same%20time.)
    * [Margin collapsing](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing)
    * [Replaced elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Replaced_element)
    * [Stacking context](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context)
    * [Visual formatting model](https://developer.mozilla.org/en-US/docs/Web/CSS/Visual_formatting_model)
* Popular CSS properties:
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
* [Learn CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS) >>> TODO split in link / tutorial and concepts
  * [CSS first steps](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps)
    * [What is CSS?](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/What_is_CSS)
    * [Getting started with CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/Getting_started)
    * [How CSS is structured](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/How_CSS_is_structured)
    * [How CSS works](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/How_CSS_works)
  * [CSS building blocks](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks)
    * [Cascade and inheritance](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance)
    * [CSS selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors)
      * [Type, class, and ID selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Type_Class_and_ID_Selectors)
      * [Attribute selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Attribute_selectors)
      * [Pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
        * [:active](https://developer.mozilla.org/en-US/docs/Web/CSS/:active): when element is activated (*mouse button is pressed down*)
        * [:hover](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover): when the user hovers over an element with the cursor (requires a mouse pointer).
        * [:focus](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus): element (such as a form input) that has received focus (triggered when the user select the element)
        * [a:link](https://developer.mozilla.org/en-US/docs/Web/CSS/:link): link that has not yet been visited
        * [a:visited](https://developer.mozilla.org/en-US/docs/Web/CSS/:visited): link that the user has already visited
        * [:first-child](https://developer.mozilla.org/en-US/docs/Web/CSS/:first-child): represents the first element among a group of sibling elements
        * [:last-child](https://developer.mozilla.org/en-US/docs/Web/CSS/:last-child): last element among a group of sibling elements
        * [:nth-child](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child): matches elements based on their position in a group of siblings
          * condition of selection can be quite complex, e.g. [:nth-child(odd) or :nth-child(even)](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child#Keyword_values) childs can be selected
        * [:optional](https://developer.mozilla.org/en-US/docs/Web/CSS/:optional)/[:required](https://developer.mozilla.org/en-US/docs/Web/CSS/:required), [:enabled](https://developer.mozilla.org/en-US/docs/Web/CSS/:enabled)/[:disabled](https://developer.mozilla.org/en-US/docs/Web/CSS/:disabled) inputs
        * [:indeterminate](https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate)/[:checked](https://developer.mozilla.org/en-US/docs/Web/CSS/:checked) radio/checkbox/option
      * [Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
      * [Combinators](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Combinators)
    * [The box model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)
    * [Backgrounds and borders](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Backgrounds_and_borders)
    * [Handling different text directions](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Handling_different_text_directions)
    * [Overflowing content](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Overflowing_content)
    * [CSS values and units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)
    * [Sizing items in CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Sizing_items_in_CSS)
    * [Images, media, and form elements](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Images_media_form_elements)
    * [Styling tables](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Styling_tables)
    * [Debugging CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Debugging_CSS)
    * [Organizing your CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Organizing)
    * see also [Advanced styling effects](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Advanced_styling_effects)
  * [Styling text](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text)
    * [Fundamental text and font styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)
    * [Styling lists](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Styling_lists)
    * [Styling links](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Styling_links)
    * [Web fonts](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Web_fonts)
  * [CSS layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout)
    * [Introduction to CSS layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Introduction)
    * [Normal Flow](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Normal_Flow)
    * [Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)
    * [Grids](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids)
    * [Floats](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats)
    * [Positioning](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning)
    * [Multiple-column layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout)
    * [Responsive design](#Responsive-design)
    * [Beginner's guide to media queries](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Media_queries)
    * [Legacy layout methods](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods)
    * [Supporting older browsers](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Supporting_Older_Browsers)
  * forms styling
    * [Styling web forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Styling_web_forms)
    * [Advanced form styling](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling)
    * [UI pseudo-classes](https://developer.mozilla.org/en-US/docs/Learn/Forms/UI_pseudo-classes)
* Animations
  * [CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions)
    is a module of CSS that lets you create gradual transitions between the values of specific CSS properties
  * [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations)
    is a module of CSS that lets you animate the values of CSS properties over time, using keyframes
    * see [animatable CSS properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties)
    * see [Using CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* Miscellaneous
  * [meta tag viewport](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta/name) 
   gives hint about the size of the initial size of the 
   [viewport](https://developer.mozilla.org/en-US/docs/Glossary/viewport)

[*Go to top*](#Cascading-Style-Sheets)


# CSSOM (CSS Object Model)

[CSSOM](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Object_Model)
to manipulate CSS from JavaScript.

* [DocumentOrShadowRoot.styleSheets](https://developer.mozilla.org/en-US/docs/Web/API/DocumentOrShadowRoot/styleSheets)
  * [styleSheets[i].cssRules](https://developer.mozilla.org/en-US/docs/Web/API/CSSRuleList)
  * [cssRules[i].cssText](https://developer.mozilla.org/en-US/docs/Web/API/CSSRule/cssText)
  * [cssRules[i].selectorText](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleRule/selectorText)
* [HTMLElement.style](https://developer.mozilla.org/en-US/docs/Web/API/ElementCSSInlineStyle/style)
* [HTMLElement.style.cssText](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/cssText)
* [Element.className](https://developer.mozilla.org/en-US/docs/Web/API/Element/className)
* [Element.classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)
* Important methods
  * [CSSStyleSheet.insertRule()](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/insertRule)
  * [CSSStyleSheet.deleteRule()](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/deleteRule)

[*Go to top*](#Cascading-Style-Sheets)



# Responsive Design

[Responsive design](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design)
that allows websites work on different screen widths, resolutions, etc.

* CSS media queries to adjust layout & design
* mobile first
* images responsive
* https://web.dev/responsive-web-design-basics/
* https://web.dev/learn/design/
* https://web.dev/responsive-images/
* https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries
* https://css-tricks.com/responsive-images-css/
* https://learn.shayhowe.com/advanced-html-css/transitions-animations/

[*Go to top*](#Cascading-Style-Sheets)


# Mobile-first design

Mobile-first design means to design web pages for mobile (small screens) first and adapt then to desktop (larger screens).

* Reasons:
  * There is more mobile than desktop nowadays
  * It's easier to develop than "Desktop-first"
* Recipes:
  * choose the smallest device to be supported e.g. 320px width seem good choice
    * see [viewportsizes](https://viewportsizes.com/) to find out used mobile resolutions
  * standard css styles of the webpage must be the mobile version
  * css styles of *desktop* version must be specified with 
    [media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries)

[*Go to top*](#Cascading-Style-Sheets)


# Sass

* [Sass](https://sass-lang.com/) features
  * [variables](https://sass-lang.com/documentation/variables) allow defining constants to reduce repetition
  * [nesting](https://sass-lang.com/documentation/style-rules#nesting) reduce repetition of same selectors
  * TODO ...

[*Go to top*](#Cascading-Style-Sheets)
