# RxJS

[RxJS](https://rxjs.dev/guide/overview) (Reactive Extensions for JavaScript) is a library for reactive 
programming using observables that makes it easier to compose asynchronous or callback-based code.

*[Reactive programming using observables](http://reactivex.io/) exists also in various other languages like [RxJava](https://github.com/ReactiveX/RxJava) for java*

*(Page mainly written in september 2020)*

[*Go to parent page*](../README.md)

* read [Angular docs](https://angular.io/guide/rx-library) and [RxJS Primer](https://www.learnrxjs.io/learn-rxjs/concepts/rxjs-primer) for quick intro or see [Understanding RxJS](https://academind.com/tutorials/understanding-rxjs/) YouTube serie
* [RxJS](https://rxjs.dev/guide/overview) concepts
  * [Observable](https://rxjs.dev/guide/observable) ([video](https://www.youtube.com/watch?v=Tux1nhBPl_w&feature=youtu.be)) represents the idea of an invokable collection of future values or events
  * [Observer](https://rxjs.dev/guide/observer) ([video](https://www.youtube.com/watch?v=Tux1nhBPl_w&feature=youtu.be)) is a collection of callbacks that knows how to listen to values delivered by the Observable
  * [pipe](https://www.learnrxjs.io/learn-rxjs/concepts/rxjs-primer#pipe) function allows to assemble a ```pipe```-line of operators on observable data
  * [Operators](https://rxjs.dev/guide/operators) ([video](https://www.youtube.com/watch?v=-nYQJkMpOHU&feature=youtu.be)) are pure functions that enable a functional programming style of dealing with collections with operations like map, filter, concat, reducetc
  * [Subscription](https://rxjs.dev/guide/subscription) ([video](https://www.youtube.com/watch?v=Tux1nhBPl_w&feature=youtu.be)) represents the execution of an Observable, is primarily useful for cancelling the execution
  * [Subjects](https://rxjs.dev/guide/subject) ([video](https://www.youtube.com/watch?v=rdK92pf3abs&feature=youtu.be)) is the equivalent to an EventEmitter, and the only way of multicasting a value or event to multiple Observers
  * [Scheduler](https://rxjs.dev/guide/scheduler) are centralized dispatchers to control concurrency, allowing us to coordinate when computation happens on e.g. setTimeout or requestAnimationFrame or others
* [Common operators](https://angular.io/guide/rx-library#common-operators) grouped by categories
  * [Combination](https://www.learnrxjs.io/learn-rxjs/operators/combination)
    * **[merge](https://rxjs.dev/api/index/function/merge)** ([doc](https://www.learnrxjs.io/learn-rxjs/operators/combination/merge), [demo](https://reactive.how/merge)) : turn multiple observables into a single observable
    * **[concat](https://rxjs.dev/api/index/function/concat)** ([doc](https://www.learnrxjs.io/learn-rxjs/operators/combination/concat)) : subscribe to observables in order as previous completes
    * [combineLatest](https://rxjs.dev/api/index/function/combineLatest) ([doc](https://www.learnrxjs.io/learn-rxjs/operators/combination/combinelatest), [demo](https://reactive.how/combinelatest)) : when any observable emits a valuemit the last emitted value from each
    * [startWith](https://rxjs.dev/api/operators/startWith) ([doc](https://www.learnrxjs.io/learn-rxjs/operators/combination/startwith), [demo](https://reactive.how/startwith)) : emit given value first
    * [withLatestFrom](https://rxjs.dev/api/operators/withLatestFrom) ([doc](https://www.learnrxjs.io/learn-rxjs/operators/combination/withlatestfrom)) : also provide the last value from another observable
    * [zip](https://rxjs.dev/api/index/function/zip) ([doc](https://www.learnrxjs.io/learn-rxjs/operators/combination/zip), [demo](https://reactive.how/zip)) : after all observables emitmit values as an array
  * [Creation](https://www.learnrxjs.io/learn-rxjs/operators/creation)
    * **[from](https://rxjs.dev/api/index/function/from)** ([doc](https://www.learnrxjs.io/learn-rxjs/operators/creation/from)) : turn an array, promiser iterable into an observable
    * **[of](https://rxjs.dev/api/index/function/of)** ([doc](https://www.learnrxjs.io/learn-rxjs/operators/creation/of)) : emit variable amount of values in a sequence and then emits a complete notification
    * [ajax](https://rxjs.dev/api/ajax/ajax) ([doc](https://www.learnrxjs.io/learn-rxjs/operators/creation/ajax)) : create an observable for an Ajax request
    * [fromEvent](https://rxjs.dev/api/index/function/fromEvent) ([doc](https://www.learnrxjs.io/learn-rxjs/operators/creation/fromevent)) : turn event into observable sequence
  * [Error Handling](https://www.learnrxjs.io/learn-rxjs/operators/error_handling)
    * **[catchError](https://rxjs.dev/api/operators/catchError)** ([doc](https://www.learnrxjs.io/learn-rxjs/operators/error_handling/catch)) : gracefully handle errors in an observable sequence
    * [retry](https://rxjs.dev/api/operators/retry) ([doc](https://www.learnrxjs.io/learn-rxjs/operators/error_handling/retry)) : retry an observable sequence a specific number of times should an error occur
  * [Multicasting](https://www.learnrxjs.io/learn-rxjs/operators/multicasting)
    * [share](https://rxjs.dev/api/operators/share) ([doc](https://www.learnrxjs.io/learn-rxjs/operators/multicasting/share)) : share source among multiple subscribers
    * [shareReplay](https://www.learnrxjs.io/learn-rxjs/operators/multicasting/sharereplay)) : share source and replay specified number of emissions on subscription
  * [Filtering](https://www.learnrxjs.io/learn-rxjs/operators/filtering)
    * **[filter](https://rxjs.dev/api/operators/filter)** ([doc](https://www.learnrxjs.io/learn-rxjs/operators/filtering/filter), [demo](https://reactive.how/filter), [video](https://www.youtube.com/watch?v=tk5x8By3yYk&feature=youtu.be)) : emit values that pass the provided condition
    * **[take](https://rxjs.dev/api/operators/take)** ([doc](https://www.learnrxjs.io/learn-rxjs/operators/filtering/take), [demo](https://reactive.how/take)) : emit provided number of values before completing
      * *hint*: [take](https://rxjs.dev/api/operators/take) operator allow to unsubscribe automatically after retrieving the data
    * [takeUntil](https://rxjs.dev/api/operators/takeUntil) ([doc](https://www.learnrxjs.io/learn-rxjs/operators/filtering/takeuntil)) : emit values until provided observable emits
    * [debounceTime](https://rxjs.dev/api/operators/debounceTime) ([doc](https://rxjs.dev/api/operators/debounceTime), [demo](https://reactive.how/debouncetime), [video](https://www.youtube.com/watch?v=QbNUD5ca99A&feature=youtu.be)) : discard emitted values that take less than the specified time between output
    * [distinctUntilChanged](https://rxjs.dev/api/operators/distinctUntilChanged) ([doc](https://www.learnrxjs.io/learn-rxjs/operators/filtering/distinctuntilchanged), [video](https://www.youtube.com/watch?v=QbNUD5ca99A&feature=youtu.be)) : only emit when the current value is different than the last
  * [Transformation](https://www.learnrxjs.io/learn-rxjs/operators/transformation)
    * **[map](https://rxjs.dev/api/operators/map)** ([doc](https://www.learnrxjs.io/learn-rxjs/operators/transformation/map), [demo](https://reactive.how/map)) : apply projection with each value from source
    * **[scan](https://rxjs.dev/api/operators/scan)** ([doc](https://www.learnrxjs.io/learn-rxjs/operators/transformation/scan), [demo](https://reactive.how/scan), [video](https://www.youtube.com/watch?v=myEeo2rZc3g&feature=youtu.be)) : reduce over time
    * [reduce](https://rxjs.dev/api/operators/reduce) ([doc](https://www.learnrxjs.io/learn-rxjs/operators/transformation/reduce), [demo](https://reactive.how/reduce), [video](https://www.youtube.com/watch?v=myEeo2rZc3g&feature=youtu.be)) : reduces the values from source observable to a single value that's emitted when the source completes
    * [concatMap](https://rxjs.dev/api/operators/concatMap) ([doc](https://www.learnrxjs.io/learn-rxjs/operators/transformation/concatmap)) : map values to inner observable, subscribe and emit in order
    * [mergeMap](https://rxjs.dev/api/operators/mergeMap) ([doc](https://www.learnrxjs.io/learn-rxjs/operators/transformation/mergemap), [video](https://www.youtube.com/watch?v=b59tcUwfpWU&feature=youtu.be)) : map to observablemit values
    * [switchMap](https://rxjs.dev/api/operators/switchMap) ([doc](https://www.learnrxjs.io/learn-rxjs/operators/transformation/switchmap), [video](https://www.youtube.com/watch?v=6lKoLwGlglE&feature=youtu.be)) : map to observable, complete previous inner observablemit values
    * [bufferTime](https://rxjs.dev/api/operators/bufferTime) ([doc](https://www.learnrxjs.io/learn-rxjs/operators/transformation/buffertime)) : collect emitted values until provided time has passedmit as array
  * [Utility](https://www.learnrxjs.io/learn-rxjs/operators/utility)
    * [tap](https://rxjs.dev/api/operators/tap) ([doc](https://www.learnrxjs.io/learn-rxjs/operators/utility/do)) : transparently perform actions or side-effects, such as logging
* Operators can be grouped by common behaviors, 
  * [Operators that **flatten**](https://www.learnrxjs.io/learn-rxjs/concepts/rxjs-primer#operators-that-flatten): Operators that manage the subscription of an inner observable
    * [Operators that flatten with **switch**](https://www.learnrxjs.io/learn-rxjs/concepts/rxjs-primer#operators-that-switch): switch based operators will turn off (unsubscribe) the current inner observable and turn on a new inner observable on emissions from the source
    * [Operators that flatten with **concat**](https://www.learnrxjs.io/learn-rxjs/concepts/rxjs-primer#operators-that-concat): comparable to a line at the ATM machine, the next transaction can't begin until the previous completes; useful operators when order of execution is important
    * [Operators that flatten with **merge**](https://www.learnrxjs.io/learn-rxjs/concepts/rxjs-primer#operators-that-merge): merge operators are useful in situations where you want to trigger an action when an event from one of many sources occurs
* Subjects
  * [Subject](https://rxjs.dev/api/index/class/Subject) ([doc](https://www.learnrxjs.io/learn-rxjs/subjects/subject), [video](https://www.youtube.com/watch?v=rdK92pf3abs&feature=youtu.be)): A Subject is a special type of Observable that allows values to be multicasted to many Observers. Subjects are like EventEmitters
  * [BehaviourSubject](https://rxjs.dev/api/index/class/BehaviorSubject) ([video](https://www.youtube.com/watch?v=-mwNLRbfKmU&feature=youtu.be)): a variant of Subject that requires an initial value and emits its current value whenever it is subscribed to
* Miscelleanous
  * [naming conventions](https://angular.io/guide/rx-library#naming-conventions-for-observables): observables should be name with a trailing "$" sign
  * It's possible to unsubscribe to the subscription inside the callback:
       ```
       this.subscription = observable.subscribe(() => {
         this.subscription.unsubscribe();
         ...
       });
       ```
* References docs
  * [Learn RxJS](https://www.learnrxjs.io/)
  * [Learn RxJS operators and Reactive Programming principles](https://reactive.how/)
  * [RxJS Acamind course](https://academind.com/learn/javascript/understanding-rxjs/)
  * [callback vs Promises vs RxJS Observables vs async/await](https://academind.com/learn/javascript/callbacks-vs-promises-vs-rxjs-vs-async-awaits/)
  * [Exercices with RxJS](http://reactivex.io/learnrx/)

[*Go to top*](#RxJS)
