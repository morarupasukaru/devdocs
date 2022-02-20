# REST API Guidelines

Selection of [Zalando](https://opensource.zalando.com/restful-api-guidelines/#) and
[Paypal](https://github.com/paypal/api-standards/blob/master/api-style-guide.md) REST API guidelines

* [Guidelines](#Guidelines)
  * [General](#General)
  * [Meta-Information](#Meta-Information)
  * [Security](#Security)
  * [Compatibility and Deprecation](#Compatibility-and-Deprecation)
  * [JSON guidelines and Data formats](#JSON-guidelines-and-Data-formats)
  * [API naming](#API-naming)
  * [Resources](#Resources)
  * [HTTP requests](#HTTP-requests)
  * [HTTP status codes and errors](#HTTP-status-codes-and-errors)
  * [Performance and Pagination](#Performance-and-Pagination)
  * [Hypermedia](#Hypermedia)
  * [HTTP headers](#HTTP-headers)
* [OpenAPI vs JSON Schema vs OData](#OpenAPI-vs-JSON-Schema-vs-OData)
* Tools
  * list of [OpenAPI tools](https://openapi.tools/)
  * [json-server](https://github.com/typicode/json-server):     fake REST API
  * [problem](https://github.com/zalando/problem): 
    A Java library that implements application/problem+json
  * [swagger-editor](https://swagger.io/tools/swagger-editor/): 
    editor of OpenAPI APIs  
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
    * OpenAPI has lot of rules to follow but ease homegeanous APIs
    * Open API is based on an extended version of the JSON Schema
    * Swagger is an implementation of the OpenAPI standard
  * [OData](https://www.odata.org/) is a protocol for sharing data
* Documentations
  * REST API
    * [Zalando API Guidelines](https://opensource.zalando.com/restful-api-guidelines/)
    * [Paypal API Guidelines](https://github.com/paypal/api-standards/blob/master/api-style-guide.md#api-design-guidelines)
    and [Design Patterns](https://github.com/paypal/api-standards/blob/master/patterns.md)
    * [Microsoft Web API design](https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design)
    * [The Web API Checklist](https://mathieu.fenniak.net/the-api-checklist/)
    * [Best Practices for Designing a Pragmatic RESTful API](https://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api)
    * [REST API Error Handling - Problem Details Response](https://blog.restcase.com/rest-api-error-handling-problem-details-response/)
  * OpenAPI
    * [OpenAPI Specification](https://github.com/OAI/OpenAPI-Specification/)
    * [OpenAPI Mindmap](https://openapi-map.apihandyman.io/)
    * [A Guide to What’s New in OpenAPI 3.0](https://swagger.io/blog/news/whats-new-in-openapi-3-0/)
    * [Swagger Editor](https://editor.swagger.io/) has a "Convert to OpenAPI 3" option
    * [swagger-petstore](https://github.com/swagger-api/swagger-petstore) as OpenAPI 3.0 example

*(Page mainly written in May 2020; links checked on 20.02.2022)*

[*Go to parent page*](../README.md)


* Guidelines
  * General
    * [MUST provide API specification using **OpenAPI**](https://opensource.zalando.com/restful-api-guidelines/#101)
    * SHOULD write **self-contained** API specification without references
    * [MUST write APIs using **U.S. English**](https://opensource.zalando.com/restful-api-guidelines/#103)
    * [SHOULD monitor **API usage**](https://opensource.zalando.com/restful-api-guidelines/#193)
  * Meta-Information
    * [MUST contain API **meta information**](https://opensource.zalando.com/restful-api-guidelines/#218)
    * [MUST use **semantic versioning**](https://opensource.zalando.com/restful-api-guidelines/#116)
    * [MUST **provide API immutable identifier**](https://opensource.zalando.com/restful-api-guidelines/#215)
  * Security
    * [MUST secure endpoints with **JWT Token**](https://opensource.zalando.com/restful-api-guidelines/#104) (see [jwt.io](https://jwt.io/))
    * [MUST define and assign **permissions**](https://opensource.zalando.com/restful-api-guidelines/#105)
  * Compatibility and Deprecation
    * [MUST NOT break **backward compatibility**](https://opensource.zalando.com/restful-api-guidelines/#106)
    * [MUST always return **JSON objects as top-level data structures**](https://opensource.zalando.com/restful-api-guidelines/#110)
    * MUST use **major URI Versioning** to provide [explorability](https://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api#versioning)
    * [MUST reflect **deprecation** in API specifications](https://opensource.zalando.com/restful-api-guidelines/#187)
    * [SHOULD add **Deprecation and Sunset** header to responses](https://opensource.zalando.com/restful-api-guidelines/#189)

TODO

### JSON guidelines and Data formats
* MUST use **snake_case** for [property names](https://opensource.zalando.com/restful-api-guidelines/#118) 
  and [query parameters](https://opensource.zalando.com/restful-api-guidelines/#130)
* [MUST declare **enum** values using **UPPER_SNAKE_CASE** format](https://opensource.zalando.com/restful-api-guidelines/#118)
* [MUST define maps using **additionalProperties**](https://opensource.zalando.com/restful-api-guidelines/#216)
* [MUST **pluralize array names**](https://opensource.zalando.com/restful-api-guidelines/#120)
* [MUST NOT use **null**](https://github.com/paypal/api-standards/blob/master/api-style-guide.md#null)
* [MUST name date/time properties with **_at suffix**](https://opensource.zalando.com/restful-api-guidelines/#235)
* MUST use [**date** common types](https://github.com/paypal/api-standards/blob/master/api-style-guide.md#date-common-types); 
  see [Zalando](https://opensource.zalando.com/restful-api-guidelines/#169)
* MUST use [**time_duration**.json](https://github.com/paypal/api-standards/blob/master/v1/schema/json/draft-04/time_duration.json); 
  see [Zalando](https://opensource.zalando.com/restful-api-guidelines/#127)
* [MUST use **standardized property formats**](https://opensource.zalando.com/restful-api-guidelines/#238)
* [MUST define **format for integer** types](https://opensource.zalando.com/restful-api-guidelines/#171)
* [MUST define **minLength** and **maxLength** for **string**](https://github.com/paypal/api-standards/blob/master/api-style-guide.md#string)
* [MUST NOT use **number**](https://github.com/paypal/api-standards/blob/master/api-style-guide.md#number)
* MUST use **string** use string to represent a **decimal value**
* [MUST define **minimum** and a **maximum** for **integer**](https://github.com/paypal/api-standards/blob/master/api-style-guide.md#number)
* [MUST define **minItems** and **maxItems** (default choice 32767) for **array**](https://github.com/paypal/api-standards/blob/master/api-style-guide.md#array)
* MUST use [**country_code**.json](https://github.com/paypal/api-standards/blob/master/v1/schema/json/draft-04/country_code.json), 
  [**language**.json](https://github.com/paypal/api-standards/blob/master/v1/schema/json/draft-04/language.json), 
  [**currency_code**.json](https://github.com/paypal/api-standards/blob/master/v1/schema/json/draft-04/currency_code.json); 
  see [Zalando](https://opensource.zalando.com/restful-api-guidelines/#170)
* MUST use [**money**.json](https://github.com/paypal/api-standards/blob/master/v1/schema/json/draft-04/money.json) 
  (see also [Zalando](https://opensource.zalando.com/restful-api-guidelines/#173), 
  [jackson-datatype-money](https://github.com/zalando/jackson-datatype-money), 
  [JavaMoney](https://github.com/JavaMoney/jsr354-api))
* MUST use other **[common types](https://github.com/paypal/api-standards/blob/master/api-style-guide.md#common-types)** 
  like [percentage.json](https://github.com/paypal/api-standards/blob/master/v1/schema/json/draft-04/percentage.json), 
  [locale.json](https://github.com/paypal/api-standards/blob/master/v1/schema/json/draft-04/locale.json), etc.
* [MUST use **common field names** and semantics](https://opensource.zalando.com/restful-api-guidelines/#174)

[*Go to top*](#REST-API-Guidelines)


### API naming
* [MUST use **lowercase separate words with hyphens** for path segments](https://opensource.zalando.com/restful-api-guidelines/#129)
* [MUST use **Hyphenated-Pascal-Case** for HTTP header fields](https://opensource.zalando.com/restful-api-guidelines/#132)
* [MUST **pluralize** resource names](https://opensource.zalando.com/restful-api-guidelines/#134)
* [MUST NOT use **/api** as base path](https://opensource.zalando.com/restful-api-guidelines/#135)
* [MUST avoid **trailing slashes**](https://opensource.zalando.com/restful-api-guidelines/#136)
* [MUST stick to **conventional query parameters**](https://opensource.zalando.com/restful-api-guidelines/#137)

[*Go to top*](#REST-API-Guidelines)


### Resources
* [MUST **avoid actions** - think about resources](https://opensource.zalando.com/restful-api-guidelines/#138)
* SHOULD use **[controller resources](https://github.com/paypal/api-standards/blob/master/patterns.md#controller-resources)** 
  if a resource cannot be designed
* [MUST keep URLs **verb-free**](https://opensource.zalando.com/restful-api-guidelines/#141)
* [MUST identify resources and sub-resources via **path segments**](https://opensource.zalando.com/restful-api-guidelines/#143)
* [MAY consider using **(non-)nested URLs**](https://opensource.zalando.com/restful-api-guidelines/#145)
* SHOULD use [**ULID**](https://github.com/ulid/javascript) instead of [UUID](https://en.wikipedia.org/wiki/Universally_unique_identifier); 
  see [Zalando](https://opensource.zalando.com/restful-api-guidelines/#144)
* MUST have non-numeric non-sequential value as **resource id** (e.g. ULID)
* MUST NOT have **resource URIs** more complex than collection/item/collection, 
  [Zalando](https://opensource.zalando.com/restful-api-guidelines/#147)
* MUST NOT expose a large number of small resources to avoid **chatty API**

[*Go to top*](#REST-API-Guidelines)


### HTTP requests
* [MUST use **HTTP methods** correctly](https://opensource.zalando.com/restful-api-guidelines/#148); 
  see [paypal](https://github.com/paypal/api-standards/blob/master/api-style-guide.md#http-methods-headers-and-statuses) 
* [MUST follow expected **safe, idempotent, cacheable** support of HTTP methods](https://opensource.zalando.com/restful-api-guidelines/#149)
* SHOULD have [**idempotent POST**](https://github.com/paypal/api-standards/blob/master/patterns.md#idempotency-for-post-requests) 
  operations; see [Zalando](https://opensource.zalando.com/restful-api-guidelines/#229), [Idempotency-Key](https://opensource.zalando.com/restful-api-guidelines/#230)
* [MUST **repeat query parameter for collections**](https://github.com/paypal/api-standards/blob/master/api-style-guide.md#passing-multiple-values-for-the-same-query-parameter), 
  see [Zalando](https://opensource.zalando.com/restful-api-guidelines/#154)

[*Go to top*](#REST-API-Guidelines)


### HTTP status codes and errors
* MUST use following **[HTTP Status Codes](https://github.com/paypal/api-standards/blob/master/api-style-guide.md#allowed-status-codes-list)**
    * for API dev: 
      [200 *OK*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/200), 
      [201 *Created*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/201), 
      [202 *Accepted*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/202), 
      [204 *No Content*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/204), 
      [400 *Bad Request*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/400), 
      [403 *Forbidden*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/403), 
      [404 *Not Found*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/404), 
      [422 *Unprocessable Entity*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/422), 
      [500 *Internal Server Error*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/500)
    * for frameworks: [401 *Unauthorized*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/401), 
      [405 *Method Not Allowed*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/405), 
      [406 *Not Acceptable*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/406), 
      [415 *Unsupported Media Type*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/415), 
      [429 *Too Many Requests*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/429), 
      [503 *Service Unavailable*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/503)
    * see also [HTTP Method to Status Code Mapping](https://github.com/paypal/api-standards/blob/master/api-style-guide.md#http-method-to-status-code-mapping), 
      [Zalando](https://opensource.zalando.com/restful-api-guidelines/#150)
* [MUST use code 207 *Multi-Status* for **batch or bulk requests**](https://opensource.zalando.com/restful-api-guidelines/#152), 
  see [paypal](https://github.com/paypal/api-standards/blob/master/patterns.md#bulk-operations)
* MUST use code [429 *Too Many Requests*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/429) 
  with headers for [**rate limits**](https://opensource.zalando.com/restful-api-guidelines/#153); 
  see this [blog](https://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api#rate-limiting)
* MUST use **[application/problem+json](https://opensource.zalando.com/restful-api-guidelines/#176)** for **errors**; 
  see [Problem](https://opensource.zalando.com/problem/schema.yaml).yaml
* [MUST not expose **stack traces**](https://opensource.zalando.com/restful-api-guidelines/#177)
* [MUST **returns the created/updated resource in response** for PUT/POST/PATCH](https://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api#useful-post-responses)
* SHOULD use **asynchronous operations** for long processing action by returning HTTP status code 
  [202 *Accepted*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/202); 
  see patterns of [microsoft](https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design#asynchronous-operations) 
  or [paypal](https://github.com/paypal/api-standards/blob/master/patterns.md#asynchronous-operations)

[*Go to top*](#REST-API-Guidelines)


### Performance and Pagination
* [MUST use **gzip** compression](https://opensource.zalando.com/restful-api-guidelines/#156) 
  with [Content-Encoding: gzip](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Encoding); 
  see [blog](https://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api#pretty-print-gzip)
* [MUST **pretty print**](https://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api#pretty-print-gzip)
* SHOULD NOT use **HTTP caching** because of the complexity; 
  see [Zalando](https://opensource.zalando.com/restful-api-guidelines/#227)
* MUST disable caching by sending response HTTP header 
  **[Cache-Control: no-store](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control)**
* [MUST support **pagination**](https://opensource.zalando.com/restful-api-guidelines/#159), 
  see [paypal Sorting](https://github.com/paypal/api-standards/blob/master/patterns.md#sorting), 
  [Pagination](https://github.com/paypal/api-standards/blob/master/patterns.md#pagination), 
  [Microsoft](https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design#filter-and-paginate-data) 
  and this [Blog](https://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api#advanced-queries)
* [MUST support **cursor-based pagination**, avoid offset-based pagination](https://opensource.zalando.com/restful-api-guidelines/#160)

[*Go to top*](#REST-API-Guidelines)


### Hypermedia
* [MUST use **REST maturity level 2**](https://opensource.zalando.com/restful-api-guidelines/#162)
* [MUST use full, **absolute URI**](https://opensource.zalando.com/restful-api-guidelines/#217)
* MUST NOT use **[HATEOAS](https://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api#hateoas)**
* MUST be **Stateless** API

[*Go to top*](#REST-API-Guidelines)


### HTTP headers
* SHOULD use only following **[standard headers](https://github.com/paypal/api-standards/blob/master/api-style-guide.md#http-standard-headers)**
  * SHOULD send header '[Accept](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept): 
    application/json', '[Accept-Charset](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Charset): 
    utf-8', '[Content-Language](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Language)' 
    in the request by client
  * MUST send '[Content-Language](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Language)', 
    '[Content-Type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type): 
    application/json; charset=utf-8' in the response by the server
  * see [Zalando](https://opensource.zalando.com/restful-api-guidelines/#230)
* [MUST support **X-Flow-ID**](https://opensource.zalando.com/restful-api-guidelines/#233)

[*Go to top*](#REST-API-Guidelines)
