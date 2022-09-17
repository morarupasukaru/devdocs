# Cascading Style Sheets

[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) 
(Cascading Style Sheets) is a language to style and present HTML.

* [Language](#language)
* [CSSOM (CSS Object Model)](#cssom--css-object-model-)
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
  * forms styling:
    * [Styling web forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Styling_web_forms)
    * [Advanced form styling](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling)
    * [UI pseudo-classes](https://developer.mozilla.org/en-US/docs/Learn/Forms/UI_pseudo-classes) >>> TODO delete?

*(Page started in 2020; in progress)*

[*Go to parent page*](../README.md)


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
  * css styles of *desktop* version must be specified with [Media Queries](#Media-Queries)

[*Go to top*](#Cascading-Style-Sheets)


# Sass

* [Sass](https://sass-lang.com/) features
  * [variables](https://sass-lang.com/documentation/variables) allow defining constants to reduce repetition
  * [nesting](https://sass-lang.com/documentation/style-rules#nesting) reduce repetition of same selectors
  * TODO ...

[*Go to top*](#Cascading-Style-Sheets)


# Language

TODO move to top section

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
    * [Animation](#Animation)
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
      * see also [box-sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing) CSS property
    * [Containing block](https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_block)
    * [Layout mode](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_mode)
      * [Normal flow](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flow_Layout)
      * [Table layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Table)
      * Float layout
      * [Positioned layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning)
      * [Multi-column layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Columns)
      * [Flexible box layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout)
      * [Grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
    * [Margin collapsing](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing)
    * [Replaced elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Replaced_element)
    * [Stacking context](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context)
    * [Visual formatting model](https://developer.mozilla.org/en-US/docs/Web/CSS/Visual_formatting_model)
* [Learn CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS)
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
* Miscellaneous
  * viewport

[*Go to top*](#Cascading-Style-Sheets)


## Layout and containing block

Size and position of an element are often impacted by its [containing block](https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_Block).

* e.g. computed width of an element with `width: 50%;` depend on the containing block
* containing block depends on the position property of the element
* basic rules to [identify containing block](https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_Block#Identifying_the_containing_block) (is more complex)
  * if position: static, relative, sticky, containing block = content box of nearest block level element/ancestor
  * if position: absolute, containing block = padding box of nearest ancestor having position != static
  * if position: fixed, the containing block is the [viewport](https://developer.mozilla.org/en-US/docs/Glossary/viewport)
* [computed values with percentage](https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_Block#Calculating_percentage_values_from_the_containing_block)
  * height, top, bottom are computed from the height of the containing block
  * width, left, right, margin are computed from the width of the containing block

[*Go to top*](#Cascading-Style-Sheets)


## min/max properties

[min-width](https://developer.mozilla.org/en-US/docs/Web/CSS/min-width), [max-width](https://developer.mozilla.org/en-US/docs/Web/CSS/max-width), [min-height](https://developer.mozilla.org/en-US/docs/Web/CSS/min-height), [max-height](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height) properties allow to specify limitations.

can be useful to prevent to display an image too small on small device if width of the image is set in percentage.

[*Go to top*](#Cascading-Style-Sheets)


## length and percentage types

[length](https://developer.mozilla.org/en-US/docs/Web/CSS/length) and [percentage](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) data types are used by many CSS properties like width, height, margin, etc.
* length data type: number + unit, e.g. 0.5em
  * unit is optional for `0` value
  * unit can be [relative](https://developer.mozilla.org/en-US/docs/Web/CSS/length#Relative_length_units) (to another distance) or [absolute](https://developer.mozilla.org/en-US/docs/Web/CSS/length#Absolute_length_units) (fix)
  * physical length on a device of an absolute length depend on the resolution
  * to avoid accessibility problems, use only relative units (users can increase font-size and layout could be broken)
* recommended units:
  * **%**: percentage, relative to the same property of the parent element
  * **rem**: relative to font size of the root element (default: 16px; can be override by user)
  * em: relative to font size of the element or inherited; be careful of cascading impact, see [em vs rem](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#ems_and_rems)
  * px: for border only (that do not require to scale)

[*Go to top*](#Cascading-Style-Sheets)



## position property

* [position](https://developer.mozilla.org/en-US/docs/Web/CSS/position) property sets how an element is positioned in a document:
  * static: default value; renders a box in the normal order of things; as they appear in the HTML.
  * relative: is much like static but the box can be offset from its original position with the properties [top](https://developer.mozilla.org/en-US/docs/Web/CSS/top), [right](https://developer.mozilla.org/en-US/docs/Web/CSS/right), [bottom](https://developer.mozilla.org/en-US/docs/Web/CSS/bottom) and [left](https://developer.mozilla.org/en-US/docs/Web/CSS/left)
  * absolute: the box can be placed anywhere on the page using [top](https://developer.mozilla.org/en-US/docs/Web/CSS/top), [right](https://developer.mozilla.org/en-US/docs/Web/CSS/right), [bottom](https://developer.mozilla.org/en-US/docs/Web/CSS/bottom) and [left](https://developer.mozilla.org/en-US/docs/Web/CSS/left).
  * fixed: behaves like absolute, but fixed boxes should stay exactly where they are on the screen even when the page is scrolled.
* see also [CSS Positioning Tutorial for Beginners](https://academind.com/learn/css/understanding-css/the-position-property/) (from [academind](https://academind.com/)

[*Go to top*](#Cascading-Style-Sheets)


## display property

* [display](https://developer.mozilla.org/en-US/docs/Web/CSS/display) property sets whether an element is treated as a block or inline element and the layout used for its children, such as flow layout, grid or flex.
  * block: generates a block element box, generating line breaks both before and after the element when in the normal flow
    * allow to change width
  * inline: generates one or more inline element boxes that do not generate line breaks before or after themselves. In normal flow, the next element will be on the same line if there is space
    * do not allow to change width
  * inline-block: generates a block element box that will be flowed with surrounding content as if it were a single inline box (without line break)
    * allow to change width of element
  * none: turns off the display of an element so that it has no effect on layout (takes the element’s box completely out of play)
    * vs "visibility: hidden; " : keeps the box and its flow in place without visually representing its contents
  * flex: see [Flexbox](#Flexbox)

TODO

[*Go to top*](#Cascading-Style-Sheets)


## Flexbox

[Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout) (Flexible Box Module) is an one-dimensional layout mode to arrange items in a container; is quite easy to use and responsive.

* flexbox allow to place [flex items](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox#Properties_applied_to_flex_items) (children elements) in a [flex container](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox#The_flex_container) (the *one dimension*) according to two axes; the [main](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox#The_main_axis), [cross](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox#The_cross_axis) axis.
* basis uses
  * [`display: flex|inline-flex;`](https://developer.mozilla.org/en-US/docs/Web/CSS/display): activate flexbox; set on container (inline-flex make container as inline element, flex as block element)
  * [`flex-direction: row|column|...;`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction): defines the main axis (default: row); set on container
  * [`justify-content: flex-start|center|...;`](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content): align items on main axis (default: flex-start); set on container
  * [`align-items: stretch|center|...;` ](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items): align items on cross axis (default: stretch); set on container
  * [`flex`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex): define width and how item will grow or shrink to fit available space in container (default: 0 1 auto); set on item; (is a [shorthand](#Shorthand-properties) for [flex-grow](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow), [flex-shrink](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-shrink), [flex-basis](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-basis))
* other properties
  * [`flex-wrap: wrap|nowrap|...;`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-wrap): to wrap items into multi-lines (default: nowrap); set on container
  * [`flex-flow`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-flow): [shorthand](#Shorthand-properties) property for [`flex-direction: row|column|...;`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction) and [flex-wrap](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-wrap); set on container
  * [`order: <integer>;`](https://developer.mozilla.org/en-US/docs/Web/CSS/order): define order of item in container (default: 0); items are sorted by ascending order; set on container
  * [`align-self: stretch|center|...;`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-self): override align-items for specific items (on cross axis); set on item
  * [`align-content: stretch|center|...;`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-content): define spacing between lines of in cross-axis (has not effect without wrapping); set on container
* resources
  * see [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) (from [CSS-TRICKS](https://css-tricks.com/))
  * see [Basic concepts of flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox) and other guides (from [MDN](https://developer.mozilla.org/en-US/))
  * TODO [Flexbox: Basics & Container](https://academind.com/learn/css/understanding-css/flexbox-basics-container/), [part 2](https://academind.com/learn/css/understanding-css/flexbox-flex-items/) (from [academind](https://academind.com/))
  * [Flexbox CSS In 20 Minutes](https://www.youtube.com/watch?v=JJSoEo8JSnc&list=PLillGF-RfqbZTASqIqdvm1R5mLrQq79CU&index=4) (from (TraversyMedia)[https://www.traversymedia.com/])
  * [Flexbox Froggy](https://flexboxfroggy.com/): game for learning CSS flexbox

[*Go to top*](#Cascading-Style-Sheets)


## font properties

* [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size): sets size of the font
  * it's good to set `hmtl { font-size: 100%; }` to indicate that browser font size is taken
* [`font-family`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family): specify prioritized list of fonts to used
  * safe fonts are Arial, Verdana and Times New Roman
* [`font-weight`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight): set whether the text is bold or not
* [`font-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style): set whether the text is italic or not
* [@font-face](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face): use an embedding font that could be downloaded
  * see [google fonts](https://fonts.google.com/) allow to easy embed font (@font-face is used internally in downloaded google css)

[*Go to top*](#Cascading-Style-Sheets)


## text formatting

* text spacing
  * [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align): sets horizontal alignment of block element or table cell
  * [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align): sets vertical alignment of an inline, inline-block or table-cell box; does not work for block-level elements
  * see also [`letter-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing), [`word-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/word-spacing), [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height), [`text-indent`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent)
* [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration): set whether the text got a line (under, over, through it or none)
* [`text-transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform): set the case of the text

[*Go to top*](#Cascading-Style-Sheets)




## viewport

[`<meta name="viewport" content="...">](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta/name) gives hint about the size of the initial size of the [viewport](https://developer.mozilla.org/en-US/docs/Glossary/viewport).

* most useful setting is to tell browser that the viewport must be the size of the device:
```css
<meta name="viewport" content="width=device-width">
```

[*Go to top*](#Cascading-Style-Sheets)






## Grid Layout

* [Gridlayout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout) is an two-dimensional layout mode
* https://academind.com/learn/css/understanding-css/css-grid-vs-flexbox/
* https://github.com/thomaspark/gridgarden/
* [Relationship of grid layout to other layout methods](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Relationship_of_Grid_Layout#:~:text=already%20be%20using.-,Grid%20and%20flexbox,columns%20at%20the%20same%20time.)

TODO

[*Go to top*](#Cascading-Style-Sheets)


## Flow Layout

* normal flow
  https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flow_Layout

TODO

[*Go to top*](#Cascading-Style-Sheets)


## properties

* layout related
  * [z-index](https://developer.mozilla.org/en-US/docs/Web/CSS/z-index): specify order of displayed overlapping elements

[*Go to top*](#Cascading-Style-Sheets)


## basic layout with position and display property
* basic **page layout**
  * floating: floating a box will shift it to the right or left of a line, with surrounding content flowing around i
    * use `float` property
    * use `clear` property to stop the float for next box

see [video about position property](https://academind.com/learn/css/understanding-css/the-position-property/)

[*Go to top*](#Cascading-Style-Sheets)



## TODO
* **properties**
  * color
    * predefined color names (not usefull except black and white, rgb, or hexcode
    * `color` and `background-color` css properties
    * advanced colors: CSS3 allow HSL (hue, saturation, and lightness) and transparency (rgba)
  * **shorthand properties**
    * margin instead of margin-top, margin-right, margin-bottom, and margin-left
    * padding instead of ...
    * border instead of border-width, border-color, and border-style
    * font instead of font-style, font-weight, font-size, line-height, and font-family
  * CSS background images with `background` css property
  * border radius
    * border-radius property (or border-top-left-radius, border-top-right-radius, border-bottom-right-radius, and border-bottom-left-radius)
    * ellipses available, e.g. `border-radius: 50px/100px;`
  * shadows
    * box-shadow property: add shadow for box
    * text-shadow property: add shadow to text
  * gradients: allow lineal and radial gradients
  * tranformation: `transform` allowe to rotate, skewe, scale, translate elements
  * multiple background images

[*Go to top*](#Cascading-Style-Sheets)


## Animations

* [CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions) is a module of CSS that lets you create gradual transitions between the values of specific CSS properties
  * see [Using CSS transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) shorthand property
  * configure the timing, duration with [transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) is a module of CSS that lets you animate the values of CSS properties over time, using keyframes.
  * configure the timing, duration, etc. with [animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation) shorthand property
  * configure the appearance of the animation with [@keyframes](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)
  * see [Using CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* CSS Transitions vs CSS Animations
  * CSS Animations provide finer control than CSS Transitions over animated properties; allow more complex animations
  * animation of CSS Transitions happen automatically whenever a change of a property happened
    * animation cannot be prevented with CSS Transitions
  * animation of CSS Animations must triggered manually by setting the `animation` property on it
* see [animatable CSS properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) (list evolves over time)

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

