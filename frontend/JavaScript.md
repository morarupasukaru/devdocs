# Javascript

TODO structure currently been changed

JavaScript (JS) is a lightweight, interpreted, or just-in-time compiled programming language with first-class functions and is the scripting language for Web pages.

* [declare](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements#declarations) 
  variables with [let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let) and constants with [const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)
* control flow with [if ... else](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else) and [switch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch)
* iterations
    * [for](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
    * [while](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while)
    * [do ... while](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while)
    * [for ... in](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in) (not to use with [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in#Array_iteration_and_for...in))
    * [for ... of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)
    * see also [Array.forEach()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) and [map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
* error handling with [try...catch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch) and [throw](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/throw)
  * [custom error types](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error#custom_error_types) ease error handling
  * [custom error should have a name and message](https://stackoverflow.com/questions/1382107/whats-a-good-way-to-extend-error-in-javascript)
* [primitive types](https://developer.mozilla.org/en-US/docs/Glossary/Primitive): 
  [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String),
  [Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number),
  [BigInt](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt),
  [Boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean),
  [undefined](https://developer.mozilla.org/en-US/docs/Glossary/undefined),
  [Symbol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol),
  [null](https://developer.mozilla.org/en-US/docs/Glossary/Null)
* reference types: [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array), [Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object), [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)
* [typeof](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof) 
  operator used to check value's type
  * [typeof variable === 'undefined'](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof#Errors) to check if variable is undefined
* [instanceof](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof) operator used to check if an object "extends a given class" (test if the presence of constructor.prototype in object's prototype chain)
* [type conversion](#Type-Conversion)
* [arithmetic's operations: +, -, *, /, %](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#arithmetic_operators)
* APIs
  * [console](https://developer.mozilla.org/en-US/docs/Web/API/Console) used for debugging purpose
  * [Math](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math) provide mathematical constants and functions (e.g. [Math.random()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random#Examples))
  * String
  * Array
  * Object
  * Date
  * Time
  * [JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON) used to convert value from/to JSON with [stringify()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify), [parse()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse)
  * [encodeURIComponent()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent), [decodeURIComponent()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/decodeURIComponent) functions used for URI handling
  * TODO


[*Go to top*](#Javascript)

TODO

* [String](#String), [Template Literals](#Template-Literals)
* [Arrays](#Arrays)
* [Object](#Object)
* [Dates & Times](#Dates-and-Times)
* [Function](#Function)
* [Regular Expression](#Regular-Expression)

* TODO
* [Object Oriented](#Object-Oriented): [ES5 Inheritance with prototype](#ES5-Inheritance-with-prototype), [ES6 Inheritance with class](#ES6-Inheritance-with-class), [Class free inheritance](#Class-free-inheritance)
* ES6/7: [Promises](#ES6-Promises), [Async & Await](#ES7-Async-and-Await), [Arrow Functions](#ES6-Arrow-Functions), [Iterators & Generators](#ES6-Iterators-and-Generators), [Symbols](#ES6-Symbols), [Destructuring](#ES6-Destructuring), [Maps](#ES6-Maps), [Sets](#ES6-Sets), [Modules](#ES6-Modules), [Public Class Fields](#Public-Class-Fields)
* ES11: [Optional chaining](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining)
* Miscelleanous
  * [JavaScript Patterns](#JavaScript-Patterns):
[Module](#Module-Pattern), [Revealing Module](#Revealing-Module-Pattern), [Singleton](#Singleton-Pattern), [Factory](#Factory-Pattern), [Observer](#Observer-Pattern), [Mediator](#Mediator-Pattern), [State](#State-Pattern)
  * [JavaScript Validation](#JavaScript-Validation) and [Minification](#Minification)
* [References](#References)

*(Page mainly written in 2019)*

[*Go to parent page*](../README.md)


## Type Conversion
* Convert to String: [(...).toString()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/toString) or [String(...)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#String_conversion) wihout new operator 
* Convert to Number: [parseInt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt) and [parseFloat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat), [Number(any type)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) without new operator
* Convert to boolean: `myValue === 'true'`
* [unary + operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Unary_plus_()) can be used to convert something to a number
* Convert String to Number: [parseInt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt) or [parseFloat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat)
* Convert any Type to Number: [Number(any type)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) without new operator
* [toFixed()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed) [Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)'s method formats a number using fixed-point notation
* [Number.isInteger()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isInteger)
* Type coersion happens in several cases in JavaScript and means that when the operands of an operator are different types, one of them will be converted to an "equivalent" value of the other operand's type.
    * It is good practise not to count on type coersion

[*Go to top*](#Javascript)


## String
* [Concatenation: 'Hello' + ' World'](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#string_operators)
* Accessor: 'Hello'[2] -> 'l'
* [length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length) property
* String's methods: [toUpperCase()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase), [toLowerCase()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase), [indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf), [lastIndexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/lastIndexOf), [substring()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring), [slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/slice), [split()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split), [replace()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace), [includes()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/includes)
* String are array-like and can be converted to Array with [Array.from()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from#Array_from_a_String)

[*Go to top*](#Javascript)


## Template Literals
* [template literals or template strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) are string literals allowing embedded expressions. You can use multi-line strings and string interpolation features with them
* template literals are very nice to dynamic build HTML sections.

[*Go to top*](#Javascript)


## Arrays
* Array literal: [1, 2, 3]
* Accessor: array[2]
* [length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/length) property
* Array's static methods:
    * [Array.isArray()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/isArray) to determines whether the passed value is an Array
    * [Array.from()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from) to convert an array-like or iterable object to array
* Array's methods: [indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf), [lastIndexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/lastIndexOf), [push()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push), [pop()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop), [unshift()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift), [shift()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift), [splice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice), [reverse()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse), [sort()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort), [concat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat), [find()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find), 
[map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map),
[filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter),
[reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)

[*Go to top*](#Javascript)


## Object
* Creating objects with [object literal/initializer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer#Creating_objects)
* [Accessing properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer#Accessing_properties)
* [Method definitions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Method_definitions#Description)
* [Access object's properties with **this** inside object method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this#As_an_object_method)

[*Go to top*](#Javascript)


## Dates and Times
* [get today with *new Date()*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date#Description)
* create date with [new Date(year, monthIndex [day, h, m, s, ms])](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/Date#syntax) - monthIndex is 0-based; January = 0
* parsing of dates with [new Date('*string*')](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/Date#parameters) or [Date.parse()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/parse)('*string*') is strongly discouraged due to browser differences and inconsistencies. Prefer use of external library such as [momentjs](http://momentjs.com/)
* [Date.get/](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getMonth)[setMonth()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setMonth), [get/](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getDate)[setDate()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setDate), [getDay()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getDay), [get/](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getFullYear)[setFullYear()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setFullYear),[get/](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getHours)[setHours()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setHours), [get/](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getMinutes)[setMinutes()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setMinutes), [get/](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getSeconds)[setSeconds()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setSeconds), [get/](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getMilliseconds)[setMilliseconds()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setMilliseconds), [get/](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getTime)[setTime()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setTime)

[*Go to top*](#Javascript)




## Function
* [function declaration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function#Description)[/expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function#Syntax), [object's method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Method_definitions#Description)
* [default value in function argument](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters#Syntax)
* [IIFE (Immediately Invoked Function Expression)](https://developer.mozilla.org/en-US/docs/Glossary/IIFE)
* [spread](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax) / [rest parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters)

[*Go to top*](#Javascript)


## Regular Expression
* [Regular expression literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions#Creating_a_regular_expression)
* Methods: [Regexp.exec()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/exec) / [.test()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/test)
, [.match()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/match), [.search()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/search), [String.replace()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace)
* [Search flags](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions#Advanced_searching_with_flags_2): i, g
* [Metacharacters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions#Using_special_characters)
  * [Boundaries](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Assertions#boundary-type_assertions) : ^, $ : must ends with
  * [Escaping](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions#Escaping) : \
  * [Groups and Ranges](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Groups_and_Ranges) : [], ()
  * [Quantifiers](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Quantifiers) : x+, x*, x?, x{n}, x{,n}, x{n,m}
  * [Types](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Character_Classes): ., \d, \D, \s, \S
  * [Assertions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Assertions) : x(?=y), x(?!y)

[*Go to top*](#Javascript)

## Object Oriented  
### ES5 Inheritance with prototype
* Construct objects with [new](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new) on a [constructor function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects#Using_a_constructor_function)
* use [this](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this) keyword to access object properties
* expect for [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date); prefer primitives to build in constructors
* [Object prototypes](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object_prototypes#Understanding_prototype_objects)
* [... are used mainly to share functions](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object_prototypes#Modifying_prototypes)
* [Object​.prototype​.hasOwnProperty](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)
* [Create object with a given prototype by using Object.create()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/create)
* [Classical inheritance with Object.create()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/create#classical_inheritance_with_object.create)

### ES6 Inheritance with class
* [class](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance#ECMAScript_2015_Classes) syntax
* [static methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/static)
* [getter & setter](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance#Getters_and_Setters)
* Inheritance with [extends](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/extends) and [super](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super)

### Class free inheritance

```
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
See [Douglas Crockford explanations](https://www.youtube.com/watch?v=PSGEjv3Tqo0&t=23m15s)

[*Go to top*](#Javascript)


## ES6 Promises
* replace "old-style" passed-in callbacks
* [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) [.then()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then) / [.catch()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/catch)
* See [Using promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises) guide

[*Go to top*](#Javascript)


## ES7 Async and Await
* [*async* function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function) runs asynchronous via the event loop and returns a Promise.
* [await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await) operator is used to wait for a Promise.
```
async function getUsers() {
  const response = await fetch('https://jsonplaceholder.typicode.com/users');
  const data = await response.json();
  return data;
}
```
* [workaround to allow await with top-level code](https://javascript.info/async-await):
```
(async () => {
  let response = await fetch('ttps://jsonplaceholder.typicode.com/users');
  let data = await response.json();
  ...
})();
```

[*Go to top*](#Javascript)


## ES6 Arrow Functions
* [arrow function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
* advantage of arrow function: provide a lexical "this" in object's method (this must not be saved into that or self)

[*Go to top*](#Javascript)


## ES6 Iterators and Generators
* [iterator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators#Iterators) implements the [iterator protocol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols#The_iterator_protocol)
* [generator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators#Generator_functions) is a more general iterator; their state can be modified by calling [next()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators#Advanced_generators)

[*Go to top*](#Javascript)


## ES6 Symbols
* [Symbol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol)

[*Go to top*](#Javascript)


## ES6 Destructuring
* [Destructuring assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment) available on [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment#Array_destructuring) or [Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment#Object_destructuring)
  * and allow to set the [Rest of an Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment#Assigning_the_rest_of_an_array_to_a_variable) to a variable
  * or set the [Rest of an Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment#Rest_in_Object_Destructuring) to a variable
* [Destructuring rest parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters#Destructuring_rest_parameters)

[*Go to top*](#Javascript)


## ES6 Maps
* [Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)
  * [get()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/get), [set()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/set), [delete()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/delete), [has()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/has), [keys()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/keys), [values()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/values), [entries()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/entries), [size](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/size)
  * [loop using for..of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map#iterating_map_with_for..of)
  * [iterating with forEach](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map#iterating_map_with_foreach)
  * [convert from/to arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map#Relation_with_Array_objects)

[*Go to top*](#Javascript)


## ES6 Sets
* [Set](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)
  * [add()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/add), [has()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/has), [delete()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/delete), [size](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/size)
  * [iterating with for..of or forEach](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set#Iterating_Sets)
  * [convert from/to arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set#Relation_with_Array_objects)

[*Go to top*](#Javascript)


## ES6 Modules
* [ES6 Modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules) uses [export](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export#Description), [import](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import#Description) statements
    * there are two different types of export: [named and default](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules#Default_exports_versus_named_exports)
* alternatives to ES2015 Modules: [CommonJS](https://en.wikipedia.org/wiki/CommonJS) or [AMD](https://github.com/amdjs/amdjs-api/blob/master/AMD.md)
* [systemjs](https://guybedford.com/systemjs-2.0) is a typical module loader to support several module format
* see [JavaScript Module Systems Showdown](https://auth0.com/blog/javascript-module-systems-showdown/) for a comparison of module loaders

[*Go to top*](#Javascript)


## ES7 Public-Class-Fields

[Public class fields](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/Public_class_fields) allow to declare fields without constructor
* [public or private](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes#Field_declarations)
* class methods can be writen with class field and arrow functions; it solve problem with `this` with events
  * see following [blog](https://ui.dev/javascript-private-and-public-class-fields/)

* example
```
class Person {
    firstName = "Mike";
    
    getName = () => {
      return this.firstName;
    };
}
```
instead of
```
class Person {
  constructor() {
    this.firstName = "Mike";

    this.getName = () => {
      return this.firstName;
    };
  }
}
```


[*Go to top*](#Javascript)

## JavaScript Patterns

### Module Pattern

```code
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

Alternative available with [ES6 Modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules) but required transpiling for support of module non-supporting browser.

[*Go to top*](#Javascript)


### Revealing Module Pattern

Revealing Module Pattern is cleaner as Module Pattern but do not allow to add additional feature to exposed methods (e.g. call other methods; like console.log above). 

```
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

[*Go to top*](#Javascript)


### Singleton Pattern
```
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

[*Go to top*](#Javascript)


### Factory Pattern
```
function TicketFactory() {
  this.createTicket = function(type) {
    let ticket;

    switch (type) {
      case "child":
          ticket = new ChildrenTicket();
        break;
      case "senior":
          ticket = new SeniorTicket();
        break;
      case "adult":
          ticket = new AdultTicket();
          break;
        default:
          throw new Error(`unsupported type ${type}`)
    }

    ticket.type = type;

    ticket.describe = function() {
      console.log(`${this.type}: ${this.cost}`);
    };

    return ticket;
  };
}

const ChildrenTicket = function() {
  this.cost = "$2";
};

const SeniorTicket = function() {
  this.cost = "$3";
};

const AdultTicket = function() {
  this.cost = "$5";
};

const factory = new TicketFactory();
factory.createTicket("child").describe();
factory.createTicket("senior").describe();
factory.createTicket("adult").describe();
```

See [Learning JavaScript Design Patterns](https://addyosmani.com/resources/essentialjsdesignpatterns/book/#factorypatternjavascript)

[*Go to top*](#Javascript)


### Observer Pattern

Example with Prototype and function as Observer:
```
function Subject() {
  this.observers = [];
}

Subject.prototype = {
  subscribe: function(fn) {
    this.observers.push(fn);
  },

  unsubscribe: function(fn) {
    this.observers = this.observers.filter(function(item) {
      if (item !== fn) {
        return item;
      }
    });
  },
  
  fire: function(value) {
    this.observers.forEach(function(item) {
      item(value);
    });
  }
}

const subject = new Subject();
subject.subscribe(observer);
subject.fire('a value');

function observer(value) {
  console.log(`receive '${value}'`);
}
```

Example with ES6 class and Object that implements a given contract as Observer (notify method):
```
class Subject {
  constructor() {
    this.observers = [];
  }

  subscribe(observer) {
    this.observers.push(observer);
  }

  unsubscribe(observer) {
    this.observers = this.observers.filter(function(item) {
      if (item !== observer) {
        return item;
      }
    });
  }

  fire(value) {
    this.observers.forEach(function(item) {
      observer.notify(value);
    });
  }
}

class Observer {
  notify(value) {
    console.log(`receive '${value}'`);
  }
}

const subject = new Subject();
const observer = new Observer();
subject.subscribe(observer);
subject.fire('a value');
```

[*Go to top*](#Javascript)


### Mediator Pattern

Mediator object encapsulates the communication between multiple objects (e.g. Airport Traffic Control Tower).
```
// MEDIATOR
const Chatroom = function() {
  let users = {}; // list of users

  return {
    register: function(user) {
      users[user.name] = user;
      user.chatroom = this;
    },

    send: function(message, from, to) {
      if (to) {
        // Single user message
        to.receive(message, from);
      } else {
        // Mass message
        for (key in users) {
          if (users[key] !== from) {
            users[key].receive(message, from);
          }
        }
      }
    }
  }
}

const User = function(name) {
  this.name = name;
  this.chatroom = null;
}

User.prototype = {
  send: function(message, to) {
    this.chatroom.send(message, this, to);
  },

  receive: function(message, from) {
    console.log(`${from.name} to ${this.name}: ${message}`)
  }
}

const user1 = new User('User 1');
const user2 = new User('User 2');
const user3 = new User('User 3');

const chatroom = new Chatroom();
chatroom.register(user1);
chatroom.register(user2);
chatroom.register(user3);

user1.send('Hello User 2', user2);
user3.send('Hello User 1', user1);
user2.send('Hello everyone');
```

[*Go to top*](#Javascript)


### State Pattern

Allow an object to alter its behavior when its internal state changes. The object will appear to change its class.
```
const TrafficLight = function() {
  let count = 0;
  let currentState;

  this.change = function(state) {
    // limits number of changes
    if (count++ >= 10) {
      return;
    }
    currentState = state;
    currentState.go();
  };

  this.start = function() {
    this.change(new Red(this));
  };
};

const Red = function(light) {
  this.light = light;

  this.go = function() {
    console.log("Red --> for 1 minute");
    light.change(new Green(light));
  };
};

const Yellow = function(light) {
  this.light = light;

  this.go = function() {
    console.log("Yellow --> for 10 seconds");
    light.change(new Red(light));
  };
};

const Green = function(light) {
  this.light = light;

  this.go = function() {
    console.log("Green --> for 1 minute");
    light.change(new Yellow(light));
  };
};

const light = new TrafficLight();
light.start();

```

[*Go to top*](#Javascript)


## JavaScript Validation

* [ESLint](https://eslint.org/) is current standard tool to validate JavaScript ([JSLint](https://jslint.com/) and [JSHint](https://jshint.com/) are obsolete; they does not support new JS features).
* ESLint is also bundled with [standardjs](https://standardjs.com/) that provide pretty-print as well.
* There is also preset of ESLint available: [airbnb](https://www.npmjs.com/package/eslint-config-airbnb), [google](https://github.com/google/eslint-config-google)

*Tools are becoming quick obsolete, please find appropriate tools during development*

[*Go to top*](#Javascript)


## Minification

Popular tools for JavaScript [minification](https://en.wikipedia.org/wiki/Minification_(programming)) are:
* [Closure compiler](https://github.com/google/closure-compiler)
* [uglifyjs](http://lisperator.net/uglifyjs/)

JSON can also be minified, see e.g. [grunt-json-minify](https://github.com/werk85/grunt-json-minify)

*Tools are becoming quick obsolete, please find appropriate tools during development*

[*Go to top*](#Javascript)


## References
* [MDN web docs](https://developer.mozilla.org/en-US/)
* Courses
  * [Modern JavaScript From The Beginning](https://www.udemy.com/modern-javascript-from-the-beginning/) by Brad Traversy
  * [JavaScript - The Complete Guide 2020](https://www.udemy.com/course/javascript-the-complete-guide-2020-beginner-advanced/) by Maximilian Schwarzmüller
* Webpages
  * [ECMAScript compatibilty table](https://kangax.github.io/compat-table/es6/)
  * [Summary of ES6 features](https://github.com/zsolt-nagy/es6-summary)
  * [Examples of everything new in ECMAScript 2016, 2017, and 2018](https://medium.freecodecamp.org/here-are-examples-of-everything-new-in-ecmascript-2016-2017-and-2018-d52fa3b5a70e)
  * [ECMAScript 6 - Overview & Comparison](http://es6-features.org/#Constants)
  * [es6 features](https://github.com/lukehoban/es6features)
  * [Good parts of JavaScript in 2014](http://bdadam.com/blog/video-douglas-crockford-about-the-new-good-parts.html)
* Books
  * [JavaScript: The Good Parts](http://shop.oreilly.com/product/9780596517748.do)
  * [JavaScript Patterns](http://shop.oreilly.com/product/9780596806767.do)
  * [Maintainable JavaScript](http://shop.oreilly.com/product/0636920025245.do)
  * [The principles of Object-Oriented JavaScript](https://leanpub.com/oopinjavascript)
  * [Effective JavaScript](http://effectivejs.com/)
  * [JavaScript, The Definitive Guide](http://shop.oreilly.com/product/9780596805531.do)
  * [Understanding ECMAScript 6](https://leanpub.com/understandinges6)
  * [ES6 & Beyond](https://github.com/getify/You-Dont-Know-JS/tree/1st-ed/es6%20%26%20beyond)

[*Go to top*](#Javascript)
