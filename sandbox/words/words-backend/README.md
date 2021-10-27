# TODO

Example of a SpringBoot application that provide REST endpoints with OpenAPI 3 and various best-practises.

* Logging with SL4J (add custom MDC parameter, e.g. flow-id)
* Monitoring with Spring Actuator (which endpoints?)
  * check app state endpoint?
* Persistence with JPA
  * small memory footprint db (H2SQL?)
  * integration-test with DB (re-create db)
* REST Controller with Spring MVC
  * generated contract first DTO
  * swagger ui (with authentification/authorization for update operations)   
* Security with Spring Security
  * Secure with JWT

[*Go to parent page*](../README.md)
