# GraphQL

[GraphQL](https://graphql.org/) 
is a query language for APIs as alternative to SOAP and REST APIs
that prioritizes giving clients exactly the data they request and no more.

* *GraphQL vs REST*: GraphQL is similar to REST but provide more query flexibility by using a rich query language
  to retrieve required data (and no more)
* concepts
  * GraphQL server exposes single endpoint and responds to queries
  * client - server is easier (no new endpoint to manage)
  * [GraphQL schema](https://graphql.org/learn/schema/)
    defines the operations (queries, mutations and subscriptions) supported by the API
    writen in [Schema Definition Language (SDL)](https://www.prisma.io/blog/graphql-sdl-schema-definition-language-6755bcb9ce51)
  * [schema stitching](https://www.prisma.io/blog/graphql-schema-stitching-explained-schema-delegation-4c6caf468405)
    allows to combine and connect multiple GraphQL APIs and merge them into a single one
  * rapid product iterations (e.g. if client data need changes, the backend API does not have to be updated)
  * GraphQL can be used with a database or/and integrates various APIs into a single endpoint
  * subscription used for realtime connection via 
    [Websockets](https://developer.mozilla.org/en-US/docs/Web/API/Websockets_API)
  * [resolvers](https://graphql.org/learn/execution/#root-fields-resolvers) contain server-side logic to implements GraphSQL schema
  * only POST request with request body
* links
  * [What is GraphQL?](https://www.redhat.com/en/topics/api/what-is-graphql)
  * [How To GraphQL](https://www.howtographql.com/)
  * [5 Reasons Why and How to use GraphQL](https://www.prisma.io/blog/top-5-reasons-to-use-graphql-b60cfa683511)
  * [GraphQL Java Kickstart](https://www.graphql-java-kickstart.com/)
  * [Getting started with Spring for GraphQL](https://www.graphql-java.com/tutorials/getting-started-with-spring-boot/)
  * security
    * [GraphQL Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/GraphQL_Cheat_Sheet.html)
    * [Securing Your GraphQL API from Malicious Queries](https://www.apollographql.com/blog/graphql/security/securing-your-graphql-api-from-malicious-queries/)

[*Go to parent page*](README.md)

*(Page mainly written in 01.2023; links checked on 31.01.2024)*
