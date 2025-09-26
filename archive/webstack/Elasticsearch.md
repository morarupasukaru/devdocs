# Elasticsearch

[Elasticsearch](https://github.com/elastic/elasticsearch)
is a search engine based on the [Lucene](https://lucene.apache.org/) library providing RESTful API. 

*Disclaimer: this document cover not all features of ElasticSearch*

* Concepts
  * Elasticsearch is part of **[Elastic Stack](https://www.elastic.co/what-is/elk-stack)**; the stack provide:
    * [Elasticsearch](https://www.elastic.co/elasticsearch/), a scallable search engine
    * [Kibana](https://www.elastic.co/kibana/), a Web UI for searching and visualizing
    * [Logstash](https://www.elastic.co/guide/en/logstash/current/introduction.html) and [Beats](https://www.elastic.co/beats/) to feed data into Elasticsearch
    * X-Pack are free and paid advanced proprietary features like security, alerting, monitoring, reporting, machine learning, graph exploration
  * Elasticsearch is used 
    * ... with RESTful API:
      ```bash
      curl -H 'Content-Type: application/json' -X[GET|POST|PUT|DELETE] <URL> -d '<BODY>`
      ```
    * ... or with high level client API's like [Java API Client](https://www.elastic.co/guide/en/elasticsearch/client/java-api-client/current/index.html)
  * **documents** are the data to search (like db row); they have a unique ID, a type and can be text or JSON data
  * **indices** provide search on documents (like db table); 
    they have [**mapping**](https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping.html) (schema definition) and **inverted indices** to provide full-text search
    * only one type of document can be stored in an index
  * [**inverted index**](https://www.geeksforgeeks.org/inverted-index/): terms of documents are split and inverted index contains occurences of terms in documents to provide full-text searches (inverted index quickly map search terms to documents)
  * **term frequency**: how often a term appear in a document
  * **document frequency**: how often a term appears in all documents
  * **term relevance**: term *frequency / document frequency* measure the relevance of a term in a document (frequent terms like 'the' won't have a high relevance)
  * index is split into **shards** that are self-contained Lucene indices and may be on different node; provide horizontal scaling 
  * primary and replica shards exist to provide resiliency if a node is unavailable
* REST APIs
  * [Search APIs](https://www.elastic.co/guide/en/elasticsearch/reference/current/search.html): see [guide about searching](https://www.elastic.co/guide/en/elasticsearch/reference/current/search-your-data.html)
    * see [Query DSL](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl.html) having queries examples like:
      * [search docs that match text](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-match-query.html) with *match* query - with analyser
      * [search docs by IDs](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-ids-query.html)
      * etc. 
    * by default, search results are sorted by [relevance score](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-filter-context.html#relevance-scores); the higher the _score, the more relevant the document
  * [Index APIs](https://www.elastic.co/guide/en/elasticsearch/reference/current/indices.html) used to manage index, mapping, analyzer, etc.
    * [Mapping](https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping.html) (schema definition)
      * [*Dynamic mapping*](https://www.elastic.co/guide/en/elasticsearch/reference/current/dynamic-field-mapping.html): mapping can be defined from Elasticsearch automatically by adding new document (good for testing purpose)
      * [*Explicit mapping*](https://www.elastic.co/guide/en/elasticsearch/reference/current/explicit-mapping.html) to be sure that data's type is correct
      * common mapping fields
        * field *type*: define the type of the properties; see [supported types](https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping-types.html)
        * field [*index*](https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping-index.html): define wether of a properties is indexed/queryable
        * field [*analyzer*](https://www.elastic.co/guide/en/elasticsearch/reference/current/analyzer.html): define the analyzer used when indexing or searching a text field (e.g. english)
        * see other [mapping parameters](https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping-params.html)
      * see [create an index with an explicit mapping](https://www.elastic.co/guide/en/elasticsearch/reference/current/explicit-mapping.html#create-mapping)
      * mapping exceptions can be ignored with [ignore_malformed](https://www.elastic.co/guide/en/elasticsearch/reference/current/ignore-malformed.html)
        mapping parameter; but it's not good practise to ignore exceptions...
    * [Analyzer](https://www.elastic.co/guide/en/elasticsearch/reference/current/analyzer-anatomy.html)
      * [character filters](https://www.elastic.co/guide/en/elasticsearch/reference/current/analyzer-anatomy.html#analyzer-anatomy-character-filters): e.g. remove HTML encoding, convert & to and.
      * [tokenizer](https://www.elastic.co/guide/en/elasticsearch/reference/current/analyzer-anatomy.html#analyzer-anatomy-tokenizer): e.g. split strings on whitespace, punctuation, non-letters
      * [token filter](https://www.elastic.co/guide/en/elasticsearch/reference/current/analyzer-anatomy.html#analyzer-anatomy-token-filters): e.g. lowercasing, [stemming](https://en.wikipedia.org/wiki/Stemming), synonyms, [stopwords](https://en.wikipedia.org/wiki/Stop_word)
      * [build-in analyzers](https://www.elastic.co/guide/en/elasticsearch/reference/current/analysis-analyzers.html):
        [standard](https://www.elastic.co/guide/en/elasticsearch/reference/current/analysis-standard-analyzer.html) (if language is unknown),
        [simple](https://www.elastic.co/guide/en/elasticsearch/reference/current/analysis-simple-analyzer.html),
        [whitespace](https://www.elastic.co/guide/en/elasticsearch/reference/current/analysis-whitespace-analyzer.html),
        [language](https://www.elastic.co/guide/en/elasticsearch/reference/current/analysis-lang-analyzer.html), etc.
      * field of type [keyword](https://www.elastic.co/guide/en/elasticsearch/reference/current/keyword.html) will be exact-match (no analyser performed)
  * [Document APIs](https://www.elastic.co/guide/en/elasticsearch/reference/current/docs.html) used for CRUD operations (see also [Quick Start](https://www.elastic.co/guide/en/elasticsearch/reference/current/getting-started.html#add-single-document) guide)
    * [create/update document](https://www.elastic.co/guide/en/elasticsearch/reference/current/docs-index_.html) with index API
    * [partial update document](https://www.elastic.co/guide/en/elasticsearch/reference/current/docs-update.html#_update_part_of_a_document)
    * [optimistic concurrency control](https://www.elastic.co/guide/en/elasticsearch/reference/current/optimistic-concurrency-control.html) provide optimistic locking on update
  * miscelleanous
    * *ping request*: `curl -XGET 127.0.0.1:9200` must return 'You Know, for Search'
* Data modeling aspects
  * [parent / child relationship](https://www.elastic.co/guide/en/elasticsearch/reference/current/parent-join.html) exists in elasticsearch if needed
  * by default, each subfield in an object is mapped and indexed separately. If the names or types of the subfields 
    are not known in advance, then they are mapped dynamically
  * [flattened field type](https://www.elastic.co/guide/en/elasticsearch/reference/current/flattened.html)
    map/index the entire object (subfields) as a single field
    * flattened field type is useful with a large or unknown number of fields to prevent [mappings explosion](https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping.html#mapping-limit-settings)
      or cluster down (too many synchronization of mappings between cluster's nodes)
    * flattened field type add search limitations as subfields are indexed as keyword (no analyzer)
* Searching
  * *query-line*: specify search in URL without JSON body; can be usefull for expirement
    * see [q request parameter of search APIs](https://www.elastic.co/guide/en/elasticsearch/reference/current/search-search.html#search-api-query-params-q)
      and [query string syntax](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-query-string-query.html#query-string-syntax)
    * e.g. `http://localhost:9200/myindex/_search?q=myfield:TEST&pretty`
    * not to use on production due to security issues & limitations
  * normal search query are done with GET request with [JSON body](https://www.elastic.co/guide/en/elasticsearch/reference/current/search-search.html#search-search-api-request-body)
  * [query and filter context](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-filter-context.html#query-filter-context)
    * [filter context](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-filter-context.html#filter-context) to filter data
    * [query context](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-filter-context.html#query-context)
      return data in terms of relevance
    * see example of mix-in of [filter & query context](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-filter-context.html#query-filter-context-ex)
  * common filters:
    * [term](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-term-query.html)
      filter by exact values
    * [terms](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-terms-query.html)
      match if any exact values in a list match
    * [range](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-range-query.html)
      find numbers or dates in a given range
    * [exists](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-exists-query.html)
      find documents where a field exists
    * [fuzzy query](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-fuzzy-query.html)
      returns documents that contain terms similar to the search term (e.g. typos)
    * [prefix](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-prefix-query.html)
      returns documents that contain a specific prefix in a provided field
    * [wildcard](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-wildcard-query.html)
      returns documents that contain terms matching a wildcard pattern
    * [regexp](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-regexp-query.html)
      returns documents that contain terms matching a regular expression
  * common queries:
    * [match](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-match-query.html)
      returns documents that match value (with analyze); standard query for full-text search
    * [multi_match](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-multi-match-query.html)
      run same match query on several fields
    * [match_phrase](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-match-query-phrase.html)
      must find all terms, in the right order
      * slop parameter can be used to specify how strict the query has to be; 
        "Maximum number of positions allowed between matching tokens (defaults: 0)"
    * [match_phrase_prefix](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-match-query-phrase-prefix.html)    
      must find all terms, in the right order. The last term of the provided text is treated as a prefix, 
      matching any words that begin with that term
      * see [explanation](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-match-query-phrase-prefix.html#match-phrase-prefix-autocomplete)
        why is match_phrase_prefix for autocompletion not always good for
  * common compound queries: 
    * [boolean query](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-bool-query.html): combine filters and queries with boolean logic
  * [pagination](https://www.elastic.co/guide/en/elasticsearch/reference/current/paginate-search-results.html)
    with from / size
  * [sorting](https://www.elastic.co/guide/en/elasticsearch/reference/current/sort-search-results.html)  
    * sort does not work on analyzed string field; 
      in that case, additional field with raw value as keyword is required;
      see [multi fields](https://www.elastic.co/guide/en/elasticsearch/reference/current/multi-fields.html)
  * autocomplete can be implemented by setting custom [search analyzer](https://www.elastic.co/guide/en/elasticsearch/reference/current/search-analyzer.html);
    see also [Index-Time Search-as-You-Type](https://www.elastic.co/guide/en/elasticsearch/guide/2.x/_index_time_search_as_you_type.html)
  * [search_as_you_type](https://www.elastic.co/guide/en/elasticsearch/reference/current/search-as-you-type.html)
    field type provide out-of-the-box autocomplete feature
* Importing data
  * ... with [bulk REST API](https://www.elastic.co/guide/en/elasticsearch/reference/current/docs-bulk.html)
  * ... with client libraries like [Java API Client](https://www.elastic.co/guide/en/elasticsearch/client/java-api-client/current/index.html)
  * ... with [Logstash](https://www.elastic.co/guide/en/logstash/current/introduction.html) and [Beats](https://www.elastic.co/beats/) to import data 
      from many sources (logs, db, etc.) to many destination (elasticsearch, csv, new relic, etc.)
    * Logstash is a tool to collect, process (e.g. anonymize), and forward events and log messages
  * ... with elasticsearch add-ons to AWS, Kafka, spark, etc.
* SQL: Elasticsearch and OpenSearch are providing SQL API
  * see [OpenSearch SQL](https://opensearch.org/docs/search-plugins/sql/index/)
  * and [SQL X-Pack](https://www.elastic.co/guide/en/elasticsearch/reference/current/xpack-sql.html) for Elasticsearch
* Links
  * [Elasticsearch Guide](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html)
  * course [Elasticsearch 8 and the Elastic Stack: In Depth and Hands On](https://www.udemy.com/course/elasticsearch-7-and-elastic-stack/)
  * [OpenSearch](https://www.opensearch.org) is a fork of version 7.10.2 of the Elasticsearch because new releases of Elasticsearch are under private license with limitations
  * [elasticsearch-head](http://mobz.github.io/elasticsearch-head/): web front end for Elasticsearch
  * [download Elasticsearch](https://www.elastic.co/downloads/elasticsearch) and install it as Windows service

[*Go to parent page*](README.md)

*(Page mainly written in july 2021; links checked on 31.01.2024)*
