# RxJS

[RxJS](https://rxjs.dev/guide/overview) (Reactive Extensions for JavaScript) is a library for reactive 
programming using observables that makes it easier to compose asynchronous or callback-based code.

[Reactive programming using observables](http://reactivex.io/) exists also in various other languages like [RxJava](https://github.com/ReactiveX/RxJava) for java.

* see [RxJS introduction](https://angular.io/guide/rx-library) for a quick intro
* [RxJS](https://rxjs.dev/guide/overview) concepts
  * Streams of values can emit a single or multi-values and can complete or not (infinite streams)
  * [Observable](https://rxjs.dev/guide/observable)
    represents a definition of stream of values; the idea of an invokable collection of future values or events
    * stream of values are created as soon as [Observable.subscribe()](https://rxjs.dev/api/index/class/Observable#subscribe)
      method is called
    * higher-order observable is an observable that emits observable that can be subscribed later on
  * Observable contract
    * if stream emit error or completes, it will never complete or emit values afterward
    * if stream completes, it will never emit error or values afterward
    * infinite streams are allowed (without completion or error)
  * [Observer](https://rxjs.dev/guide/observer)
    is a collection of callbacks that knows how to listen to values delivered by the Observable
  * [pipe](https://www.learnrxjs.io/learn-rxjs/concepts/rxjs-primer#pipe) function allows to assemble a ```pipe```-line 
    of operators on observable data
  * [Operators](https://rxjs.dev/guide/operators)
    are pure functions that enable a functional programming style of dealing with collections with operations like map, 
    filter, concat, reduce, etc.
  * [Subscription](https://rxjs.dev/guide/subscription)
    represents the execution of an Observable, is primarily useful for cancelling the execution
  * [Subject](https://rxjs.dev/api/index/class/Subject) is a special type of Observable
    that allows values to be multicasted to many Observers. Subjects are like Angular [EventEmitter](https://angular.io/api/core/EventEmitter)
    * to prevent misuses of Subject
      * try to create an Observable with creation operators if possible
      * try to hide Subject; give only public access to the Observable part of Subject, by calling [Subject.asObservable()](https://rxjs.dev/api/index/class/Subject#asObservable)
    * [BehaviourSubject](https://rxjs.dev/api/index/class/BehaviorSubject) is the most usefull variant of Subject that 
      requires an initial value and emits its current value whenever it is subscribed to
      * subscriber after observable completion won't receive any value
    * [AsyncSubject](https://rxjs.dev/api/index/class/AsyncSubject) is a variant of Subject that only emits its 
      latest value to all its observers on completion (and also if subscribing happens after observable completion)
      * usefull for long-running computation
    * [ReplaySubject](https://rxjs.dev/api/index/class/ReplaySubject) is a variant of Subject that "replays" old values 
      to new subscribers by emitting them when they first subscribe (even after observable completion)
  * [Scheduler](https://rxjs.dev/guide/scheduler) are centralized dispatchers to control concurrency, allowing us to 
    coordinate when computation happens on e.g. setTimeout or requestAnimationFrame or others
  * [Marble diagrams](https://rxjs.dev/guide/operators#marble-diagrams) are visual representations of how operators work over time
* [Common operators](https://angular.io/guide/rx-library#common-operators) grouped by [categories](https://rxjs.dev/guide/operators#categories-of-operators)
  * Creation operators (*not pipeable*)
    * [from](https://rxjs.dev/api/index/function/from)
      converts array, promise, iterable into an observable
    * [fromEvent](https://rxjs.dev/api/index/function/fromEvent)
      creates an observable from DOM events
    * [of](https://rxjs.dev/api/index/function/of)
      creates an observable that emits the arguments and then completes
    * [interval](https://rxjs.dev/api/index/function/interval)
      creates an observable that emits sequential numbers every specified interval of time
    * [timer](https://rxjs.dev/api/index/function/timer)
      is like interval, but you can specify when should the emissions start
    * [throwError](https://rxjs.dev/api/index/function/throwError)
      creates an observable that just emits an error
  * Join Creation operators (*not pipeable*)
    * [combineLatest](https://rxjs.dev/api/index/function/combineLatest)
      whenever any input observable emits a value, emit the last emitted value from each observable
    * [concat](https://rxjs.dev/api/index/function/concat)
      concatenates multiple observables together by sequentially emitting their values, one observable after the other
    * [forkJoin](https://rxjs.dev/api/index/function/forkJoin)
      wait for observables emitting in parallel to complete and then combine last values they emitted
      * cautious: all observables must complete
    * [merge](https://rxjs.dev/api/index/function/merge)
      creates an observable which concurrently emits all values from every given input observable
    * [zip](https://rxjs.dev/api/index/function/zip)
      combine and emit n-th value of any observables as an array
      * difference with [combineLatest](https://rxjs.dev/api/index/function/combineLatest):
        zip waits until all observables emit values with same index with combine values
  * Join operators
    * [concatAll](https://rxjs.dev/api/operators/concatAll)
      flattens an observable-of-observables by putting one inner observable after the other
    * [exhaustAll](https://rxjs.dev/api/operators/exhaustAll)
      flattens an observable-of-observables by dropping the next inner observables while the current inner is
      still executing
    * [mergeAll](https://rxjs.dev/api/operators/mergeAll)
      flattens an observable-of-observables in parrallel
    * [startWith](https://rxjs.dev/api/operators/startWith)
      returns an observable that emits the items you specify as arguments before it begins to emit items emitted by 
      the source observable
    * [switchAll](https://rxjs.dev/api/operators/switchAll)
      flattens an observable-of-observables; producing values only from the most recent observable sequence
      (stop emmiting last observable before emitting a new one)
    * [withLatestFrom](https://rxjs.dev/api/operators/withLatestFrom) 
      combines the source observable with other observables to create an observable whose values are calculated from
      the latest values of each as an array, only when the source emits
  * Filtering operators
    * [debounceTime](https://rxjs.dev/api/operators/debounceTime)
      returns an observable that delays the emissions of a source observable only after a particular time span has passed, 
      and may drop some values if they occur too frequently 
      * can be used to limit emited values from a streams of typed search input
      * cautious: value could never be emited if they are never stable enough
    * [distinctUntilChanged](https://rxjs.dev/api/operators/distinctUntilChanged)
      returns an observable that emits all items emitted by the source observable that are distinct by comparison 
      from the previous item (useful for key/mouse events)
    * [filter](https://rxjs.dev/api/operators/filter)
      returns an Observable that emits a value from the source if it passes a criterion function (like [Array.prototype.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter))
    * [first](https://rxjs.dev/api/operators/first)
      emits the first item or emits only the first value that passes some test
    * [take](https://rxjs.dev/api/operators/take)
      takes the first count values from the source, then completes
      * hint: depend on the concept, unsubscribe on the returned subscription is not required 
    * [takeUntil](https://rxjs.dev/api/operators/takeUntil)
      emits the values emitted by the source observable until a notifier observable emits its first value, 
      then completes
      * see [destroy subject pattern](https://barista.dynatrace.com/components/best-practices-and-patterns#destroy-subject-pattern) to unsubscribe several subscriptions with takeUntil
    * [throttle](https://rxjs.dev/api/operators/throttle)
      emits a value from the source observable, then ignores subsequent source values for a duration determined by
      another observable, then repeats this process;
      * can be used to limit emited values from a verbose source
      * cautious: last emiting value could be not emited (see marble diagram)
  * Transformation operators
    * [bufferTime](https://rxjs.dev/api/operators/bufferTime)
      buffers the source observable values for a specific time period; emits buffered values as an array 
    * [concatMap](https://rxjs.dev/api/operators/concatMap)
      maps each value from source to an observable (apply a projection function that returns an observable), 
      then flattens all of these inner observables using [concatAll](https://rxjs.dev/api/operators/concatAll)
    * [exhaustMap](https://rxjs.dev/api/operators/exhaustMap)
      maps each value from source to an observable
      and flattens all of these inner observables using [exhaust](https://rxjs.dev/api/operators/exhaust)
      (dropping the next inner observables while the current inner is still executing)
    * [map](https://rxjs.dev/api/operators/map)
      maps each value from source (apply projection function); like [Array.prototype.map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
    * [mergeMap](https://rxjs.dev/api/operators/mergeMap)
      maps each value from source to an observable
      and flattens all of these inner observables using [mergeAll](https://rxjs.dev/api/operators/mergeAll) 
      (done in parrallel)
    * [scan](https://rxjs.dev/api/operators/scan)
      reduces the values from source observable (apply a reducer function) and emits all accumulated (intermediate) values
      * it's like [reduce](https://rxjs.dev/api/operators/reduce), but emits accumuled value after each update
    * [switchMap](https://rxjs.dev/api/operators/switchMap)
      maps each value from source to an observable
      and flattens all of these inner observables using [switchAll](https://rxjs.dev/api/operators/switchAll) 
      (stop emmiting last observable before emitting a new one)
    * [reduce](https://rxjs.dev/api/operators/reduce)
      reduces the values from source observable (apply a reducer function) 
      and returns the accumulated result when the source completes
  * Utility operators
    * [tap](https://rxjs.dev/api/operators/tap) 
      returns an Observable identical to the source, but runs the specified Observer or callback(s) for each item
    * [delayWhen](https://rxjs.dev/api/operators/delayWhen) 
      delays the emission of items from the source observable by a given time span determined by the emissions of 
      another observable
  * Multicasting operators
    * [shareReplay](https://rxjs.dev/api/operators/shareReplay)
      share source and replay specified number of emissions on subscription
      * quite useful to share response of http request and avoid unnecessary requests
  * Error Handling operators
    * [catchError](https://rxjs.dev/api/operators/catchError)
      continues with a different observable when there's an error
    * [retry](https://rxjs.dev/api/operators/retry) 
      returns an observable that mirrors the source observable and if the source observable calls error, this method 
      will resubscribe to the source observable for a given number of retry
    * [retryWhen](https://rxjs.dev/api/operators/retryWhen)
      returns the source observable modified with retry logic defined in a notifier observabe (parameter); 
      notifier decide whether to call complete, error on source observable or retry;
      cautious: function that create the notifier observable with retry logic is called once on error of the source 
      observable
    * [finalize](https://rxjs.dev/api/operators/finalize)
      returns an observable that mirrors the source, but will call the specified function on termination (complete or error)
* Miscelleanous
  * naming convention: observables should be named with a trailing $ sign
  * it's possible to unsubscribe to the subscription inside the callback:
    ```typescript
    this.subscription = observable.subscribe(() => {
      this.subscription.unsubscribe();
      ...
    });
    ```
* Design patterns (sandbox applications)
  * [debounce user input](https://github.com/morarupasukaru/rxjs-patterns/blob/master/rxjs-debounce-user-input/README.md)
    illustrate a RxJS pattern within an Angular application to delay user inputs submission to avoid
    unnecessary processing
  * [map-filter-reduce](https://github.com/morarupasukaru/rxjs-patterns/blob/master/rxjs-map-filter-reduce/README.md)
    illustrate an example of map/filter/reduce data with RxJS
  * [stateless observable service and store service](https://github.com/morarupasukaru/rxjs-patterns/blob/master/rxjs-stateless-observable-and-store-services/README.md)
    illustrate RxJS patterns that hide complexity betwen a simple API with Observables
  * [single data observable](https://github.com/morarupasukaru/rxjs-patterns/blob/master/rxjs-single-data-observable/README.md)
    illustrate a RxJS pattern to merge several observables into a single one to ease use
    their uses in component's template by calling a unique async pipe
  * [error handling strategies](https://github.com/morarupasukaru/rxjs-patterns/blob/master/rxjs-error-handling/README.md)
    show in actions different ways to handle error with RxJS
* Documentation
  * [RxJS official doc](https://rxjs.dev/guide/overview)
  * [RxJS](https://angular.io/guide/rx-library) from Angular docs   
  * [Callback vs Promises vs RxJS Observables vs async/await](https://academind.com/tutorials/callbacks-vs-promises-vs-rxjs-vs-async-awaits)
  * [Exercices with RxJS](http://reactivex.io/learnrx/)
  * [Understanding RxJS](https://academind.com/tutorials/understanding-rxjs) videos
  * [RxJS 6 in practice](https://www.udemy.com/course/rxjs-course/) and 
    [Reactive Angular Course](https://www.udemy.com/course/rxjs-reactive-angular-course/) 
    courses (contents are overlapping but both courses are great to follow)

[*Go to parent page*](README.md)

*(Page mainly written in september 2020; links checked on 28.02.2024)*
