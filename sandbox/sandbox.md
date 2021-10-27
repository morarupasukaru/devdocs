# Sandbox

Compilations of sandbox projects (2021 - now) that are basic examples of the webstack described in
[devdocs](../README.md).

* RxJS patterns
  * [debounce user input](./rxjs-debounce-user-input/README.md) 
    illustrate a RxJS pattern to delay user inputs submission to avoid unnecessary processing
  * [map-filter-reduce](./rxjs-map-filter-reduce/README.md) 
    illustrate an example how to map/filter/reduce data with RxJS
  * [stateless observable service and store service](./rxjs-stateless-observable-and-store-services/README.md)
    illustrate RxJS patterns that hide complexity betwen a simple API with Observables
  * [single data observable](./rxjs-single-data-observable/README.md)
    illustrate a RxJS pattern to merge several observables into a single one to ease use
    their uses in component's template by calling a unique async pipe
  * [error handling strategies](./rxjs-error-handling/README.md)
    show in actions different ways to handle error with RxJS

*coming in following months:*
* [words](./words/README.md) as example of an [Angular + SpringBoot webstack](https://github.com/morarupasukaru/devdocs) with
  * [Contract first REST API with OpenAPI 3](./words/words-api/README.md)
  * [Secure REST API implementation with SpringBoot](./words/words-backend/README.md)
  * [Secure single page application with Angular](./words/words-frontend/README.md)
    * including automate testing

*coming later:*
* Java Stream patterns