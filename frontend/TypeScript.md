# Typescript

TODO doc restructuring in progress

[TypeScript](https://www.typescriptlang.org/) is based on [JavaScript](JavaScript.md) language and features and add 
new features: **strongly types**, generics, interfaces, etc. It's a *wrapper* around JavaScript and must be [transpiled](https://en.wikipedia.org/wiki/Source-to-source_compiler) to JavaScript to be run in the 
browser.

* [JavaScript features](JavaScript.md) are normally also [supported by TypeScript](http://kangax.github.io/compat-table/)
* declare variables with [let](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#let-declarations) and constants 
  with [const](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#const-declarations)
* types
  * [basic types](https://www.typescriptlang.org/docs/handbook/basic-types.html): 
    [string](https://www.typescriptlang.org/docs/handbook/basic-types.html#string),
    [number and bigint](https://www.typescriptlang.org/docs/handbook/basic-types.html#number),
    [boolean](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean),
    [object](https://www.typescriptlang.org/docs/handbook/basic-types.html#object),
    [array](https://www.typescriptlang.org/docs/handbook/basic-types.html#array),
    [tuple](https://www.typescriptlang.org/docs/handbook/basic-types.html#tuple), 
    [enum](https://www.typescriptlang.org/docs/handbook/basic-types.html#enum), 
    [null and undefined](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined),
    [any](https://www.typescriptlang.org/docs/handbook/basic-types.html#any), 
    [void](https://www.typescriptlang.org/docs/handbook/basic-types.html#void), 
    [never](https://www.typescriptlang.org/docs/handbook/basic-types.html#never)
  * [type annotation](https://www.typescriptlang.org/docs/handbook/typescript-tooling-in-5-minutes.html#type-annotations) 
    declare explicitly a variable to be a given type; e.g. `let x: number;`
  * [type inference](https://www.typescriptlang.org/docs/handbook/type-inference.html) 
    infer type of variables from its value; e.g. `let x = 1;` 
  * [type alias](https://www.typescriptlang.org/docs/handbook/advanced-types.html#type-aliases) allow to create a new name for a type 
  * [union types](https://www.typescriptlang.org/docs/handbook/declaration-files/do-s-and-don-ts.html#use-union-types) allow to accept a given variable to be a of dedicated list of types (more restrictive than *any*)
  * [string literal types](https://www.typescriptlang.org/docs/handbook/literal-types.html#string-literal-types) allow you to specify the exact value a string must have (enum-like)
* functions
  * [interface of function type](https://www.typescriptlang.org/docs/handbook/interfaces.html#function-types) can be used to specify the signature
  * [function type](https://www.typescriptlang.org/docs/handbook/functions.html#writing-the-function-type) can also be defined directly
  * [arrow function](https://www.typescriptlang.org/docs/handbook/functions.html#this-and-arrow-functions) to write compact code
  * [default parameters](https://www.typescriptlang.org/docs/handbook/functions.html#optional-and-default-parameters)
  * [rest parameters](https://www.typescriptlang.org/docs/handbook/functions.html#rest-parameters) 
    available on [tuple](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-3-0.html#tuples-in-rest-parameters-and-spread-expressions) as well
* classes
  * TODO
  * [TypeScript classes](https://www.typescriptlang.org/docs/handbook/classes.html) are more powerfull as [ES6 classes](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance#ECMAScript_2015_Classes), additional features:
    * access modifiers: [public](https://www.typescriptlang.org/docs/handbook/classes.html#public-by-default) (default), [private](https://www.typescriptlang.org/docs/handbook/classes.html#understanding-typescripts-private), [protected](https://www.typescriptlang.org/docs/handbook/classes.html#understanding-protected), [readonly](https://www.typescriptlang.org/docs/handbook/classes.html#readonly-modifier)
    * [static properties](https://www.typescriptlang.org/docs/handbook/classes.html#static-properties) (es6 supports only [static methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/static))
    * [abstract classes](https://www.typescriptlang.org/docs/handbook/classes.html#abstract-classes)
    * [private and protected constructors](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-2-0.html#private-and-protected-constructors) => usefull to implement singleton pattern
    * tip: [parameter property declaration](https://www.typescriptlang.org/docs/handbook/classes.html#parameter-properties) in constructor is shorthand for declaring a property with the same name as the parameter and initializing it with the value of the parameter
* interfaces
  * TODO
* other nice language features
  * [spread](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#spread) 
    operator to create easily array or object from existing one
  * [destructuring assignment](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#destructuring)
    ease copy of values from [arrays](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#array-destructuring) 
    or properties of [tuples](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#tuple-destructuring) or [objects](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#object-destructuring) 
    into distinct variables
  * [template literal](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-1-4.html#template-strings)
  * [TypeScript modules](https://www.typescriptlang.org/docs/handbook/modules.html) works like [ES6 Modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)
  * generics: TODO
  * decorators: TODO
* TODO
  * https://www.typescriptlang.org/docs/handbook/intro.html
  * https://www.typescriptlang.org/docs/handbook/utility-types.html
    * partial
    * record
    * readonly
    * nonnullabletype
  * Declaration Files
  * JSDoc 
  * https://www.typescriptlang.org/docs/handbook/declaration-files/dts-from-js.html
  * see [release notes](https://www.typescriptlang.org/docs/handbook/release-notes/overview.html) to check out new features
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


### Decorators
* [decorators (es6)](https://github.com/tc39/proposal-decorators) provide a way to add annotations and a meta-programming syntax (e.g. making a class immutable)
* [decorators](https://www.typescriptlang.org/docs/handbook/decorators.html) can be applied to [class (constructor)](https://www.typescriptlang.org/docs/handbook/decorators.html#class-decorators), [method](https://www.typescriptlang.org/docs/handbook/decorators.html#method-decorators)/[accessor](https://www.typescriptlang.org/docs/handbook/decorators.html#accessor-decorators)([property Descriptor (JS Object)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty#Description)), [property](https://www.typescriptlang.org/docs/handbook/decorators.html#property-decorators), [parameter](https://www.typescriptlang.org/docs/handbook/decorators.html#parameter-decorators)
* [factories](https://www.typescriptlang.org/docs/handbook/decorators.html#decorator-factories) allow to customize the used decorator.
* decorators are an experimental feature that may change in future releases
