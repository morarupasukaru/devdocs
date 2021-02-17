# Typescript

TODO doc restructuring in progress

[TypeScript](https://www.typescriptlang.org/) is based on [JavaScript](JavaScript.md) language and features and add 
new features: **strongly types**, generics, interfaces, etc. It's a *wrapper* around JavaScript and must be [transpiled](https://en.wikipedia.org/wiki/Source-to-source_compiler) to JavaScript to be run in the 
browser.

* TODO note about versions
* [JavaScript features](JavaScript.md) are normally also [supported by TypeScript](http://kangax.github.io/compat-table/)
* language features in addition to JavaScript
  * primitive types: TODO
  * function: TODO
  * type checks: TODO
  * inheritance: TODO
  * APIs: TODO
  * TODO new features
  * https://www.typescriptlang.org/docs/handbook/intro.html
  * https://www.typescriptlang.org/docs/handbook/utility-types.html
    * partial
    * record
    * readonly
    * nonnullabletype
  * Declaration Files
  * JSDoc 
  * https://www.typescriptlang.org/docs/handbook/declaration-files/dts-from-js.html
  
* getting started
  * [installation](https://www.typescriptlang.org/#installation)
  * [playground](https://www.typescriptlang.org/play)
  * ```tsc``` is TypeScript command line compiler
    * ```tsc --init``` to initialize project
    * ```tsc --watch``` to recompile project on changes
    * see other [options](https://www.typescriptlang.org/docs/handbook/compiler-options.html)
  * [build tools integration](https://www.typescriptlang.org/docs/handbook/integrating-with-build-tools.html#gulp) 
    with [gulp](https://www.typescriptlang.org/docs/handbook/integrating-with-build-tools.html#gulp), 
    [webpack 4](https://webpack.js.org/guides/typescript/), etc.
  * project configuration: [tsconfig.json](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html); useful flags:
    * [sourceMap](https://www.typescriptlang.org/tsconfig#sourceMap) : allow to debug typescript code in browser
    * [noImplicitAny](https://www.typescriptlang.org/tsconfig#noImplicitAny): force to declare type of variables
    * [noUnusedParameters](https://www.typescriptlang.org/tsconfig#noUnusedParameters): report errors on unused parameters
    * [noUnusedLocals](https://www.typescriptlang.org/tsconfig#noUnusedLocals): report errors on unused locals
    * [include](https://www.typescriptlang.org/tsconfig#include) /
    [exclude](https://www.typescriptlang.org/tsconfig#exclude): define compiled files
    * [target](https://www.typescriptlang.org/tsconfig#target): specify target browser (e.g. ES6)
    * [module](https://www.typescriptlang.org/tsconfig#module): specify module system (e.g. ES6)
    * see more flags in [tsconfig.json reference](https://www.typescriptlang.org/tsconfig)
  * use library (JavaScript or TypeScript)
    * [type search](https://www.typescriptlang.org/dt/search?search=) to find npm packages to integrate in a project
    * or [download](https://www.typescriptlang.org/docs/handbook/declaration-files/consumption.html#downloading) *TypeScript type definitions* (which are [declaration files](https://www.typescriptlang.org/docs/handbook/declaration-files/introduction.html)) of needed JS library at [DefinitelyTyped](http://definitelytyped.org/)
    * see also [how to write a TypeScript library](https://www.tsmean.com/articles/how-to-write-a-typescript-library/)
* references
  * [TypeScript documentation](https://www.typescriptlang.org/docs/)
  * course: [Understanding TypeScript](https://www.udemy.com/course/understanding-typescript/)
  
*(Page mainly written in 2019)*

[*Go to parent page*](../README.md)


## Types
* basic types: [string](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), [number](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), [boolean](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean), [array](https://www.typescriptlang.org/docs/handbook/basic-types.html#array), [tuple](https://www.typescriptlang.org/docs/handbook/basic-types.html#tuple), [enum](https://www.typescriptlang.org/docs/handbook/basic-types.html#enum), [any](https://www.typescriptlang.org/docs/handbook/basic-types.html#any), [void](https://www.typescriptlang.org/docs/handbook/basic-types.html#void), [never](https://www.typescriptlang.org/docs/handbook/basic-types.html#never), [null & undefined](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)
* assigning types explicitly with *type annotation*: `var x: number;` or implicitly with [type inference](https://www.typescriptlang.org/docs/handbook/type-inference.html): `var x = 1;`
* function: [types of args & return](https://www.typescriptlang.org/docs/handbook/functions.html#function-types), [function type](https://www.typescriptlang.org/docs/handbook/functions.html#writing-the-function-type), [optional parameters](https://www.typescriptlang.org/docs/handbook/functions.html#optional-and-default-parameters)
* [type alias](https://www.typescriptlang.org/docs/handbook/advanced-types.html#type-aliases) allow to create a new name for a type 
* [union types](https://www.typescriptlang.org/docs/handbook/declaration-files/do-s-and-don-ts.html#use-union-types) allow to accept a given variable to be a of dedicated list of types (more restrictive than *any*)
* [string literal types](https://www.typescriptlang.org/docs/handbook/literal-types.html#string-literal-types) allow you to specify the exact value a string must have (enum-like)

[*Go to top*](#TypeScript)


### Basic features
* [let](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#let-declarations) ([es6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)), [const](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#const-declarations)([es6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)), [block scope](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#block-scoping)([es6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/block))
* [arrow function](https://www.typescriptlang.org/docs/handbook/functions.html#this-and-arrow-functions)([es6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions))
* [default parameters](https://www.typescriptlang.org/docs/handbook/functions.html#optional-and-default-parameters)([es6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters#Syntax))
* [spread parameters (es6)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax), [rest parameters](https://www.typescriptlang.org/docs/handbook/functions.html#rest-parameters)([es6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters)) availables on [tuple](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-3-0.html#tuples-in-rest-parameters-and-spread-expressions) as well
* [destructuring assignment](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#destructuring) : [array](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#array-destructuring)[(es6)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment#Array_destructuring), [tuple](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#tuple-destructuring), [object](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#object-destructuring)[(es6)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment#Object_destructuring)
* [template string / literal](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-1-4.html#template-strings)([es6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals))
* more advanced: [symbols](https://www.typescriptlang.org/docs/handbook/symbols.html)([es6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol)), [iterator (es6)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators#Iterators), [generators (es6)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators#Generator_functions)


### Classes
[TypeScript classes](https://www.typescriptlang.org/docs/handbook/classes.html) are more powerfull as [ES6 classes](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance#ECMAScript_2015_Classes), additional features:
* access modifiers: [public](https://www.typescriptlang.org/docs/handbook/classes.html#public-by-default) (default), [private](https://www.typescriptlang.org/docs/handbook/classes.html#understanding-typescripts-private), [protected](https://www.typescriptlang.org/docs/handbook/classes.html#understanding-protected), [readonly](https://www.typescriptlang.org/docs/handbook/classes.html#readonly-modifier)
* [static properties](https://www.typescriptlang.org/docs/handbook/classes.html#static-properties) (es6 supports only [static methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/static))
* [abstract classes](https://www.typescriptlang.org/docs/handbook/classes.html#abstract-classes)
* [private and protected constructors](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-2-0.html#private-and-protected-constructors) => usefull to implement singleton pattern
* tip: [parameter property declaration](https://www.typescriptlang.org/docs/handbook/classes.html#parameter-properties) in constructor is shorthand for declaring a property with the same name as the parameter and initializing it with the value of the parameter


### Modules
[TypeScript Modules](https://www.typescriptlang.org/docs/handbook/modules.html) works like [ES6 Modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules).

#### Code Generation for Modules
* If *target* property in tsconfig.json is es5 or older, a module loader is required
* type of module loader is configured in *module* property of tsconfig.json
* see [Code Generation for Modules](https://www.typescriptlang.org/docs/handbook/modules.html#code-generation-for-modules) for more information

[*Go to top*](#TypeScript)


## TypeScript features

### Interfaces
* [interfaces](https://www.typescriptlang.org/docs/handbook/interfaces.html) of TypeScript are similar to interface of Java
* interface can exists without label, see [example](https://www.typescriptlang.org/docs/handbook/interfaces.html#our-first-interface)
* [optional properties in interface](https://www.typescriptlang.org/docs/handbook/interfaces.html#optional-properties)
* [readonly properties](https://www.typescriptlang.org/docs/handbook/interfaces.html#readonly-properties) are modifiable only when the object is created
* [string index signature](https://www.typescriptlang.org/docs/handbook/interfaces.html#indexable-types) allow dynamic not yet known properties in interfaces:
```
interface Person {
    firstName: string;
    [propName: string]: any; // string index signature
}
```
* [class implementing an interface](https://www.typescriptlang.org/docs/handbook/interfaces.html#class-types)
* [function types](https://www.typescriptlang.org/docs/handbook/interfaces.html#function-types) allow to define the signature of a function
* [interface inheritance](https://www.typescriptlang.org/docs/handbook/interfaces.html#extending-interfaces)
* interface are not compiled to JavaScript; there are used only for development purpose

### Generics
* [Generics](https://www.typescriptlang.org/docs/handbook/generics.html) of TypeScript
 are similar to generics of Java and like in java, generics can be quite complex.
* Concepts
  * [generic functions and interfaces](https://www.typescriptlang.org/docs/handbook/generics.html#generic-types)
  * [generic classes](https://www.typescriptlang.org/docs/handbook/generics.html#generic-classes)
  * [generic constraints](https://www.typescriptlang.org/docs/handbook/generics.html#generic-constraints) (by using *extends* keyword)


### Namespaces
* [namespace](https://www.typescriptlang.org/docs/handbook/namespaces.html) group logically related code; quite similar to *Module Pattern* in JS
* namespaces could be used for small projects that requires no complex *modules* dependencies; use *modules* otherwise.
* see also [multi-file namespace](https://www.typescriptlang.org/docs/handbook/namespaces.html#multi-file-namespaces), [alias](https://www.typescriptlang.org/docs/handbook/namespaces.html#aliases)


### Decorators
* [decorators (es6)](https://github.com/tc39/proposal-decorators) provide a way to add annotations and a meta-programming syntax (e.g. making a class immutable)
* [decorators](https://www.typescriptlang.org/docs/handbook/decorators.html) can be applied to [class (constructor)](https://www.typescriptlang.org/docs/handbook/decorators.html#class-decorators), [method](https://www.typescriptlang.org/docs/handbook/decorators.html#method-decorators)/[accessor](https://www.typescriptlang.org/docs/handbook/decorators.html#accessor-decorators)([property Descriptor (JS Object)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty#Description)), [property](https://www.typescriptlang.org/docs/handbook/decorators.html#property-decorators), [parameter](https://www.typescriptlang.org/docs/handbook/decorators.html#parameter-decorators)
* [factories](https://www.typescriptlang.org/docs/handbook/decorators.html#decorator-factories) allow to customize the used decorator.
* decorators are an experimental feature that may change in future releases
