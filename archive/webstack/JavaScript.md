# JavaScript

JavaScript (JS) is a lightweight, interpreted, or just-in-time compiled programming language with first-class functions 
and is the scripting language for Web pages.

* [language versions](https://en.wikipedia.org/wiki/ECMAScript_version_history): 
  * ES1 1997, ES2 1998, ES3 1999, ..., ES16 2025 and ES.Next for next version  
  * using [transpiler](https://en.wikipedia.org/wiki/Source-to-source_compiler) and/or [polyfills](https://en.wikipedia.org/wiki/Polyfill_(programming)) are recommended to be able to use features of latest JS version
* [declare](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements#declarations) 
  variables with [let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let) and constants 
  with [const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)
* [primitive types](https://developer.mozilla.org/en-US/docs/Glossary/Primitive): 
  [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String),
  [Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number),
  [BigInt](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt),
  [Boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean),
  [undefined](https://developer.mozilla.org/en-US/docs/Glossary/undefined),
  [Symbol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol),
  [null](https://developer.mozilla.org/en-US/docs/Glossary/Null)
* control flow with [if ... else](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else) 
  and [switch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch)
* iterations with
    [for](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for),
    [while](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while),
    [do ... while](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while),
    [for ... of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of),
    [for ... in](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in) 
    ([not for Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in#array_iteration_and_for...in)
    see also [Array.forEach()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) 
    and [map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map))
* error handling with [try...catch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch) 
  and [throw](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/throw)
  * [custom error types](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error#custom_error_types) ease error handling
  * [custom error should have a name and message](https://stackoverflow.com/questions/1382107/whats-a-good-way-to-extend-error-in-javascript)
* functions
  * kinds: [function declaration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function#Description), 
    [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function#Syntax),
    [object's method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Method_definitions#Description),
    [arrow function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
  * [IIFE](https://developer.mozilla.org/en-US/docs/Glossary/IIFE): immediately invoked function expression
  * [default function parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters#Syntax)
  * [rest parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters)
  * [Function.prototype.bind()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Function/bind) allow to create a new function with provided `this` value and argument values
* type checks
  * [typeof](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof)
    operator used to check value's type
    * `typeof variable === 'undefined'` to check if variable is undefined
  * [instanceof](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof) operator used to 
    check if an object "extends a given class" (test if the presence of constructor.prototype in object's prototype chain)
  * [Number.isInteger()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isInteger)
  * [Array.isArray()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/isArray)
* type conversions
  * ... to String: 
    [toString()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/toString) 
    , [String()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#String_conversion) function (without new)
    and [Number.toFixed()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed) 
  * ... to Number: [parseInt(string)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt),
    [parseFloat(string)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat), 
    [Number(any type)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) function (without new)
    and [+ unary operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#unary_operators) 
  * ... to Boolean: `myValue === 'true'`
  * [type coersion](https://developer.mozilla.org/en-US/docs/Glossary/Type_coercion) 
    happens in several cases in JavaScript and means that when the operands of an operator are different types, 
    one of them will be converted to an "equivalent" value of the other operand's type.
    * do not to count on type coersion; e.g. use ```===``` instead of ```==```
    * ... except to check if an object is [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)/[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)
* [arithmetic's operations: +, -, *, /, %](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#arithmetic_operators)
* [prototype inheritance](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)
  * construct objects [with literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain#objects_created_with_syntax_constructs)
  * ... [with a constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain#with_constructor_functions) function
    and [new](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new) operator
    * constructor main goal is to specify object properties
  * ... [with Object.create()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain#with_object.create)
    and a given [prototype](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object_prototypes#Understanding_prototype_objects)
    * prototype are used mainly to share functions
    * see [example of classical inheritance with constructor function, prototype and Object.create()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/create#classical_inheritance_with_object.create)
  * ... [with class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain#with_classes) and 
    [constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/constructor),
    [static](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/static),
    [extends](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/extends),
    [super](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super) keywords
    and [getter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get)/[setter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/set)
    * [class](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance#ECMAScript_2015_Classes) is a syntactic sugar; prototype inheritance remains under the hood
  * [this](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this) keyword to access object properties
  * [hasOwnProperty()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty) indicate if an object has the specified property as its own property (as opposed to inheriting it)
* [class free inheritance](https://www.youtube.com/watch?v=PSGEjv3Tqo0&t=23m15s) (from Douglas Crockford)
  ```javascript
  function constructor(spec) {
    let { member } = spec,
        { other } = other_constructor(spec),
        method = function() {
            // accessing member, other, method, spec
        };
  
    return Object.freeze({
        method,
        other
    });
  }
  ```
* APIs
  * [Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
    * create object with [object literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer#Creating_objects); e.g. ```{name: 'toto', age: 21}```
    * [access properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer#Accessing_properties)
      with [dot](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Property_Accessors#dot_notation)
      or [bracket](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Property_Accessors#bracket_notation) notation (e.g. ```object.name``` or ```object['name']```)
    * see shorter syntax of [method definitions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Method_definitions#Description)
    * [**this** refers to object's properties within an object method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this#class_context)
  * [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
    * create array with [array literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Array#array_literal_notation); e.g. ```[1, 2, 3]```
    * [access with index](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#access_an_array_item_by_its_index); e.g. ```array[2]```
    * [length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/length) property,
      [Array.isArray()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/isArray),
      [Array.from()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from) static methods and
      [indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf), 
      [lastIndexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/lastIndexOf), 
      [push()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push), 
      [pop()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop), 
      [unshift()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift), 
      [shift()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift), 
      [splice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice), 
      [reverse()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse), 
      [sort()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort), 
      [concat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat), 
      [find()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find), 
      [map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map),
      [filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter),
      [reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce) methods
  * [Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map) 
    * [get()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/get), 
      [set()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/set), 
      [delete()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/delete), 
      [has()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/has), 
      [keys()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/keys), 
      [values()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/values), 
      [entries()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/entries), 
      [size](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/size) methods
    * iterate with [for..of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map#iterating_map_with_for...of)
      or [forEach](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map#iterating_map_with_foreach)
    * [convert maps from/to arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map#relation_with_array_objects)
  * [Set](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)
    * [add()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/add), 
      [has()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/has), 
      [delete()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/delete), 
      [size](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/size) methods
    * iterate with [for..of or forEach](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set#iterating_sets)
    * [convert sets from/to arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set#relation_to_arrays)
  * [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
    * [concatenation with +](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#string_operators); e.g. ```'my ' + 'string'```
    * [accessor with [...]](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#character_access); e.g. ```'hello'[1]```
    * [length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length) property
      and [toUpperCase()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase), 
      [toLowerCase()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase), 
      [indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf), 
      [lastIndexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/lastIndexOf), 
      [substring()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring), 
      [slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/slice), 
      [split()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split), 
      [replace()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace), 
      [includes()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/includes) methods 
    * strings are array-like and can be converted to Array with 
      [Array.from()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from#Array_from_a_String)
  * [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)
    * [new Date()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/Date#parameters) to get current date/time
    * [new Date(year, monthIndex [day, h, m, s, ms])](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/Date#syntax) to create a given date/time (monthIndex is 0-based; January = 0)
    * parse dates with [momentjs](http://momentjs.com/) (or other external lib) instead of 
     [new Date(dateString)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/Date#parameters) or
      [Date.parse(dateString)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/parse)
      (due to browser differences and inconsistencies)
    * [Date.now()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/now) static method and
      [getTime()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getTime),
      [setTime()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setTime),
      [getMonth()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getMonth),
      [setMonth()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setMonth), etc. methods
  * [JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON) used to convert value from/to JSON with [stringify()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify), [parse()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse)
  * [encodeURIComponent()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent), [decodeURIComponent()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/decodeURIComponent) functions used for URI handling
  * [console](https://developer.mozilla.org/en-US/docs/Web/API/Console) used for debugging purpose
  * [Math](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math) 
    provide mathematical constants and functions (e.g. [Math.random()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random#Examples))
  * [Regular expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) with [RegExp](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp) and strings
    * create regex with [regex literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions#Creating_a_regular_expression);
      e.g. ```/ab+c/``` 
    * [exec()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/exec),
      [test()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/test) RegExp methods and
      [match()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/match), 
      [search()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/search), 
      [replace()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace) String methods
    * concepts: [search flags](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions#advanced_searching_with_flags) and
      [metacharacters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions#using_special_characters)
* other nice language features
  * [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) used for asynchronous operations (replace "old-style" passed-in callbacks)
    * [then()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then), 
      [catch()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/catch),
      [finally()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/finally) methods
    * [Promise.all()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all) takes promises as parameters, wait for completion of all promises and returns a Promise with array of the results of promises
    * see [Using promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises) guide or
    * see [JavaScript Promises: an introduction](https://web.dev/articles/promises)
    * or see [Why Promises Are Faster Than setTimeout()?](https://dmitripavlutin.com/javascript-promises-settimeout/)
    * see also [Microtasks ](https://developer.mozilla.org/en-US/docs/Web/API/HTML_DOM_API/Microtask_guide)
  * async and await to write asynchronous like synchronous code
    * [async function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function) runs asynchronous via the event loop and returns a Promise
    * [await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await) operator is used to wait for a Promise
    * async IIFE can be used to use await from top-level code; e.g.
       ```javascript
       (async () => {
         let response = await fetch('https://some-server.com/some-resource');
         let data = await response.json();
         ...
       })();
       ```
  * [template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) used to build strings efficiently (e.g. dynamic HTML sections)
  * [arrow function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) to write compact code
    * advantage: an arrow function inherit *this* if called in an object's method
  * [spread syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax) 
    to create easily [array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax#spread_in_array_literals)
    or [object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax#spread_in_object_literals) with existing ones (see also use in [function calls](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax#spread_in_function_calls))
  * [destructuring assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment) 
    ease copy of values from [arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring#array_destructuring) 
    or properties from [objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring#object_destructuring) into distinct variables
    * allow also to set the [rest of an array or object to a variable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring#rest_properties_and_rest_elements) 
  * [rest parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters) allows a function to accept an indefinite number of arguments as an array
  * [optional chaining](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining) with ```?.``` operator ease access of object properties
  * [shorthand property](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer#property_definitions)
    and [shorthand method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer#method_definitions)
    is a shorter way to define object's properties or methods within an 
    [object literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer)
  * [nullish coalescing operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing_operator) 
    ```??``` allow to specify default value if left-hand side operand is null or undefined only
    * [logical OR](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR) ```||``` returns default value also if left-hand side operand if falsy (side-effect possible; e.g. 0)
  * [modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules) ease to compose self-contained piece of codes together
    * [import](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import#Description) and [export](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export#Description) statements
    * features: [named and default](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules#default_exports_versus_named_exports) exports,
      [dynamic module loading](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules#dynamic_module_loading),
      [top level await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules#top_level_await)
    * JavaScript's modules should replace other module format like [CommonJS](https://en.wikipedia.org/wiki/CommonJS), 
      [AMD](https://github.com/amdjs/amdjs-api/blob/master/AMD.md),
      [UMD](https://github.com/umdjs/umd) 
      or module and revealing module patterns (see below)
      * see also articles [Understand the different javascript modules formats](https://code-trotter.com/web/understand-the-different-javascript-modules-formats/)
      and [JavaScript Module Systems Showdown](https://auth0.com/blog/javascript-module-systems-showdown/) 
      * module loaders like [systemjs](https://github.com/systemjs/systemjs), [requirejs](https://requirejs.org/) load specific format of modules at runtime in browser
      * module bundlers like [webpack](https://github.com/webpack/webpack), [browserify](http://browserify.org/), [parcel](https://parceljs.org/) bundle all modules together during build
* tools
  * playground: [JSFiddle](https://jsfiddle.net/), [JS Bin](https://jsbin.com/), [Flems](https://flems.io/)
  * [transpilers](https://en.wikipedia.org/wiki/Source-to-source_compiler): [Babel](https://babeljs.io/) or [Traceur](https://github.com/google/traceur-compiler) (they support also polyfills)
  * [linters](https://en.wikipedia.org/wiki/Lint_(software)): [ESLint](https://eslint.org/) 
    or bundled in [standardjs](https://standardjs.com/); see also [airbnb](https://www.npmjs.com/package/eslint-config-airbnb), [google](https://github.com/google/eslint-config-google) presets
  * [minifiers](https://en.wikipedia.org/wiki/Minification_(programming)): [Closure compiler](https://github.com/google/closure-compiler)
    or [uglifyjs](http://lisperator.net/uglifyjs/); see also [grunt-json-minify](https://github.com/werk85/grunt-json-minify) JSON minifier
  * documentation: [JSDoc](https://jsdoc.app/); see also [cheatsheet](https://devhints.io/jsdoc) 
    (JSDoc is also used in TypeScript to [generate declaration files from JavaScript](https://www.typescriptlang.org/docs/handbook/declaration-files/dts-from-js.html))
  * *tools are becoming quick obsolete, please find appropriate tools during development*
* libs
  * [validatejs](http://validatejs.org/) to valide javascript objects 
  * [marked.js](https://marked.js.org/) to compile markdown to HTML
  * [lodash](https://lodash.com/) or [underscore](https://underscorejs.org/) for utility librairies (needed in some cases; frameworks & current javascript version is often enough)
  * [bcryptjs](https://github.com/dcodeIO/bcrypt.js) to hash password and compare hash with plain password
* design patterns
  * *module pattern* as alternative to [module](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)
    ```javascript
    const module = (function () {
    
      let privateData = 'some private data';
    
      const privateMethod = function(arg) {
        privateData += arg;
        console.log(privateData);
      }
    
      return {
          publicMethod: function(arg) {
            privateMethod(arg); 
            console.log('do something else');
        }
      }
    })();
    
    module.publicMethod(' and more');
    ```
  * *revealing module pattern* as another alternative to [module](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)
    ```javascript
    const module = (function () {
    
      let privateData = 'some private data';
    
      const privateMethod = function(arg) {
        privateData += arg;
        console.log(privateData);
      }
    
      return {
          publicMethod: privateMethod
      }
    })();
    
    module.publicMethod(' and more');
    ```
    * revealing module pattern is cleaner as module oattern but do not allow to add additional feature to exposed methods (e.g. call other methods; like console.log above)
  * *singleton pattern*
    ```javascript
    const Singleton = (function() {
      let instance;
    
      function createInstance() {
        const object = { field: 'value', /* ... other fields, methods */ };
        return object;
      }
    
      return {
        getInstance: function() {
          if (!instance) {
            instance = createInstance();
          }
          return instance;
        }
      }
    })();
    
    var instance1 = Singleton.getInstance();
    var instance2 = Singleton.getInstance();
     
    console.assert(instance1 === instance2);
    ```
* references: [MDN web docs](https://developer.mozilla.org/en-US/)
  * courses: [Modern JavaScript From The Beginning](https://www.udemy.com/modern-javascript-from-the-beginning/) and
    [JavaScript - The Complete Guide 2025](https://www.udemy.com/course/javascript-the-complete-guide-2020-beginner-advanced/)
  * tutorial [beginner](https://htmldog.com/guides/javascript/beginner/),
    [intermediate](https://htmldog.com/guides/javascript/intermediate/),
    [advanced](https://htmldog.com/guides/javascript/advanced/)
  * webpages:
    * [ECMAScript compatibilty table](https://compat-table.github.io/compat-table/es6/)
    * [Good parts of JavaScript in 2014](http://bdadam.com/blog/video-douglas-crockford-about-the-new-good-parts.html)
  * books:
    [JavaScript: The Good Parts](http://shop.oreilly.com/product/9780596517748.do),
    [JavaScript Patterns](http://shop.oreilly.com/product/9780596806767.do),
    [Maintainable JavaScript](http://shop.oreilly.com/product/0636920025245.do),
    [The principles of Object-Oriented JavaScript](https://leanpub.com/oopinjavascript),
    [JavaScript, The Definitive Guide](http://shop.oreilly.com/product/9780596805531.do),
    [Understanding ECMAScript 6](https://leanpub.com/understandinges6) and
    [ES6 & Beyond](https://github.com/getify/You-Dont-Know-JS/tree/1st-ed/es6%20%26%20beyond)

[*Go to parent page*](README.md)

*(Page mainly written in 2019; links checked on 09.09.2025)*
