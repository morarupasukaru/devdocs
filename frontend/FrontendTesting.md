# Frontend testing

Compilation of links about frontend testing

* test libraries
  * [Jasmine](https://jasmine.github.io/), 
    see [cheatsheet](https://devhints.io/jasmine) (used by Angular)
  * [Chai](https://www.chaijs.com/) and also [Chai as Promised](https://github.com/domenic/chai-as-promised/)
  * [Jest](https://jestjs.io/) is both a test runner and library; *nice to try*
* test runners
  * [karma](https://karma-runner.github.io/latest/index.html) (used by Angular)
  * [mocha](https://mochajs.org/) require an assertion library, e.g. Chai
  * jest
* e2e tests: [Selenium](https://www.selenium.dev/), [Puppeteer](https://pptr.dev/), [Cypress](https://www.cypress.io/)
* angular libs
  * [ng-mocks](https://github.com/ike18t/ng-mocks) as alternative to spy
  * [shallow-render](https://github.com/getsaf/shallow-render) as alternative to Angular testing with shallow rendering and easy mocking
* documentation:
  * Jest: [Testing JavaScript code with Jest](https://academind.com/learn/javascript/javascript-testing-introduction/), 
    [Mocking Async Code](https://academind.com/learn/javascript/javascript-testing-mocking-async-code/)
  * Mocha & Chai: [Testing JavaScript Promises with Mocha and Chai](https://www.sitepoint.com/promises-in-javascript-unit-tests-the-definitive-guide/)


## Testing in Angular

[Testing](https://angular.io/guide/testing) to write and run unit tests

* isolated tests: [Jasmine](https://jasmine.github.io/) unit test without angular bundle
  * [testing services](https://angular.io/guide/testing-services#testing-services)
  * [testing pipes](https://angular.io/guide/testing-pipes)
* shallow component tests / non isolated tests: unit test with [TestBed](https://angular.io/guide/testing-services#angular-testbed)
  to have angular dependency injection
  * non isolated test is a "shallow component test" that test a component and its template, without its dependencies by mocking them
  * e.g. [testing component DOM](https://angular.io/guide/testing-components-basics#component-dom-testing)
* hints:
  * [fixture.detectChanges()](https://angular.io/guide/testing-components-scenarios#detectchanges) call is required to perform data binding
  * [spy](https://angular.io/guide/testing-components-scenarios#testing-with-a-spy) can be used to mock remote servers
* testing asynchronous code
  * [async](https://angular.io/guide/testing-components-scenarios#component-with-async-service) and whenStable() methods are used to test asynchronous code;
  * [whenStable()](https://angular.io/guide/testing-components-scenarios#whenstable) is used to wait that all asynchronous code are finished
  * [fakeAsync](https://angular.io/guide/testing-components-scenarios#async-test-with-fakeasync) and tick methods are an alternative to async
  * [tick](https://angular.io/guide/testing-components-scenarios#the-tick-function) method is then used to say "finish all asynchronous tasks"
* course: [Angular Testing Masterclass](https://www.udemy.com/course/angular-testing-course/) : nice course containing helpfull explanation about asynchronous testing

[*Go to parent page*](../README.md)

*(Page mainly written in december 2020; links checked on 17.02.2022)*
