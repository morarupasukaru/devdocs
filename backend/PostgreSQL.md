# PostgreSQL

[PostgreSQL](https://www.postgresql.org/) is a powerful, open source object-relational database.

[PostgreSQL Documentation](https://www.postgresql.org/docs/current/index.html)
* [Tutorial](https://www.postgresql.org/docs/current/tutorial.html)
* [SQL Language](https://www.postgresql.org/docs/current/sql.html)
  * [data definition (ddl)](https://www.postgresql.org/docs/current/ddl.html)
    * [constraints](https://www.postgresql.org/docs/current/ddl-constraints.html)
      * [PRIMARY KEY](https://www.postgresql.org/docs/current/ddl-constraints.html#DDL-CONSTRAINTS-PRIMARY-KEYS)
      * foreign keys with [REFERENCES](https://www.postgresql.org/docs/current/ddl-constraints.html#DDL-CONSTRAINTS-FK) and `ON DELETE` *referential_action* (see [CREATE TABLE](https://www.postgresql.org/docs/current/sql-createtable.html))
      * [CHECK](https://www.postgresql.org/docs/current/ddl-constraints.html#DDL-CONSTRAINTS-CHECK-CONSTRAINTS)
      * [NOT NULL](https://www.postgresql.org/docs/current/ddl-constraints.html#id-1.5.4.6.6)
      * [UNIQUE](https://www.postgresql.org/docs/current/ddl-constraints.html#DDL-CONSTRAINTS-UNIQUE-CONSTRAINTS)
  * [queries](https://www.postgresql.org/docs/current/queries.html)    
    * [queries with JOIN](https://www.postgresql.org/docs/current/queries-table-expressions.html#QUERIES-FROM) (inner join, left outer join, right outer join, full join)
    * [grouping with GROUP BY and HAVING](https://www.postgresql.org/docs/current/queries-table-expressions.html#QUERIES-GROUP)
    * [sort with ORDER BY](https://www.postgresql.org/docs/current/queries-order.html)
    * [retrieve a portion of rows with LIMIT and OFFSET](https://www.postgresql.org/docs/current/queries-limit.html)
    * [combining with UNION [ALL], (INTERSECT, EXCEPT)](https://www.postgresql.org/docs/current/queries-union.html)
    * [eliminate dupplicate rows with DISTINCT](https://www.postgresql.org/docs/current/queries-select-lists.html#QUERIES-DISTINCT)
    * [subquery in FROM or JOIN = returns rows](https://www.postgresql.org/docs/current/queries-table-expressions.html#QUERIES-FROM)
      ; must have an alias
    * [subquery in WHERE = returns values](https://www.postgresql.org/docs/current/queries-table-expressions.html#QUERIES-WHERE)
    * [correlated subqueries](https://en.wikipedia.org/wiki/Correlated_subquery) uses values from the outer query 
      * subquery may be evaluated once for each row processed by the outer query, it can be slow
      * correlated subqueries appear in SELECT or WHERE clauses
      * [subquery in SELECT are called scalar subqueries and returns single value](https://www.postgresql.org/docs/current/sql-expressions.html#SQL-SYNTAX-SCALAR-SUBQUERIES)
    * select without FROM clauses used to returns single value of a subquery,
      e.g. `SELECT (SELECT xyz FROM ...)`
    * [select without FROM clauses used as calculator](https://www.postgresql.org/docs/current/queries-overview.html)
      like `SELECT random();`
  * [common table expessions (CTE) / WITH queries](https://www.postgresql.org/docs/current/queries-with.html)
    * `WITH` query always to extract subquery into temporary table that exist just for one query
    * advantages
      * make complex query easier to understand
      * produce a table that we can refer to anywhere else (clauses)
      * allow recursive query 
      * might be more performant: `WITH` query are normally evaluated only once per execution of the parent query, even if they are referred to more than once by the parent query or sibling `WITH` queries
    * [recursive common table expessions](https://www.postgresql.org/docs/current/queries-with.html#QUERIES-WITH-RECURSIVE)
      * recursive CTE are quite different and more complex than normal CTE
      * recursive CTE are usefull to parse a tree or graph
    * see also [SQL CTE Explained](https://learnsql.com/blog/what-is-sql-cte/) and [What Is a Recursive CTE in SQL?](https://learnsql.com/blog/sql-recursive-cte/)  * [data types](https://www.postgresql.org/docs/current/datatype.html)
    * [numbers](https://www.postgresql.org/docs/current/datatype-numeric.html);
      important types are
      * [serial](https://www.postgresql.org/docs/current/datatype-numeric.html#DATATYPE-SERIAL) for autoincrementing ID/PK
      * [INTEGER](https://www.postgresql.org/docs/current/datatype-numeric.html#DATATYPE-INT) for number without decimal
      * [NUMERIC](https://www.postgresql.org/docs/current/datatype-numeric.html#DATATYPE-NUMERIC-DECIMAL) for precise decimal number
      * [DOUBLE PRECISION](https://www.postgresql.org/docs/current/datatype-numeric.html#DATATYPE-FLOAT) for unprecise decimal number
    * [character](https://www.postgresql.org/docs/current/datatype-character.html) like `VARCHAR`, `TEXT` (unlimited)
    * [boolean](https://www.postgresql.org/docs/current/datatype-boolean.html)
    * [date/time](https://www.postgresql.org/docs/current/datatype-datetime.html) 
      like `DATE`, `TIMESTAMP` 
      * and [INTERVAL](https://www.postgresql.org/docs/current/datatype-datetime.html#DATATYPE-INTERVAL-INPUT) (duration of time); very useful to calculate date with [date/time operators](https://www.postgresql.org/docs/current/functions-datetime.html) `+`, `-`, etc.
    * other: 
      [enum](https://www.postgresql.org/docs/current/datatype-enum.html),
      [arrays](https://www.postgresql.org/docs/current/arrays.html),
      [JSON](https://www.postgresql.org/docs/current/datatype-json.html),
      [UUID](https://www.postgresql.org/docs/current/datatype-uuid.html),
      user-defined data types
      [composite](https://www.postgresql.org/docs/current/rowtypes.html) and 
      [domain](https://www.postgresql.org/docs/current/domains.html), ...
  * [type casts](https://www.postgresql.org/docs/current/sql-expressions.html#SQL-SYNTAX-TYPE-CASTS) `::`, e.g. `SELECT 10::BOOLEAN` or `SELECT CAST(10 AS BOOLEAN)` (sql conform)   
  * [functions & operators](https://www.postgresql.org/docs/current/functions.html)
    * [comparison functions and operators](https://www.postgresql.org/docs/current/functions-comparison.html)
      like `BETWEEN`
    * [string functions and operators](https://www.postgresql.org/docs/current/functions-string.html)
      like `||` for concat
    * [mathematical functions and operators](https://www.postgresql.org/docs/current/functions-math.html)
      like 
      * `^` for exponent
      * `@` for absolut value
      * `|/` for square root
    * [aggregate functions](https://www.postgresql.org/docs/current/functions-aggregate.html)
      like max, avg, sum
    * [date/time functions & operators](https://www.postgresql.org/docs/current/functions-datetime.html) like `current_timestamp`, `date_trunc`
    * [conditional expressions](https://www.postgresql.org/docs/current/functions-conditional.html)
      like [GREATEST and LEAST](https://www.postgresql.org/docs/current/functions-conditional.html#FUNCTIONS-GREATEST-LEAST), 
      [CASE](https://www.postgresql.org/docs/current/functions-conditional.html#FUNCTIONS-CASE), 
      [COALESCE](https://www.postgresql.org/docs/current/functions-conditional.html#FUNCTIONS-COALESCE-NVL-IFNULL)
      * tip: `COALESCE(value::BOOLEAN::INTEGER, 0)` to convert value to [0|1] number that can be used in CHECK or aggregate functions
    * [subquery expressions](https://www.postgresql.org/docs/current/functions-subquery.html)
      like [EXISTS](https://www.postgresql.org/docs/current/functions-subquery.html#FUNCTIONS-SUBQUERY-EXISTS),
      [IN](https://www.postgresql.org/docs/current/functions-subquery.html#FUNCTIONS-SUBQUERY-IN),
      [ANY/SOME](https://www.postgresql.org/docs/current/functions-subquery.html#FUNCTIONS-SUBQUERY-ANY-SOME),
      [ALL](https://www.postgresql.org/docs/current/functions-subquery.html#FUNCTIONS-SUBQUERY-ALL),
      [single-row comparison](https://www.postgresql.org/docs/current/functions-subquery.html#id-1.5.8.29.15)
  * [indexes](https://www.postgresql.org/docs/current/indexes.html)
    * [index-types](https://www.postgresql.org/docs/current/indexes-types.html): [B-Tree](https://www.postgresql.org/docs/current/indexes-types.html#INDEXES-TYPES-BTREE) [index type](https://www.postgresql.org/docs/current/indexes-types.html) is 99% used and is for general purpose; see [other index types](https://www.postgresql.org/docs/current/indexes-types.html) if needed
    * see tips in [examining index usage](https://www.postgresql.org/docs/current/indexes-examine.html) on when to create indexes
    * PostgreSQL automatically create an index for primary key and UNIQUE constraint (invisible in pgAdmin)
    * index and foreign key
      * PostgreSQL does not automatically create an index for foreign key
      * see [Should I Create an Index on Foreign Keys in PostgreSQL?](https://www.percona.com/blog/should-i-create-an-index-on-foreign-keys-in-postgresql/)
      * and [ARE YOUR FOREIGN KEYS INDEXED?](https://www.cybertec-postgresql.com/en/index-your-foreign-key/)
      <details>
        <summary>query to find missing index on (click me)</summary>

        ```sql
        SELECT c.conrelid::regclass AS "table",
        /* list of key column names in order */
        string_agg(a.attname, ',' ORDER BY x.n) AS columns,
        pg_catalog.pg_size_pretty(
            pg_catalog.pg_relation_size(c.conrelid)
        ) AS size,
        c.conname AS constraint,
        c.confrelid::regclass AS referenced_table
        FROM pg_catalog.pg_constraint c
          /* enumerated key column numbers per foreign key */
          CROSS JOIN LATERAL
              unnest(c.conkey) WITH ORDINALITY AS x(attnum, n)
          /* name for each key column */
          JOIN pg_catalog.pg_attribute a
              ON a.attnum = x.attnum
                AND a.attrelid = c.conrelid
        WHERE NOT EXISTS
                /* is there a matching index for the constraint? */
                (SELECT 1 FROM pg_catalog.pg_index i
                WHERE i.indrelid = c.conrelid
                  /* it must not be a partial index */
                  AND i.indpred IS NULL
                  /* the first index columns must be the same as the
                      key columns, but order doesn't matter */
                  AND (i.indkey::smallint[])[0:cardinality(c.conkey)-1]
                      OPERATOR(pg_catalog.@>) c.conkey)
          AND c.contype = 'f'
        GROUP BY c.conrelid, c.conname, c.confrelid
        ORDER BY pg_catalog.pg_relation_size(c.conrelid) DESC;
        ```
      </details>
* [views](https://www.postgresql.org/docs/current/tutorial-views.html)
  * views allow to reuse query
  * views allow you to encapsulate the details of the structure of your tables, which might change as your application evolves, behind consistent interfaces
  * view vs materialized view
    * views: query is executed every time
    * materialized views are _caches_; query is executed at specific time to renew the _cache_
    * materialized views are useful for expensive queries
    * disadvantage of materialized views: have to be updated _MANUALLY_ with [REFRESH MATERIALIZED VIEW](https://www.postgresql.org/docs/current/sql-refreshmaterializedview.html)
* transactions
  * PostgreSQL has autocommit by default
  * call [START TRANSACTION](https://www.postgresql.org/docs/current/sql-start-transaction.html) to disable autocommit
* schema/data migration
  * schema migration file: precise change to make to database and its counterpart to revert the change
  * schema/data migration file should be done in separate steps (over a few days/weeks) along with changes in applications (consumers/producers), e.g.
    * step 1: add new column (_schema migration_)
    * step 2: applications write in old/new column
    * step 3: copy values from old to new (_data migration_, might take time)
    * step 4: applications write only in new column
    * step 5: drop old column (_schema migration_)
  * if lot of rows must be updated, update should be done in several transaction 
    to prevent **transaction locks**
    ```sql
    UPDATE ... LIMIT 5000; COMMIT; -- (to repeat)
    ```
  * library for schema migration:
    [flyway](https://flywaydb.org/) or
    [liquibase](https://www.liquibase.com/)
    * see [database migrations with Flyway](https://www.baeldung.com/database-migrations-with-flyway)
    * see [liquibase vs flyway](https://www.liquibase.com/liquibase-vs-flyway)
    * see [liquibase works with Plain Old SQL](https://www.liquibase.com/blog/plain-sql)
  * [schemas](https://www.postgresql.org/docs/current/ddl-schemas.html)
    * a database contains one or more named schemas, which in turn contain tables. Schemas also contain other kinds of named objects, including data types, functions, and operators
    * unlike databases, schemas are not rigidly separated: a user can access objects in any of the schemas in the database they are connected to, if they have privileges to do so
    * [schema search path](https://www.postgresql.org/docs/current/ddl-schemas.html#DDL-SCHEMAS-PATH)
      * schema search path define order of schemas look for if query does not have schema prefix
      * `SHOW search_path;` allow to display current schema search path
      * `SET search_path TO myschema,public;` allow to define schema search path 
* [SQL Commands](https://www.postgresql.org/docs/current/sql-commands.html)
  * CRUD: [SELECT](https://www.postgresql.org/docs/current/sql-select.html),
  [INSERT](https://www.postgresql.org/docs/current/sql-insert.html),
  [UPDATE](https://www.postgresql.org/docs/current/sql-update.html),
  [DELETE](https://www.postgresql.org/docs/current/sql-delete.html),
  * [[CREATE](https://www.postgresql.org/docs/current/sql-createtable.html)|[ALTER](https://www.postgresql.org/docs/current/sql-altertable.html)|[DROP](https://www.postgresql.org/docs/current/sql-droptable.html)]
  TABLE
  * [[CREATE](https://www.postgresql.org/docs/current/sql-createindex.html)|[ALTER](https://www.postgresql.org/docs/current/sql-alterindex.html)|[DROP](https://www.postgresql.org/docs/current/sql-dropindex.html)]
    INDEX
  * [[CREATE](https://www.postgresql.org/docs/current/sql-createview.html)|[ALTER](https://www.postgresql.org/docs/current/sql-alterview.html)|[DROP](https://www.postgresql.org/docs/current/sql-dropview.html)]
    VIEW
    * `CREATE OR REPLACE VIEW`: if a view of the same name already exists, it is replaced (might be better then `ALTER VIEW`)
  * [[CREATE](https://www.postgresql.org/docs/current/sql-creatematerializedview.html)|[ALTER](https://www.postgresql.org/docs/current/sql-altermaterializedview.html)|[DROP](https://www.postgresql.org/docs/current/sql-dropmaterializedview.html)|[REFRESH](https://www.postgresql.org/docs/current/sql-refreshmaterializedview.html)]
     MATERIALIZED VIEW
  * transaction: [START TRANSACTION](https://www.postgresql.org/docs/current/sql-start-transaction.html) (or [BEGIN](https://www.postgresql.org/docs/current/sql-begin.html)), [COMMIT](https://www.postgresql.org/docs/current/sql-commit.html), [ROLLBACK](https://www.postgresql.org/docs/current/sql-rollback.html) 
  * [EXPLAIN](https://www.postgresql.org/docs/current/sql-explain.html) for benchmarking query
    * `EXPLAIN`: info about query plan
    * `EXPLAIN ANALYZE`: info about runned query
      * take care: `EXPLAIN ANALYZE` execute query and could update data!
    * see [Using EXPLAIN](https://www.postgresql.org/docs/current/using-explain.html)
  * [SHOW](https://www.postgresql.org/docs/current/sql-show.html) [search_path](https://www.postgresql.org/docs/current/ddl-schemas.html#DDL-SCHEMAS-PATH);
  * [SET](https://www.postgresql.org/docs/current/sql-set.html) [search_path](https://www.postgresql.org/docs/current/ddl-schemas.html#DDL-SCHEMAS-PATH);
  * ...
* query tuning
  * use [EXPLAIN](https://www.postgresql.org/docs/current/sql-explain.html) to benchmark query
  * see [planner cost constants](https://www.postgresql.org/docs/current/runtime-config-query.html#RUNTIME-CONFIG-QUERY-CONSTANTS) used by query planner
    * cost of a disk page fetch is 1.0 is used as reference
  * explain provide two costs, e.g. `(cost=8.31..1756.11 ...)`
    * left value = _startup_ cost for this step to produce the first row
    * right value = _total_ cost for this step to produce all rows
  * steps of query plan have `(cost=...)`
  * goal is to identify which steps are expensive
  * existing index might be not used if sequential readings is more performant than lot of random accesses  
* [Server Programming](https://www.postgresql.org/docs/current/server-programming.html)
* Other database concepts
  * [ACID (atomicity, consistency, isolation, durability)](https://en.wikipedia.org/wiki/ACID)
  * [type of locks](https://www.geeksforgeeks.org/levels-of-locking-in-dbms/)
  * [isolation levels](https://en.wikipedia.org/wiki/Isolation_%28database_systems%29)
* Links & Tools
  * https://pg-sql.com/: temporary online Postgres Database
  * [Awesome Postgres](https://github.com/dhamaniasad/awesome-postgres) : compilations of links about PostgreSQL
  * db tools
    * [dbeaver](https://dbeaver.io/) : Universal Database Tool
    * [pgAdmin](https://www.pgadmin.org/) : PostgreSQL Database Tool (provided also in [PostgreSQL installer](https://www.postgresql.org/download/))
    * [diagrams.net](https://www.diagrams.net/) : diagrams editor
  * sql schema designers
    * https://ondras.zarovi.cz/sql/demo/ for wiziwig editor
    * [dbdiagram.io](https://dbdiagram.io/home) for code first editor using [DBML](https://www.dbml.org/home/)
  * database version control: [flyway](https://flywaydb.org/), [liquibase](https://www.liquibase.com/)
  * [Prisma](https://www.prisma.io/) is a Node.js and TypeScript ORM

*(Page mainly started in march 2023)*

[*Go to parent page*](../README.md)
