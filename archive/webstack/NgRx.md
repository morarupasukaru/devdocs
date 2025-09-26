# NgRx

[NgRx](https://ngrx.io/) is used to manage application state
(see [comparisons](https://ordina-jworks.github.io/angular/2018/10/08/angular-state-management-comparison.html#:~:text=%20NGRX%20offers%20support%20for%20Selectors%20as%20constants.,similar%2C%20but%20uses%20functions%20inside%20the%20State%20class.)
of alternatives like [Redux](https://redux.js.org/),
[ngxs](https://www.ngxs.io/), [elf](https://ngneat.github.io/elf/))

* application state is the data used by the application at runtime; the *session data* (state is lost by application refresh)
* to not lose all important data, some of them are stored in the *persistent state* on backend (db)
* application state is scattered in several components, services
* for big projects, application state can be difficult to manage
* [RxJS](RxJS.md) ease management of the application state with Subject and Observable
* Angular does not force to have a clear structure about application state
* [Redux](https://redux.js.org/) is a state management pattern (available in ReactJS) and a library
* Redux library could be used in Angular
* [NgRx](https://ngrx.io/) is an Angular implementation of [Redux](https://redux.js.org/) and is therfore easier to use as Redux directly
    * using NgRX (or Redux) can avoid to fetch same data from backend and store them in memory
* Redux vs NgRx
    * NgRx provide injectable services
    * NgRx integrate/use RxJS to have Observable
    * NgRx is written in TypeScript
    * NgRx provide a concept *Side Effect* to support asynchronous code (e.g. http requests)
* Redux basics
    * lifecycle:
      ![Redux Lifecycle](https://res.cloudinary.com/practicaldev/image/fetch/s--fCDvEpjd--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://i.stack.imgur.com/LNQwH.png)
      *(source: [ABC of Redux](https://dev.to/radiumsharma06/abc-of-redux-5461))*
    * there is only one application state; the *Store*
    * services and components can interact between themselves but receives their state from the *Store* (with use of subscriptions)
    * change in the store are *dispatched* into *Actions*
    * an *Action* has a type and could have data; the *Payload*
    * *Actions* are sent to *Reducers* by dispatching them from the *Store*
    * an Action is dispatched to every *Reducers* no matter whether the reducer could handle the action or not
        * always provide a default case in reducer that returns the unchanged state
        * action.type must be unique in the whole application
    * *Reducers* copy a *State* from the *Store*, apply changes on it with the *Action* & *Payload* and saves the reduced State in the *Store*
    * *State* are immutable (or must be immutable)
    * a JavaScript object can be shallow-copied with spread operator: `const newObject = { ...object };`
* NgRx basics
    * lifecycle:
      ![NgRx Lifecycle](https://ngrx.io/generated/images/guide/store/state-management-lifecycle.png)
      *(source: [NgRx](https://ngrx.io/guide/store))*
    * [selectors](https://ngrx.io/guide/store/selectors): pure functions used for obtaining slices of store state.
        * see [example of selector](https://ngrx.io/guide/store/selectors#selecting-feature-states) that uses [createFeatureSelector](https://ngrx.io/api/store/createFeatureSelector) and [createSelector](https://ngrx.io/api/store/createSelector) functions
    * [feature state](https://ngrx.io/guide/store/reducers#registering-feature-state): state associated to a feature module
    * [effect](https://ngrx.io/guide/effects): allow to handle asynchronous events
        * Effects are long-running services that listen to an observable of every action dispatched from the Store.
        * Effects filter those actions based on the type of action they are interested in. This is done by using an operator.
        * Effects perform tasks, which are synchronous or asynchronous and return a new action (have to).
* other concepts
    * [@ngrx/router-store](https://ngrx.io/guide/router-store): module dispatching actions of route navigation
    * [@ngrx/store-devtools](https://ngrx.io/guide/store-devtools) extension allow seeing dispatched actions and Store changes
        * navigation can be replayed in combination with router-store with the time-travelling debugger; see following [blog](https://blog.angular-university.io/angular-ngrx-devtools/)
    * [runtime-checks](https://ngrx.io/guide/store/configuration/runtime-checks) : throws errors during development if some NgRx and Redux core concepts and best practices are violated (e.g. state immutability)
    * [meta-reducers](https://ngrx.io/guide/store/metareducers) are processed before handling the actions & normal reducers
    * [@ngrx/schematics](https://ngrx.io/guide/schematics) provides Angular CLI commands for generating/updating components/modules with NgRx.
    * [@ngrx/entity](https://ngrx.io/guide/entity) provides an API to manipulate and query entity collections (reduce the amount of code)
    * [@ngrx/data](https://ngrx.io/guide/data) is an extension that abstract NgRx and reduce amounts of work of entity collections (even more than [@ngrx/entity](https://ngrx.io/guide/entity)).
* docs:
    * [NgRx docs](https://ngrx.io/docs)
    * [example-app of ngrx/platform](https://github.com/ngrx/platform/tree/master/projects/example-app) is a project example with best-practises of NgRx
* courses:
  * [Angular material, angularfire & NgRx](https://www.udemy.com/angular-full-app-with-angular-material-angularfire-ngrx/)
  * [NgRx (with NgRx Data) - The Complete Guide](https://www.udemy.com/course/ngrx-course/)

[*Go to parent page*](README.md)

*(Page mainly written in 2019-2022; links checked on 28.02.2024)*
