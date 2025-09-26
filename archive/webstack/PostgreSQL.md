# PostgreSQL

[PostgreSQL](https://www.postgresql.org/) is a powerful, open source object-relational database.

* [Tutorial](https://www.postgresql.org/docs/current/tutorial.html)
* [Language](https://www.postgresql.org/docs/current/sql.html)
  * [data definition](https://www.postgresql.org/docs/current/ddl.html)
    * [table](https://www.postgresql.org/docs/current/ddl-basics.html)
    * [DEFAULT](https://www.postgresql.org/docs/current/ddl-default.html) column value
    * [constraints](https://www.postgresql.org/docs/current/ddl-constraints.html)
      * [PRIMARY KEY](https://www.postgresql.org/docs/current/ddl-constraints.html#DDL-CONSTRAINTS-PRIMARY-KEYS)
      * foreign-key with [REFERENCES ... [ON DELETE [NO ACTION |RESTRICT |CASCADE |SET NULL]]](https://www.postgresql.org/docs/current/ddl-constraints.html#DDL-CONSTRAINTS-FK)
      * [CHECK](https://www.postgresql.org/docs/current/ddl-constraints.html#DDL-CONSTRAINTS-CHECK-CONSTRAINTS),
        [NOT NULL](https://www.postgresql.org/docs/current/ddl-constraints.html#DDL-CONSTRAINTS-NOT-NULL),
        [UNIQUE](https://www.postgresql.org/docs/current/ddl-constraints.html#DDL-CONSTRAINTS-UNIQUE-CONSTRAINTS)
    * [schemas](https://www.postgresql.org/docs/current/ddl-schemas.html)
      * a database contains one or more named schemas, which in turn contain tables. Schemas also contain other kinds of named objects, including data types, functions, and operators
      * unlike databases, schemas are not rigidly separated: a user can access objects in any of the schemas in the database they are connected to, if they have privileges to do so
      * [schema search path](https://www.postgresql.org/docs/current/ddl-schemas.html#DDL-SCHEMAS-PATH)
        define order of schemas look for if query does not have schema prefix
  * [insert, update, delete](https://www.postgresql.org/docs/current/dml.html)  
  * [queries](https://www.postgresql.org/docs/current/queries.html)
    * [JOIN _tables_](https://www.postgresql.org/docs/current/queries-table-expressions.html#QUERIES-FROM) : inner join, left outer join, right outer join, full join
    * [GROUP BY and HAVING _for grouping_](https://www.postgresql.org/docs/current/queries-table-expressions.html#QUERIES-GROUP)
    * [ORDER BY _to sort_](https://www.postgresql.org/docs/current/queries-order.html)
    * [LIMIT and OFFSET _to retrieve a portion of rows_](https://www.postgresql.org/docs/current/queries-limit.html)
    * [UNION [ALL], (INTERSECT, EXCEPT) _to combine rows_](https://www.postgresql.org/docs/current/queries-union.html)
    * [DISTINCT _to eliminate dupplicate_](https://www.postgresql.org/docs/current/queries-select-lists.html#QUERIES-DISTINCT)
    * subqueries
      * [... in FROM/JOIN](https://www.postgresql.org/docs/current/queries-table-expressions.html#QUERIES-FROM) returns rows and MUST have an alias
      * [... in WHERE](https://www.postgresql.org/docs/current/queries-table-expressions.html#QUERIES-WHERE) returns values
      * ... without FROM clauses 
        * ... returns single value of a subquery; e.g. `SELECT (SELECT xyz FROM ...)`
        * ... or are used as [calculator](https://www.postgresql.org/docs/current/queries-overview.html);
        like `SELECT random()`
      * ... using values from outer query are 
        [correlated subqueries](https://en.wikipedia.org/wiki/Correlated_subquery) /
        [scalar subqueries](https://www.postgresql.org/docs/current/sql-expressions.html#SQL-SYNTAX-SCALAR-SUBQUERIES)
        * correlated subqueries can be slow because they may be evaluated for each row
        * correlated subqueries appear in SELECT or WHERE clauses
  * [common table expessions (CTE) / WITH queries](https://www.postgresql.org/docs/current/queries-with.html)
    * `WITH` query allows to extract a subquery into temporary table used by the whole query
    * advantages
      * make complex query easier to understand
      * produce a temporary table that we can refer to several times/places in query
      * allow recursive query
      * (might be more performant: `WITH` query are normally evaluated only once per execution of the parent query, even if they are referred to more than once by the parent query or sibling `WITH` queries)
    * [recursive common table expessions](https://www.postgresql.org/docs/current/queries-with.html#QUERIES-WITH-RECURSIVE)
      * recursive CTE are quite different and more complex than normal CTE
      * recursive CTE are usefull to parse a tree or graph
    * see also [SQL CTE Explained](https://learnsql.com/blog/what-is-sql-cte/) and [What Is a Recursive CTE in SQL?](https://learnsql.com/blog/sql-recursive-cte/)
  * [types](https://www.postgresql.org/docs/current/datatype.html)
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
  * [type casts](https://www.postgresql.org/docs/current/sql-expressions.html#SQL-SYNTAX-TYPE-CASTS) with `::` or `CAST(...)`
      * `SELECT 10::BOOLEAN` (PostgreSQL specific)
      * `SELECT CAST(10 AS BOOLEAN)` (sql standard)
      * tip: `COALESCE(value::BOOLEAN::INTEGER, 0)` to convert value to [0|1] number that can be used 
        in CHECK or aggregate functions
  * [functions & operators](https://www.postgresql.org/docs/current/functions.html)
    * [logical](https://www.postgresql.org/docs/current/functions-logical.html): 
      `AND`, `OR`, `NOT`
    * [comparison](https://www.postgresql.org/docs/current/functions-comparison.html):
      `<`, `>=`, `=`, `<>`, `BETWEEN`, `IS NULL`, `IS TRUE`, etc.
      * be careful with comparison with `NULL`, do not write expression = NULL (see [comparison](https://www.postgresql.org/docs/current/functions-comparison.html))
    * [mathematical](https://www.postgresql.org/docs/current/functions-math.html): 
      `+`, `*`, `%`, `abs`, `round`, etc.
    * [string](https://www.postgresql.org/docs/current/functions-string.html): 
      `||`, `lower`, `substring`, `trim`, etc.
    * [pattern matching](https://www.postgresql.org/docs/current/functions-matching.html):
      `LIKE`, etc. 
    * [data type formatting](https://www.postgresql.org/docs/current/functions-formatting.html):
      `to_char`, `to_date`, etc.
    * [date/time](https://www.postgresql.org/docs/current/functions-datetime.html):
      `+`, `-`, `current_date`, `current_timestamp` (or `now()`), `date_trunc`, etc.
    * [conditional](https://www.postgresql.org/docs/current/functions-conditional.html):
      [CASE](https://www.postgresql.org/docs/current/functions-conditional.html#FUNCTIONS-CASE), 
      [COALESCE](https://www.postgresql.org/docs/current/functions-conditional.html#FUNCTIONS-COALESCE-NVL-IFNULL), etc.
    * [aggregate](https://www.postgresql.org/docs/current/functions-aggregate.html):
      `count`, `max`, `avg`, `sum`, etc.
    * [subquery expressions](https://www.postgresql.org/docs/current/functions-subquery.html):
      [EXISTS](https://www.postgresql.org/docs/current/functions-subquery.html#FUNCTIONS-SUBQUERY-EXISTS),
      [IN](https://www.postgresql.org/docs/current/functions-subquery.html#FUNCTIONS-SUBQUERY-IN),
      [ANY/SOME](https://www.postgresql.org/docs/current/functions-subquery.html#FUNCTIONS-SUBQUERY-ANY-SOME),
      [ALL](https://www.postgresql.org/docs/current/functions-subquery.html#FUNCTIONS-SUBQUERY-ALL), etc.
    * other: 
      [sequence manipulation](https://www.postgresql.org/docs/current/functions-sequence.html),
      [enum](https://www.postgresql.org/docs/current/functions-enum.html),
      [UUID](https://www.postgresql.org/docs/current/functions-uuid.html),
      [JSON](https://www.postgresql.org/docs/current/functions-json.html), ...
  * [indexes](https://www.postgresql.org/docs/current/indexes.html) allows to find rows much faster
    * [B-Tree](https://www.postgresql.org/docs/current/indexes-types.html#INDEXES-TYPES-BTREE) is most used [index type](https://www.postgresql.org/docs/current/indexes-types.html)
    * index are automatically created for primary key and UNIQUE constraints but not foreign keys
      * see [Should I Create an Index on Foreign Keys in PostgreSQL?](https://www.percona.com/blog/should-i-create-an-index-on-foreign-keys-in-postgresql/)
      * and [Are your foreign keys indexed?](https://www.cybertec-postgresql.com/en/index-your-foreign-key/)
      <details>
        <summary>Click to see a query to find missing index on foreign keys</summary>

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
    allow to reuse query (DRY)
    * views allow you to encapsulate the details of the structure of your tables, which might change as your application evolves, behind consistent interfaces
    * view vs materialized view
      * query is executed every time for view but not for materialized views
      * materialized views are _caches_ populated manually with [REFRESH MATERIALIZED VIEW](https://www.postgresql.org/docs/current/sql-refreshmaterializedview.html)
      * materialized views are useful for expensive queries
* transactions handling
  * PostgreSQL has autocommit by default
  * disable autocommit with [START TRANSACTION](https://www.postgresql.org/docs/current/sql-start-transaction.html)
* query tuning
  * use [EXPLAIN](https://www.postgresql.org/docs/current/sql-explain.html) to benchmark query
  * see [planner cost constants](https://www.postgresql.org/docs/current/runtime-config-query.html#RUNTIME-CONFIG-QUERY-CONSTANTS) used by query planner
    * cost of a disk page fetch is 1.0 is used as reference
  * EXPLAIN provide two costs, e.g. `(cost=left..right )`
    * left value = _startup_ cost for this step to produce the first row
    * right value = _total_ cost for this step to produce all rows
  * goal is to identify which steps are expensive
  * tip: existing index might be not used if sequential readings is more performant than a lot of random accesses (and maybe index could be removed if never used)
* concurrency
  * ACID: 
    [Atomicity](https://www.postgresql.org/docs/15/glossary.html#GLOSSARY-ATOMICITY),
    [Consistency](https://www.postgresql.org/docs/15/glossary.html#GLOSSARY-CONSISTENCY),
    [Isolation](https://www.postgresql.org/docs/15/glossary.html#GLOSSARY-ISOLATION),
    [Durability](https://www.postgresql.org/docs/15/glossary.html#GLOSSARY-DURABILITY)
  * [type of locks](https://www.postgresql.org/docs/current/explicit-locking.html)
  * [transaction isolation](https://www.postgresql.org/docs/current/transaction-iso.html)
  * [CAP theorem](https://en.wikipedia.org/wiki/CAP_theorem)
* schema/data migration
  * schema migration file: precise change to make to database and its counterpart to revert the change (up/down)
  * **best-practise**: schema and data migration files should be done in separate steps (over a few days/weeks) along with changes in applications (consumers/producers), e.g.
    * step 1: add new column (_schema migration_)
    * step 2: applications write in old/new column
    * step 3: copy values from old to new (_data migration_, might take time)
    * step 4: applications write only in new column
    * step 5: drop old column (_schema migration_)
  * if a lot of rows must be updated, update should be done in several transaction 
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
    * see [guide of migrations with flyway](https://documentation.red-gate.com/fd/migrations-184127470.html)
* [server programming](https://www.postgresql.org/docs/current/server-programming.html):
  [functions](https://www.postgresql.org/docs/current/xfunc-sql.html),
  [triggers](https://www.postgresql.org/docs/current/triggers.html), etc.
* [SQL Commands](https://www.postgresql.org/docs/current/sql-commands.html)
  * CRUD: [SELECT](https://www.postgresql.org/docs/current/sql-select.html),
    [INSERT](https://www.postgresql.org/docs/current/sql-insert.html),
    [UPDATE](https://www.postgresql.org/docs/current/sql-update.html),
    [DELETE](https://www.postgresql.org/docs/current/sql-delete.html),
  * transactions
   handling: [START TRANSACTION](https://www.postgresql.org/docs/current/sql-start-transaction.html) (or [BEGIN](https://www.postgresql.org/docs/current/sql-begin.html)), [COMMIT](https://www.postgresql.org/docs/current/sql-commit.html), [ROLLBACK](https://www.postgresql.org/docs/current/sql-rollback.html) 
  * [DDL / data definition](https://www.postgresql.org/docs/current/ddl.html):
    * [[CREATE](https://www.postgresql.org/docs/current/sql-createtable.html)|[ALTER](https://www.postgresql.org/docs/current/sql-altertable.html)|[DROP](https://www.postgresql.org/docs/current/sql-droptable.html)]
      TABLE
    * [[CREATE](https://www.postgresql.org/docs/current/sql-createindex.html)|[ALTER](https://www.postgresql.org/docs/current/sql-alterindex.html)|[DROP](https://www.postgresql.org/docs/current/sql-dropindex.html)]
        INDEX
    * [[CREATE OR REPLACE VIEW](https://www.postgresql.org/docs/current/sql-createview.html)|[DROP](https://www.postgresql.org/docs/current/sql-dropview.html)]
        VIEW
    * [[CREATE](https://www.postgresql.org/docs/current/sql-creatematerializedview.html)|[DROP](https://www.postgresql.org/docs/current/sql-dropmaterializedview.html)|[REFRESH](https://www.postgresql.org/docs/current/sql-refreshmaterializedview.html)]
        MATERIALIZED VIEW
  * [query tuning](https://www.postgresql.org/docs/current/using-explain.html): 
    * [EXPLAIN](https://www.postgresql.org/docs/current/sql-explain.html): info about query plan
    * `EXPLAIN ANALYZE`: info about runned query (take care with update query!)
  * [schema search path](https://www.postgresql.org/docs/current/ddl-schemas.html#DDL-SCHEMAS-PATH)
    * [SHOW](https://www.postgresql.org/docs/current/sql-show.html) [search_path](https://www.postgresql.org/docs/current/ddl-schemas.html#DDL-SCHEMAS-PATH): allow to display current schema search path
    * [SET](https://www.postgresql.org/docs/current/sql-set.html) [search_path](https://www.postgresql.org/docs/current/ddl-schemas.html#DDL-SCHEMAS-PATH): allow to define schema search path 
* References
  * [Awesome Postgres](https://github.com/dhamaniasad/awesome-postgres) : 
    compilations of links about PostgreSQL
* Links & Tools
  * https://pg-sql.com/: temporary online Postgres Database
  * [dbeaver](https://dbeaver.io/) or 
    [pgAdmin](https://www.pgadmin.org/) as db tool
  * https://ondras.zarovi.cz/sql/demo/ or  
    [dbdiagram.io](https://dbdiagram.io/home) as sql schema designers
    * see [DBML](https://www.dbml.org/home/)
  * [flyway](https://flywaydb.org/) or
    [liquibase](https://www.liquibase.com/) 
    as database version control / for schema migration
  * [SQL and PostgreSQL: The Complete Developer's Guide](https://www.udemy.com/course/sql-and-postgresql/) course

[*Go to parent page*](README.md)

*(Page mainly started in March 2023; links checked on 12.02.2024)*
