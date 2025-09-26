# Typescript

[TypeScript](https://www.typescriptlang.org/) is based on [JavaScript](../archive/JavaScript.md) language and features and add 
new features: **strongly types**, generics, interfaces, etc. It's a *wrapper* around JavaScript and TypeScript must be 
[transpiled](https://en.wikipedia.org/wiki/Source-to-source_compiler) to JavaScript to be run in the browser.

* [language versions](https://en.wikipedia.org/wiki/TypeScript#Release_history): 0.8 (2012) to 5.9 (2025)
* [JavaScript's features](../archive/JavaScript.md) are normally also [supported by TypeScript](https://compat-table.github.io/compat-table/)
* declare variables with [let](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#let-declarations) 
  and constants with [const](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#const-declarations)
* types
  * [basic types](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html): 
    [string, number, boolean](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#the-primitives-string-number-and-boolean),
    [bigint](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#bigint),
    [object](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#object-types),
    [array](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#arrays),
    [tuple](https://www.typescriptlang.org/docs/handbook/2/objects.html#tuple-types), 
    [enum](https://www.typescriptlang.org/docs/handbook/enums.html), 
    [null and undefined](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#null-and-undefined),
    [any](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any), 
    [void](https://www.typescriptlang.org/docs/handbook/2/functions.html#void), 
    [never](https://www.typescriptlang.org/docs/handbook/2/functions.html#never)
  * [template strings](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-1-4.html#template-strings)
  * [Array](https://www.typescriptlang.org/docs/handbook/2/objects.html#the-array-type) and [ReadonlyArray](https://www.typescriptlang.org/docs/handbook/2/objects.html#the-readonlyarray-type) generic types  
  * [type annotation](https://www.typescriptlang.org/docs/handbook/typescript-tooling-in-5-minutes.html#type-annotations) 
    declare explicitly a variable to be a given type; e.g. `let x: number;`
  * [type inference](https://www.typescriptlang.org/docs/handbook/type-inference.html) 
    infer type of variables from its value; e.g. `let x = 1;` 
  * [type alias](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#type-aliases) 
    allow to create a new name for a type 
  * [union types](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#union-types) 
    allow to accept a given variable to be a value of dedicated list of types (more restrictive than 
    [any](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any))
  * [string literal types](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#literal-types)
    allow you to specify the exact value a string must have (enum-like); 
    * e.g. `type Alignment = "left" | "right" | "center";`
    * see [How to list the possible values of a string literal union type in TypeScript](https://danielbarta.com/literal-iteration-typescript/)
  * [discriminated unions](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes-func.html#discriminated-unions) or [tagged union](https://en.wikipedia.org/wiki/Tagged_union)
    is a data structure used to hold a value that could take on several different, but fixed, types
  * [intersection types](https://www.typescriptlang.org/docs/handbook/2/objects.html#intersection-types) to build up new types from other types by extending them
  * [tuple](https://www.typescriptlang.org/docs/handbook/2/objects.html#tuple-types) and [readonly
 tuple](https://www.typescriptlang.org/docs/handbook/2/objects.html#readonly-tuple-types) types
  * [utility types](https://www.typescriptlang.org/docs/handbook/utility-types.html) used to transform types; e.g.
    * [`Partial<Type>`](https://www.typescriptlang.org/docs/handbook/utility-types.html#partialtype)
      : constructs a type with all properties of *Type* set to optional
    * [`Readonly<Type>`](https://www.typescriptlang.org/docs/handbook/utility-types.html#readonlytype)
      : constructs a type with all properties of *Type* set to readonly (immutable)
    * [`Record<Keys,Type>`](https://www.typescriptlang.org/docs/handbook/utility-types.html#recordkeys-type)
      : constructs an object type whose property keys are *Keys* and whose property values are *Type* (map)
    * [`NonNullable<Type>`](https://www.typescriptlang.org/docs/handbook/utility-types.html#nonnullabletype)
      : constructs a type by excluding null and undefined from *Type*
    * etc.
* [narrowing](https://www.typescriptlang.org/docs/handbook/2/narrowing.html) is the process of refining types to more specific types than declared; help TypeScript to use JavaScript syntax with strong typing
  * use [{ ... } as const](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#literal-inference) to convert an entire object to be type literals
* creating types from types
  * [generics](https://www.typescriptlang.org/docs/handbook/2/generics.html) - types which take parameters (in types, interfaces, ...)
    * [using type parameters in generic constraints](https://www.typescriptlang.org/docs/handbook/2/generics.html#using-type-parameters-in-generic-constraints), e.g.
    ```typescript
    function getProperty<Type, Key extends keyof Type>(obj: Type, key: Key) {
      return obj[key];
    }
    let x = { a: 1, b: 2, c: 3, d: 4 };
    getProperty(x, "a");
    getProperty(x, "m"); // error, m not assignable to type '"a" | "b" | "c" | "d"'
      ```
  * [keyof type operators](https://www.typescriptlang.org/docs/handbook/2/keyof-types.html) - Using the keyof operator to create new types
  * [typeof type operators](https://www.typescriptlang.org/docs/handbook/2/typeof-types.html) - Using the typeof operator to create new types
  * [indexed access typess](https://www.typescriptlang.org/docs/handbook/2/indexed-access-types.html) - Using Type['a'] syntax to access a subset of a type
  * [conditional typess](https://www.typescriptlang.org/docs/handbook/2/conditional-types.html) - Types which act like if statements in the type system
  * [mapped typess](https://www.typescriptlang.org/docs/handbook/2/mapped-types.html) - Creating types by mapping each property in an existing type
  * [template literal types](https://www.typescriptlang.org/docs/handbook/2/template-literal-types.html) - Mapped types which change properties via template literal strings
    * [intrinsic String manipulation types](https://www.typescriptlang.org/docs/handbook/2/template-literal-types.html#intrinsic-string-manipulation-types) like `Uppercase<StringType>`, etc.
* [functions](https://www.typescriptlang.org/docs/handbook/2/functions.html)
  * [function type expressions](https://www.typescriptlang.org/docs/handbook/2/functions.html#function-type-expressions)
    can also be defined directly
  * [optional and default parameters](https://www.typescriptlang.org/docs/handbook/2/functions.html#optional-parameters)
  * [rest parameters](https://www.typescriptlang.org/docs/handbook/2/functions.html#rest-parameters)
    available on [tuple](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-3-0.html#tuples-in-rest-parameters-and-spread-expressions)
    as well
  * [parameter destructuring](https://www.typescriptlang.org/docs/handbook/2/functions.html#parameter-destructuring) to conveniently unpack objects provided as an argument into one or more local variables in the function body; default value can be set to local variables
  * [function overloads](https://www.typescriptlang.org/docs/handbook/2/functions.html#function-overloads) by specifiying several signature overload and one function implementation matching them
* [modules](https://www.typescriptlang.org/docs/handbook/modules.html) 
  of TypeScript works like 
  [ES6 Modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)
* [classes](https://www.typescriptlang.org/docs/handbook/2/classes.html) of TypeScript are more powerful as in 
  [JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance#ECMAScript_2015_Classes), e.g.
  * more wide support of access modifiers: [public](https://www.typescriptlang.org/docs/handbook/2/classes.html#public) (default), [private](https://www.typescriptlang.org/docs/handbook/2/classes.html#private), [protected](https://www.typescriptlang.org/docs/handbook/2/classes.html#protected), [readonly](https://www.typescriptlang.org/docs/handbook/2/classes.html#readonly)
  * [static members](https://www.typescriptlang.org/docs/handbook/2/classes.html#static-members) (es6 supports only [static methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/static))
  * [abstract classes](https://www.typescriptlang.org/docs/handbook/2/classes.html#abstract-classes-and-members)
  * [private and protected constructors](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-2-0.html#private-and-protected-constructors) 
    are useful to implement singleton pattern
  * [parameter property declaration](https://www.typescriptlang.org/docs/handbook/2/classes.html#parameter-properties) 
    in a constructor is a shorthand for declaring a property with the same name as the parameter and initializing it 
    with the value of the parameter
* [interfaces](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#interfaces) are used to define custom types/contracts 
  to be implemented by [classes](https://www.typescriptlang.org/docs/handbook/2/classes.html)
  * see [optional](https://www.typescriptlang.org/docs/handbook/2/objects.html#optional-properties) and 
    [readonly](https://www.typescriptlang.org/docs/handbook/2/objects.html#readonly-properties) 
    properties in interface
  * [index signature](https://www.typescriptlang.org/docs/handbook/2/objects.html#index-signatures) allow defining maps in interface:
    ```typescript
    interface Person {
      firstName: string;
      [propName: string]: any; // string index signature
    }
    ```
  * take care: interface like type are not compiled to JavaScript; there are used only for development purpose
  * see [interfaces vs types](https://stackoverflow.com/questions/37233735/interfaces-vs-types) 
    to find out when custom "types" can be created with type or with interface
* other nice language features
  * [spread](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#spread) 
    operator to create easily array or object from existing one
  * [destructuring assignment](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#destructuring)
    ease copy of values from [arrays](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#array-destructuring) 
    or properties of [tuples](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#tuple-destructuring) or [objects](https://www.typescriptlang.org/docs/handbook/variable-declarations.html#object-destructuring) 
    into distinct variables
  * [decorators](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/#decorators) based on ECMAScript to annotate a class/method/property/etc.
    (see also [legacy TS only decorators](https://www.typescriptlang.org/docs/handbook/decorators.html)) 
  * [declaration files](https://www.typescriptlang.org/docs/handbook/2/type-declarations.html#dts-files)
    `.d.ts` contain only type information
    * see [creating .d.ts Files from .js files with JSDoc](https://www.typescriptlang.org/docs/handbook/declaration-files/dts-from-js.html) 
* getting started
  * [installation](https://www.typescriptlang.org/#installation)
  * [playground](https://www.typescriptlang.org/play)
  * ```tsc``` is TypeScript command line compiler
    * ```tsc --init``` to initialize project
    * ```tsc --watch``` to recompile project on changes
    * see other [options](https://www.typescriptlang.org/docs/handbook/compiler-options.html)
  * [build tools integration](https://www.typescriptlang.org/docs/handbook/integrating-with-build-tools.html#gulp) 
  * project configuration: [tsconfig.json](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html); useful flags:
    * [strict](https://www.typescriptlang.org/tsconfig/#strict): to enables a wide range of type checking behavior like
      * ... [strictNullChecks](https://www.typescriptlang.org/tsconfig/#strictNullChecks) : to get a type error if null and undefined is used where a concrete value is expected (if strictNullChecks = true)
      * ... [noImplicitAny](https://www.typescriptlang.org/tsconfig#noImplicitAny): force to declare type of variables
      * etc.
    * [noUnusedParameters](https://www.typescriptlang.org/tsconfig#noUnusedParameters): report errors on unused parameters
    * [noUnusedLocals](https://www.typescriptlang.org/tsconfig#noUnusedLocals): report errors on unused locals
    * [sourceMap](https://www.typescriptlang.org/tsconfig#sourceMap) : allow to debug typescript code in browser
    * [include](https://www.typescriptlang.org/tsconfig#include) /
    [exclude](https://www.typescriptlang.org/tsconfig#exclude): define compiled files
    * [target](https://www.typescriptlang.org/tsconfig#target): specify target ECMAScript version (e.g. ES6)
    * [module](https://www.typescriptlang.org/tsconfig#module): specify module system (e.g. ES6)
    * see more flags in [tsconfig.json reference](https://www.typescriptlang.org/tsconfig)
  * use library (JavaScript or TypeScript)
    * [download](https://www.typescriptlang.org/docs/handbook/declaration-files/consumption.html#downloading) *TypeScript type definitions* (which are [declaration files](https://www.typescriptlang.org/docs/handbook/declaration-files/introduction.html)) 
    * of needed JS library at [DefinitelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped)
    * see also [how to write a TypeScript library](https://www.tsmean.com/articles/how-to-write-a-typescript-library/)
* references
  * **[TypeScript Cheat Sheets](https://www.typescriptlang.org/cheatsheets/)**
  * [TypeScript documentation](https://www.typescriptlang.org/docs/)
  * [JSDoc reference](https://www.typescriptlang.org/docs/handbook/jsdoc-supported-types.html)
  * [TypeScript release notes](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-5-9.html) to check out new features
  * course: [Understanding TypeScript](https://www.udemy.com/course/understanding-typescript/)

[*Go to parent page*](../README.md)

*Page update written in 2019, last update: 09.2025; links checked on 02.09.2025*
