# REST API Guidelines

Selection of [Zalando](https://opensource.zalando.com/restful-api-guidelines/#) REST API guidelines

* Guidelines
  * General
    * [MUST provide API specification using **OpenAPI**](https://opensource.zalando.com/restful-api-guidelines/#101)
    * SHOULD write **self-contained** API specification without references
    * [MUST write APIs using **U.S. English**](https://opensource.zalando.com/restful-api-guidelines/#103)
    * [SHOULD monitor **API usage**](https://opensource.zalando.com/restful-api-guidelines/#193)
  * Meta-Information
    * [MUST contain API **meta information**](https://opensource.zalando.com/restful-api-guidelines/#218)
    * [MUST use **semantic versioning**](https://opensource.zalando.com/restful-api-guidelines/#116)
      * see [Semantic Versioning](https://semver.org/) 
    * [MUST **provide API immutable identifier**](https://opensource.zalando.com/restful-api-guidelines/#215)
  * Security: [MUST secure endpoints](https://opensource.zalando.com/restful-api-guidelines/#104) with [JWT](https://jwt.io/) tokens
  * Compatibility and Deprecation
    * [MUST NOT break **backward compatibility**](https://opensource.zalando.com/restful-api-guidelines/#106)
    * [MUST always return **JSON objects as top-level data structures**](https://opensource.zalando.com/restful-api-guidelines/#110)
    * MUST use **major URI Versioning** to provide [explorability](https://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api#versioning)
    * [MUST reflect **deprecation** in API specifications](https://opensource.zalando.com/restful-api-guidelines/#187)
    * [SHOULD add **Deprecation and Sunset** header to responses](https://opensource.zalando.com/restful-api-guidelines/#189)
  * JSON guidelines and Data formats
    * MUST use **snake_case** for [property](https://opensource.zalando.com/restful-api-guidelines/#118)
      and [query parameters](https://opensource.zalando.com/restful-api-guidelines/#130)
    * [MUST declare **enum** values using **UPPER_SNAKE_CASE** format](https://opensource.zalando.com/restful-api-guidelines/#118)
    * [MUST **pluralize array names**](https://opensource.zalando.com/restful-api-guidelines/#120)
    * [MUST use **common field names** and semantics](https://opensource.zalando.com/restful-api-guidelines/#174)
    * [MUST use **standard data formats**](https://opensource.zalando.com/restful-api-guidelines/#238)
    * MUST use **string** to represent a **floating point numbers**
    * [MUST define **format for integer** types](https://opensource.zalando.com/restful-api-guidelines/#171)
    * SHOULD define **minimum** and a **maximum** for **integer**
    * SHOULD define **minLength** and **maxLength** for **string**
    * SHOULD define **minItems** and **maxItems** for **array**
    * [MUST name date/time properties with **_at suffix**](https://opensource.zalando.com/restful-api-guidelines/#235)
  * API naming
    * [MUST use **kebab-case** for path segments](https://opensource.zalando.com/restful-api-guidelines/#129)
    * [MUST use **Kebab-Case** with uppercase separate words for HTTP header](https://opensource.zalando.com/restful-api-guidelines/#132)
    * [MUST **pluralize** resource names](https://opensource.zalando.com/restful-api-guidelines/#134)
    * [MUST stick to **conventional query parameters**](https://opensource.zalando.com/restful-api-guidelines/#137)
  * Resources
    * [MUST **avoid actions** - think about resources](https://opensource.zalando.com/restful-api-guidelines/#138)
    * [SHOULD keep URLs **verb-free**](https://opensource.zalando.com/restful-api-guidelines/#141)
    * [MUST identify resources and sub-resources via **path segments**](https://opensource.zalando.com/restful-api-guidelines/#143)
    * [MUST limit number of sub-resource levels](https://opensource.zalando.com/restful-api-guidelines/#147)
      (e.g. collection/item/collection)
    * [MAY consider using **(non-)nested URLs**](https://opensource.zalando.com/restful-api-guidelines/#145)
    * ... but MUST NOT expose a large number of small resources to avoid **chatty API**
    * SHOULD use [**ULID**](https://github.com/ulid/javascript) instead of [UUID](https://en.wikipedia.org/wiki/Universally_unique_identifier);
      see [Zalando](https://opensource.zalando.com/restful-api-guidelines/#144)
    * MUST use UUID or ULID instead of integer as **resource id**
  * HTTP requests
    * [MUST use **HTTP methods** correctly](https://opensource.zalando.com/restful-api-guidelines/#148)
    * [MUST fulfill **safe, idempotent, cacheable** properties of HTTP methods](https://opensource.zalando.com/restful-api-guidelines/#149)
    * [SHOULD design **idempotent POST**](https://opensource.zalando.com/restful-api-guidelines/#229);
      see [Idempotency-Key](https://opensource.zalando.com/restful-api-guidelines/#230)
  * HTTP headers
    * SHOULD use only following **standard headers**
      * '[Accept](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept):
        application/json' (in request)
      * '[Accept-Charset](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Charset):
        utf-8' (in request)
      * '[Content-Language](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Language)'
        (in request/response)
    * '[Content-Type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type):
      application/json; charset=utf-8' (in response)
    * [MAY consider to support **Idempotency-Key** header](https://opensource.zalando.com/restful-api-guidelines/#230)
    * [MUST support **X-Flow-ID** header](https://opensource.zalando.com/restful-api-guidelines/#233)
  * HTTP responses
    * [SHOULD only use most common HTTP status codes](https://opensource.zalando.com/restful-api-guidelines/#150)
      * success
        * [200 *OK*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/200),
          [201 *Created*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/201),
          [204 *No Content*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/204)
          * add [Location](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/201#examples) HTTP Header to [201 *Created*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/201)
        * [202 *Accepted*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/202) for [**long processing action**](https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design#asynchronous-operations)
      * client side errors: [400 *Bad Request*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/400),
        * [401 *Unauthorized*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/401),
          [403 *Forbidden*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/403),
          [404 *Not Found*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/404),
          [405 *Method Not Allowed*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/405),
          [406 *Not Acceptable*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/406),
          [415 *Unsupported Media Type*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/415),
          [422 *Unprocessable Entity*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/422)
        * [429 *Too Many Requests*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/429)
          for [**rate limits**](https://opensource.zalando.com/restful-api-guidelines/#153);
          see this [blog](https://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api#rate-limiting)
      * server side errors: [500 *Internal Server Error*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/500), [503 *Service Unavailable*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/503)
    * [SHOULD support problem JSON for errors](https://opensource.zalando.com/restful-api-guidelines/#176);
      see [schema.yaml of Problem](https://opensource.zalando.com/problem/schema.yaml)
    * [MUST not expose **stack traces**](https://opensource.zalando.com/restful-api-guidelines/#177)
    * [MUST **returns the created/updated resource in response** for PUT/POST/PATCH](https://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api#useful-post-responses)
  * Performance and Pagination
    * [MUST use **gzip** compression](https://opensource.zalando.com/restful-api-guidelines/#156)
      with [Content-Encoding: gzip](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Encoding);
      see [blog](https://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api#pretty-print-gzip)
    * [MUST **pretty print**](https://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api#pretty-print-gzip)
    * [SHOULD NOT use **HTTP caching**](https://opensource.zalando.com/restful-api-guidelines/#227) due to complexity & inefficient
      * disable caching by sending response HTTP header
        **[Cache-Control: no-store](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control)**
    * [SHOULD prefer **cursor-based pagination**, avoid offset-based pagination](https://opensource.zalando.com/restful-api-guidelines/#160)
  * Hypermedia
    * [MUST use **REST maturity level 2**](https://opensource.zalando.com/restful-api-guidelines/#162) : HTTP resources responding to HTTP verbs (GET, POST, etc.)
    * and therefore MUST NOT use **[HATEOAS](https://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api#hateoas)**
    * MUST be **Stateless** API
* Tools
  * [Spectral](https://stoplight.io/open-source/spectral): an open-source API style guide enforcer and linter
  * [HTTP Client Tool in IntelliJ](https://www.jetbrains.com/help/idea/http-client-in-product-code-editor.html) as alternative to [curl](https://curl.se/)
  * list of [OpenAPI tools](https://openapi.tools/)
  * [json-server](https://github.com/typicode/json-server): fake REST API
  * [problem](https://github.com/zalando/problem): 
    A Java library that implements application/problem+json
  * [swagger-editor](https://swagger.io/tools/swagger-editor/): 
    editor of OpenAPI APIs  
  * [httpbin](https://httpbin.org/#) a simple HTTP Request & Response Service that test typical Http Request (e.g. downloading image)
  * [Star Wars API](https://pipedream.com/apps/swapi) to do some quick testing
  * code generators
    * [OpenAPI Generator](https://github.com/openapitools/openapi-generator); see [openapi-generator-maven-plugin](https://github.com/OpenAPITools/openapi-generator/blob/master/modules/openapi-generator-maven-plugin/README.md) and [Migration from swagger-codegen](https://github.com/OpenAPITools/openapi-generator/blob/master/docs/migration-from-swagger-codegen.md)
    * alternatives: [swagger codegen](https://github.com/swagger-api/swagger-codegen),
  [zalando swagger codegen](https://github.com/zalando-stups/swagger-codegen-tooling)
  * documentation generators
    * [Swagger UI](https://swagger.io/tools/swagger-ui/) documentation can be generated with [springdoc-openapi](https://springdoc.org/)
    * alternatives: [redoc](https://github.com/Redocly/redoc), [dapperdox](http://dapperdox.io/),
  [widdershins](https://github.com/mermade/widdershins)
* OpenAPI vs JSON Schema vs OData
  * [JSON Schema](http://json-schema.org/) describes JSON documents
  * JSON Schema focuses on data modeling and is more flexible as OpenAPI and could be
    used to implement [HATEOAS](https://en.wikipedia.org/wiki/HATEOAS)
  * [Open API](https://www.openapis.org/) describes APIs
    * OpenAPI provide more tooling as JSON Schema
    * OpenAPI has a lot of rules to follow but ease homegeanous APIs
    * Open API is based on an extended version of the JSON Schema
    * Swagger is an implementation of the OpenAPI standard
  * [OData](https://www.odata.org/) is a protocol for sharing data
* Documentations
  * REST API
    * [Zalando API Guidelines](https://opensource.zalando.com/restful-api-guidelines/)
    * [Microsoft Web API design](https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design)
    * [The Web API Checklist](https://mathieu.fenniak.net/the-api-checklist/)
    * [Best Practices for Designing a Pragmatic RESTful API](https://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api)
    * [REST API Error Handling - Problem Details Response](https://blog.restcase.com/rest-api-error-handling-problem-details-response/)
    * [API Design Guidelines from Paypal](https://github.com/levid-gc/paypal-api-standards/blob/master/api-style-guide.md)
    * [Federal Administration API Guidelines](https://github.com/swiss/api-guidelines)
  * OpenAPI
    * [OpenAPI Specification](https://github.com/OAI/OpenAPI-Specification/)
    * [OpenAPI Mindmap](https://openapi-map.apihandyman.io/)
    * [A Guide to What’s New in OpenAPI 3.0](https://swagger.io/blog/news/whats-new-in-openapi-3-0/)
    * [Swagger Editor](https://editor.swagger.io/) has a "Convert to OpenAPI 3" option
    * [swagger-petstore](https://github.com/swagger-api/swagger-petstore) as OpenAPI 3.0 example

[*Go to parent page*](../../README.md)

*(Page mainly written in May 2020; links checked on 19.02.2024)*
