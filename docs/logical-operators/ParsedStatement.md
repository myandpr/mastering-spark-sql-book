# ParsedStatement Logical Operators

`ParsedStatement` is an extension of the [LogicalPlan](LogicalPlan.md) abstraction for [logical operators](#implementations) that hold exactly what was parsed from SQL statements.

`ParsedStatement` are never resolved and must be converted to concrete logical plans.

## Implementations

* `LeafParsedStatement`
* `UnaryParsedStatement`
    * [InsertIntoStatement](InsertIntoStatement.md)
