# Spring Boot

[Spring Boot](https://spring.io/projects/spring-boot#learn) 
makes it easy to create stand-alone, production-grade Java/Spring based Applications that you can "just run". (springboot.devdoc)
.d
* [Spring Initializr](https://start.spring.io/) : wizard to initialize a Spring Boot application
* [Spring Framework](https://spring.io/projects/spring-framework#overview) is an application framework that 
  provide [dependency injection (DI) or Inversion of Control (IoC)](https://docs.spring.io/spring-framework/docs/current/reference/html/core.html#beans-introduction)
* [Spring Boot quickstart guide](https://spring.io/quickstart)
* [Spring Web MVC](https://docs.spring.io/spring/docs/current/spring-framework-reference/web.html) 
  is a Java framework which is used to build web applications
  * tutorials: [producing](https://spring.io/guides/gs/rest-service/) and 
  [consuming a REST web service](https://spring.io/guides/gs/consuming-rest/), 
  [uploading files](https://spring.io/guides/gs/uploading-files/), 
  [testing web layer](https://spring.io/guides/gs/testing-web/), 
  [building RESTful service](https://spring.io/guides/tutorials/rest/)
  * [ResponseEntity](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/http/ResponseEntity.html) to manipulate the HTTP response
  * [UriComponentsBuilder](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/util/UriComponentsBuilder.html) helps to create [UriComponents](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/util/UriComponents.html) (URI)
    * UriComponentsBuilder can be injected right into a controller method
      ```java
      @RequestMapping(method = RequestMethod.POST)
      public ResponseEntity<Customer> createCustomer(@RequestBody Customer newCustomer, UriComponentsBuilder builder) {
        // implementation
      }
      ```
* [Spring WebFlux](https://docs.spring.io/spring/docs/current/spring-framework-reference/web-reactive.html) 
  is a reactive-stack web framework
  * tutorials: [reactive REST](https://spring.io/guides/gs/reactive-rest-service/), 
    [circuit breaker guide](https://spring.io/guides/gs/cloud-circuit-breaker/)
* [Spring Data R2DBC](https://spring.io/projects/spring-data-r2dbc) 
  ease implement R2DBC (Reactive Relational Database Connectivity) based repositories and can be used with 
  Spring WebFlux; [tutorial](https://spring.io/guides/gs/accessing-data-r2dbc/)
  * [initialize a database using basic SQL scripts](https://docs.spring.io/spring-boot/how-to/data-initialization.html#howto.data-initialization.using-basic-sql-scripts)
    * ... by default, Spring Boot loads schema scripts from `optional:classpath*:schema.sql` and data scripts from `optional:classpath*:data.sql` ...
  * other classes: [CrudRepository](https://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/repository/CrudRepository.html) and
    [PagingAndSortingRepository](https://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/repository/PagingAndSortingRepository.html)
  * Spring Data generate itself queries (sql) related repositories
  * it's still possible to
    [define query methods](https://docs.spring.io/spring-data/relational/reference/repositories/query-methods-details.html)
    based on method name convention or manually with [@Query](https://docs.spring.io/spring-data/jpa/docs/current/api/org/springframework/data/jpa/repository/Query.html)
* [Spring Boot Actuator](https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#actuator) 
  add monitor by using 
  HTTP [endpoints](https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#production-ready-endpoints) 
  or with JMX; see [tutorial](https://spring.io/guides/gs/actuator-service/)
* [Spring Security](https://spring.io/projects/spring-security) to provide authentication & authorization; 
  * tutorials: [Spring Security architecture](https://spring.io/guides/topicals/spring-security-architecture/), 
    [securing a web application](https://spring.io/guides/gs/securing-web/), 
    [enabling CORS](https://spring.io/guides/gs/rest-service-cors/), 
    [Spring Boot and OAuth2](https://spring.io/guides/tutorials/spring-boot-oauth2/), 
    [Spring Security and Angular](https://spring.io/guides/tutorials/spring-security-and-angular-js/)
  * [Security Filters](https://docs.spring.io/spring-security/reference/servlet/architecture.html#servlet-security-filters) (Filter Chain)
    * each filter in the chain decides whether to allow request processing to continue, or not
    * Spring Security inserts a filter which checks the user’s authentication and returns with a 401 UNAUTHORIZED   
response if the request is not authenticated
    * [override default configuration](https://docs.spring.io/spring-security/reference/servlet/configuration/java.html#jc-httpsecurity)
      of [SecurityFilterChain](https://docs.spring.io/spring-security/site/docs/current/api/org/springframework/security/web/SecurityFilterChain.html)
    * use [InMemoryUserDetailsManager](https://docs.spring.io/spring-security/site/docs/current/api/org/springframework/security/provisioning/InMemoryUserDetailsManager.html)
      to test basic authentication, see [InMemoryUserDetailsManager Java Configuration](https://docs.spring.io/spring-security/reference/servlet/authentication/passwords/in-memory.html)
  * Spring Security provides [Authorization](https://docs.spring.io/spring-security/reference/servlet/authorization/architecture.html) via [Role-Based Access Control (RBAC)](https://en.wikipedia.org/wiki/Role-based_access_control)
    * principal has roles
    * resource (or operation) specifies which roles a principal must have
    * configure authorization by calling ecurityFilterChain by calling hasRole or hasAuthority
    * use [@WithMockUser](https://docs.spring.io/spring-security/site/docs/current/api/org/springframework/security/test/context/support/WithMockUser.html) to test authorization of [InMemoryUserDetailsManager](https://docs.spring.io/spring-security/site/docs/current/api/org/springframework/security/provisioning/InMemoryUserDetailsManager.html) for testing purpose
    * Spring Boot allow to [model the authorization](https://docs.spring.io/spring-security/reference/servlet/authorization/authorize-http-requests.html) depend on different use-cases
      * e.g. add [hasRole()/hasAuthority() to SecurityFilterChain](https://docs.spring.io/spring-security/reference/servlet/authorization/authorize-http-requests.html#authorizing-endpoints) to restrict endpoints to provided roles
      * or [Spring Security Method Security](https://docs.spring.io/spring-security/reference/servlet/authorization/method-security.html) to have authorization at the method level instead of request level
    *  [Principal](https://docs.oracle.com/en/java/javase/21/docs/api//java.base/java/security/Principal.html) holds our user's authenticated and can be injected to RestController
    ```java
    @GetMapping("/{requestedId}")
    private ResponseEntity<Xyz> findById(@PathVariable Long requestedId, Principal principal) {
      ... principal.getName() ...
    ```
  * [@CrossOrigin](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/CrossOrigin.html) used to specify a list of allowed sites for [Cross-Origin Resource Sharing (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) to relax [Same Origin Policy (SOP)](https://en.wikipedia.org/wiki/Same-origin_policy)
  * spring boot support [CSRF Token](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html#synchronizer-token-pattern) to protect against [Cross-Site Request Forgery (CSRF)](https://en.wikipedia.org/wiki/Cross-site_request_forgery) attacks like [Cross-Site Scripting (XSS)](https://owasp.org/www-community/attacks/xss/)
    * CSRF must be enabled (default) for any request that could be processed by a browser by normal users
    * [CSRF protection can be disabled](https://docs.spring.io/spring-security/reference/servlet/exploits/csrf.html#disable-csrf) can be disabled by non-browser clients.
    * see [Testing with CSRF Protection](https://docs.spring.io/spring-security/reference/servlet/test/mockmvc/csrf.html)
  * if spring security is active, '500 INTERNAL_SERVER_ERROR' is returned as '403 FORBIDDEN' to prevent "leaking" information
* [Spring Batch](https://spring.io/projects/spring-batch#overview) is a batch framework;
  [tutorial](https://spring.io/guides/gs/batch-processing/)
* [Spring Data JPA](https://spring.io/projects/spring-data-jpa#overview) 
  ease implement [JPA](https://en.wikipedia.org/wiki/Jakarta_Persistence) based repositories;
  [tutorial](https://spring.io/guides/gs/accessing-data-jpa/)
* [Spring Data JDBC](https://spring.io/projects/spring-data-jdbc#overview)
  ease implement JDBC based repositories; [tutorial](https://spring.io/guides/gs/relational-data-access/)
* [Spring Web Services](https://spring.io/projects/spring-ws)
  ease implement SOAP services
  * tutorials: [producing](https://spring.io/guides/gs/producing-web-service/), 
    [consuming a SOAP web service](https://spring.io/guides/gs/consuming-web-service/)
* other [tutorials](https://spring.io/guides#getting-started-guides)
  * [managing transactions](https://spring.io/guides/gs/managing-transactions/)
  * [caching data](https://spring.io/guides/gs/caching/): 
    see [documentation](https://docs.spring.io/spring-framework/docs/current/reference/html/integration.html#cache)
  * [scheduling tasks](https://spring.io/guides/gs/scheduling-tasks/)
  * [asynchronous methods](https://spring.io/guides/gs/async-method/): 
    see [documentation](https://docs.spring.io/spring/docs/current/spring-framework-reference/integration.html#scheduling)
  * [WebSocket](https://spring.io/guides/gs/messaging-stomp-websocket/)
  * [GraphQL](https://spring.io/guides/gs/graphql-server)
  * [docker](https://spring.io/guides/topicals/spring-boot-docker)
  * [kubernetes](https://spring.io/guides/gs/spring-boot-kubernetes)
  * [API documentation with Restdocs](https://spring.io/guides/gs/testing-restdocs)
* concepts
  * [spring bean scope](https://www.baeldung.com/spring-bean-scopes)
  * [spring component vs repository vs service](https://www.baeldung.com/spring-component-repository-service)
  * [auto-configuration](https://docs.spring.io/spring-boot/reference/using/auto-configuration.html)
  * [@Autowired](https://docs.spring.io/spring-framework/reference/core/beans/annotation-config/autowired.html) should only be used for test classes
* [testing](https://docs.spring.io/spring-boot/reference/testing/spring-boot-applications.html)
  * [JacksonTester](https://docs.spring.io/spring-boot/api/java/org/springframework/boot/test/json/JacksonTester.html) as a wrapper to the Jackson JSON parsing library
  * [SpringBootTest](https://docs.spring.io/spring-boot/api/java/org/springframework/boot/test/context/SpringBootTest.html) to start a Spring Boot application and make it available for a test
  * [JsonPath](https://github.com/json-path/JsonPath) as a java DSL for reading JSON documents
    ```java
    DocumentContext documentContext = JsonPath.parse(... json as string ...);
    ```
  * [TestRestTemplate](https://docs.spring.io/spring-boot/api/java/org/springframework/boot/test/web/client/TestRestTemplate.html)
    as test helper that’ll allow us to make HTTP requests to the locally running application
  * [DirtiesContext](https://docs.spring.io/spring-framework/reference/testing/annotations/integration-spring/annotation-dirtiescontext.html) is a Spring testing annotation. It indicates the associated test/method or class modifies the ApplicationContext. It tells the testing framework to close and recreate the context for later tests.
  * [assertThat(...).containsExactlyInAnyOrder(...)](https://www.javadoc.io/doc/org.assertj/assertj-core/latest/org/assertj/core/api/AbstractIterableAssert.html#containsExactlyInAnyOrder(ELEMENT...)) of [assertj](https://assertj.github.io/doc/#assertj-core) might be usefull sometime
* other Spring classes: [Pageable](https://docs.spring.io/spring-data/commons/docs/current/api/org/springframework/data/domain/Pageable.html)
* tools: [spring-boot-migrator](https://github.com/spring-projects-experimental/spring-boot-migrator) 
* alternatives to SpringBoot:
  [Quarkus](https://quarkus.io/),
  [Micronaut](https://micronaut.io/),
  [Dropwizard](https://www.dropwizard.io/en/latest/),
  [NodeJS](https://nodejs.org/) (JS), 
  [Deno](https://deno.land/) (JS)
  * see [Spring vs. the World: Comparing Spring Boot Alternatives](https://www.jrebel.com/blog/spring-boot-alternatives)

[*Go to parent page*](../README.md)

*(Page mainly written in july 2020; links checked on 09.02.2024)*
(springboot-devdoc)
