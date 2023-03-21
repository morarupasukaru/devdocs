# PostgreSQL

[PostgreSQL Documentation](https://www.postgresql.org/docs/current/index.html)
* [Tutorial](https://www.postgresql.org/docs/current/tutorial.html)
* [SQL Language](https://www.postgresql.org/docs/current/sql.html)
  * [data definition (ddl)](https://www.postgresql.org/docs/current/ddl.html)
    * [constraints](https://www.postgresql.org/docs/current/ddl-constraints.html)
      * [PRIMARY KEY](https://www.postgresql.org/docs/current/ddl-constraints.html#DDL-CONSTRAINTS-PRIMARY-KEYS)
      * foreign keys with [REFERENCES](https://www.postgresql.org/docs/current/ddl-constraints.html#DDL-CONSTRAINTS-FK) and `ON DELETE` *referential_action* (see [CREATE TABLE](https://www.postgresql.org/docs/current/sql-createtable.html))
  * [queries](https://www.postgresql.org/docs/current/queries.html)    
    * [queries with JOIN](https://www.postgresql.org/docs/current/queries-table-expressions.html#QUERIES-FROM) (inner join, left outer join, right outer join, full join)
    * [grouping with GROUP BY and HAVING](https://www.postgresql.org/docs/current/queries-table-expressions.html#QUERIES-GROUP)
    * [sort with ORDER BY](https://www.postgresql.org/docs/current/queries-order.html)
    * [retrieve a portion of rows with LIMIT and OFFSET](https://www.postgresql.org/docs/current/queries-limit.html)
    * [combining with UNION [ALL], (INTERSECT, EXCEPT)](https://www.postgresql.org/docs/current/queries-union.html)
    * [eliminate dupplicate rows with DISTINCT](https://www.postgresql.org/docs/current/queries-select-lists.html#QUERIES-DISTINCT)
  * [data types](https://www.postgresql.org/docs/current/datatype.html)
    * [numeric types](https://www.postgresql.org/docs/current/datatype-numeric.html)
      * [serial](https://www.postgresql.org/docs/current/datatype-numeric.html#DATATYPE-SERIAL) like SERIAL (PostgreSQL specific)
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
    * [conditional expressions](https://www.postgresql.org/docs/15/functions-conditional.html)
      like [GREATEST and LEAST](https://www.postgresql.org/docs/15/functions-conditional.html#FUNCTIONS-GREATEST-LEAST), 
      [CASE](https://www.postgresql.org/docs/15/functions-conditional.html#FUNCTIONS-CASE), 
      [COALESCE](https://www.postgresql.org/docs/15/functions-conditional.html#FUNCTIONS-COALESCE-NVL-IFNULL)


Links
* https://pg-sql.com/: temporary online Postgres Database
* https://www.diagrams.net/ : diagrams editor, TODO keep link?
* [Awesome Postgres](https://github.com/dhamaniasad/awesome-postgres) : compilations of links about PostgreSQL

*(Page mainly started in march 2023)*

[*Go to parent page*](../README.md)
