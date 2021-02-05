# Typescript

TypeScript is based on [JavaScript](JavaScript.md) features and add new features: **strongly types**, generics, interfaces, etc. It's a *wrapper* around JavaScript.
 TypeScript must be compiled to JavaScript to be run in the browser.

* [Installation](#Installation)
* [Configuration](#Configuration)
* [Using Javascript libraries](#Using-Javascript-libraries)
* [ES6 features supported by TypeScript](#ES6-features-supported-by-TypeScript): [Basic features](#Basic-features), [Classes](#Classes), [Modules](#Modules)
* [TypeScript features](#TypeScript-features): [Interfaces](#Interfaces), [Generics](#Generics), ([Namespaces](#Namespaces), [Decorators](#Decorators))
* [References](#References)

*(Page mainly written in 2019)*

[*Go to parent page*](../README.md)


## Installation

* Basic
  * ```npm -g install typescript```
  * Init project: ```tsc --init```
  * Compile: ```tsc --watch``` (allow to recompile TypeScript files on changes)
* Build-Tools: see [Integrating with Build Tools](https://www.typescriptlang.org/docs/handbook/integrating-with-build-tools.html#gulp): [gulp](https://www.typescriptlang.org/docs/handbook/integrating-with-build-tools.html#gulp) with [gulp-typescript](https://www.npmjs.com/package/gulp-typescript), [webpack 4](https://webpack.js.org/guides/typescript/), etc.

[*Go to top*](#TypeScript)


## Configuration
* usefull [compiler options](https://www.typescriptlang.org/docs/handbook/compiler-options.html) that can be defined in [tsconfig-json](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html):
  * sourceMap : allow to debug typescript code in browser
  * noImplicitAny: force to declare type of variables
  * noUnusedParameters: report errors on unused parameters
  * noUnusedLocals: report errors on unused locals
* compiled files can be configured in [tsconfig.json](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html) by defining *include*, *exclude* or *files* properties

[*Go to top*](#TypeScript)


## Using Javascript libraries
* [Download](https://www.typescriptlang.org/docs/handbook/declaration-files/consumption.html#downloading) *TypeScript type definitions* (which are [declaration files](https://www.typescriptlang.org/docs/handbook/declaration-files/introduction.html)) of needed JS library at [DefinitelyTyped](http://definitelytyped.org/)
* Alternative (hack): use an [ambient declaration](https://www.typescriptlang.org/docs/handbook/modules.html#shorthand-ambient-modules) to declare a variable already been loaded outside TypeScript "world" => disadvantage: no "types" checks

[*Go to top*](#TypeScript)


## Types
* basic types: [string](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), [number](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), [boolean](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean), [array](https://www.typescriptlang.org/docs/handbook/basic-types.html#array), [tuple](https://www.typescriptlang.org/docs/handbook/basic-types.html#tuple), [enum](https://www.typescriptlang.org/docs/handbook/basic-types.html#enum), [any](https://www.typescriptlang.org/docs/handbook/basic-types.html#any), [void](https://www.typescriptlang.org/docs/handbook/basic-types.html#void), [never](https://www.typescriptlang.org/docs/handbook/basic-types.html#never), [null & undefined](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)
* assigning types explicitly with *type annotation*: `var x: number;` or implicitly with [type inference](https://www.typescriptlang.org/docs/handbook/type-inference.html): `var x = 1;`
* function: [types of args & return](https://www.typescriptlang.org/docs/handbook/functions.html#function-types), [function type](https://www.typescriptlang.org/docs/handbook/functions.html#writing-the-function-type), [optional parameters](https://www.typescriptlang.org/docs/handbook/functions.html#optional-and-default-parameters)
* [type alias](https://www.typescriptlang.org/docs/handbook/advanced-types.html#type-aliases) allow to create a new name for a type 
* [union types](https://www.typescriptlang.org/docs/handbook/declaration-files/do-s-and-don-ts.html#use-union-types) allow to accept a given variable to be a of dedicated list of types (more restrictive than *any*)
* [string literal types](https://www.typescriptlang.org/docs/handbook/literal-types.html#string-literal-types) allow you to specify the exact value a string must have (enum-like)

[*Go to top*](#TypeScript)


## ES6 features supported by TypeScript

* see [JavaScript](JavaScript.md) for deeper ES6 features explanations.
* see [ES6 features supported by TypeScript](http://kangax.github.io/compat-table/es6/)


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
* [*string index signature*](https://www.typescriptlang.org/docs/handbook/interfaces.html#indexable-types) allow dynamic not yet known properties in interfaces:
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

[*Go to top*](#TypeScript)


## References
* [Documentation](https://www.typescriptlang.org/docs/)
* Course: [Understanding TypeScript](https://www.udemy.com/course/understanding-typescript/) by Maximilian Schwarzmüller
* [How to Write a TypeScript Library](https://www.tsmean.com/articles/how-to-write-a-typescript-library/)

[*Go to top*](#TypeScript)
