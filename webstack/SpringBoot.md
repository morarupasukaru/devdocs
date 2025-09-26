# Spring Boot

[Spring Boot](https://spring.io/projects/spring-boot#learn) 
makes it easy to create stand-alone, production-grade Java/Spring based Applications that you can "just run".
* [Spring Initializr](https://start.spring.io/) : wizard to initialize a Spring Boot application
* [Spring Framework](https://spring.io/projects/spring-framework#overview) is an application framework that 
  provide [dependency injection (DI) or Inversion of Control (IoC)](https://docs.spring.io/spring-framework/docs/current/reference/html/core.html#beans-introduction)
* [Spring Boot quickstart guide](https://spring.io/quickstart)
* [Spring Web MVC](https://docs.spring.io/spring-framework/reference/web/webmvc.html#mvc) 
  is a Java framework which is used to build web applications
  * tutorials: [producing](https://spring.io/guides/gs/rest-service/) and 
  [consuming a REST web service](https://spring.io/guides/gs/consuming-rest/), 
  [uploading files](https://spring.io/guides/gs/uploading-files/), 
  [testing web layer](https://spring.io/guides/gs/testing-web/), 
  [building RESTful service](https://spring.io/guides/tutorials/rest/)
   * use [RestClient](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/client/RestClient.html) instead
     [RestTemplate](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/client/RestTemplate.html)   
* [Spring WebFlux](https://docs.spring.io/spring/docs/current/spring-framework-reference/web-reactive.html) 
  is a reactive-stack web framework
  * tutorials: [reactive REST](https://spring.io/guides/gs/reactive-rest-service/), 
    [circuit breaker guide](https://spring.io/guides/gs/cloud-circuit-breaker/)
* [Spring Data R2DBC](https://spring.io/projects/spring-data-r2dbc) 
  ease implement R2DBC (Reactive Relational Database Connectivity) based repositories and can be used with 
  Spring WebFlux; [tutorial](https://spring.io/guides/gs/accessing-data-r2dbc/)
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
* [Spring Batch](https://spring.io/projects/spring-batch#overview) is a batch framework;
  [tutorial](https://spring.io/guides/gs/batch-processing/)
* [Spring Data JPA](https://spring.io/projects/spring-data-jpa#overview) 
  ease implement [JPA](https://en.wikipedia.org/wiki/Jakarta_Persistence) based repositories;
  [tutorial](https://spring.io/guides/gs/accessing-data-jpa/)
* [Spring Data JDBC](https://spring.io/projects/spring-data-jdbc)
  is a simple ORM (Object-Relational Mapping framework); it ease implement JDBC based repositories; [tutorial](https://spring.io/guides/gs/relational-data-access/)
  * use [JdbcClient](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/jdbc/core/simple/JdbcClient.html) instead
    [JdbcTemplate](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/jdbc/core/JdbcTemplate.html)
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
  * [spring-modulith](https://spring.io/projects/spring-modulith#overview)
* [Spring Boot Best Practices](https://mshemeel.github.io/java-learning/spring-boot/spring-boot-best-practices/) 
* tools:
  * [spring-boot-migrator](https://github.com/spring-projects-experimental/spring-boot-migrator)
  * [Spring Tools 4](https://spring.io/tools) for the IDEs integration
* courses
  * [Spring Academy - Learning path - Spring Certified Professional](https://spring.academy/paths)
  * [Spring Boot 3, Spring 6 & Hibernate for Beginners](https://www.udemy.com/course/spring-hibernate-tutorial/)
  * Spring Professional Certification Exam Tutorial
    * [Module 1 - Container, Dependency, and IoC](https://www.udemy.com/course/spring-certified-tutorial) /
      [Tests Module 1](https://www.udemy.com/course/spring-professional-certification-practice-tests-module-01)
    * [Module 2 - Aspect Oriented Programming](https://www.udemy.com/course/spring-professional-certification-exam-tutorial-module-02) /
      [Tests Module 2](https://www.udemy.com/course/spring-professional-certification-practice-tests-module-02)
    * [Module 3 - Data Management: JDBC, Transactions, Spring Data JPA](https://www.udemy.com/course/spring-professional-certification-exam-tutorial-module-03) /
      [Tests Module 3](https://www.udemy.com/course/spring-professional-certification-practice-tests-module-03)
    * [Module 4 - Spring Boot, Spring Boot Auto Configuration, Spring Boot Actuator, Spring Boot Testing](https://www.udemy.com/course/spring-professional-certification-exam-tutorial-module-04-spring-boot) /
      [Tests Module 4](https://www.udemy.com/course/spring-professional-certification-practice-tests-module-04)
    * [Module 5 - Spring MVC and the Web Layer](https://www.udemy.com/course/spring-professional-certification-exam-tutorial-module-05) /
      [Tests Module 5](https://www.udemy.com/course/spring-professional-certification-practice-tests-module-05)
    * [Module 6 - Spring Security](https://www.udemy.com/course/spring-professional-certification-exam-tutorial-module-06) /
      [Tests Module 6](https://www.udemy.com/course/spring-professional-certification-practice-tests-module-06)
    * [Module 7 - Spring REST](https://www.udemy.com/course/spring-professional-certification-exam-tutorial-module-07) /
      [Tests Module 7](https://www.udemy.com/course/spring-professional-certification-practice-tests-module-07)
    * [Module 8 - Spring Testing](https://www.udemy.com/course/spring-professional-certification-exam-tutorial-module-08) /
      [Tests Module 8](https://www.udemy.com/course/spring-professional-certification-practice-tests-module-08)
    * see also [Spring certification know-how](https://github.com/DalvirSinghBains/spring-cert-prep-2025) 
* alternatives to SpringBoot:
  [Quarkus](https://quarkus.io/),
  [Micronaut](https://micronaut.io/),
  [Dropwizard](https://www.dropwizard.io/en/latest/),
  [Node.js](https://nodejs.org/) (JS), 
  [Deno](https://deno.land/) (JS)
  * see [Spring vs. the World: Comparing Spring Boot Alternatives](https://www.jrebel.com/blog/spring-boot-alternatives)

[*Go to parent page*](../README.md)

*(Page mainly written in july 2020, last update 25.03.2025; links checked on 09.02.2024)*
