# [LINQ with C# Essential Features](https://www.lynda.com/LINQ-tutorials/Use-exercise-files/397357/451078-4.html)

## Data Overview

+ Two lists, each containing elements with standard structor
+ Customers:
  + Last name
  + First name
  + State of residence
  + Money spent
  + Items purchased
+ Distributors:
  + Name
  + State of residence
  
## LINQ Overview

+ Language Integrated Query
+ Three main parts:
  + LINQ to objects
  + LINQ to SQL
  + LINQ to XML
+ Common query language for interfacing with a variety of data sources
  + Common syntax
  + Easier to read
  + Easier to maintain
  + Easier to learn
  
## Basic LINQ Queries

+ Parts:
  + Data source
  + Query
  + Execution
+ Queries return `IEnumerable`
  + So, no data is iterated or fetched when query is created
  + Instead, data will be available when iterating over `IEnumerable`
  + Very important because no work is done here (so not using memory or disk resources yet)
  + However, some queries force immediate execution

## Data Transformation

+ Change type of result
  + Common use case
```csharp
var customerTransformationQuery = 
  from c in customers
  from p in c.Purchases
  select new { name = c.LastName, Purchase = p};
```
  + In this example, created a new kind of object in the `select` clause
+ Perform operation on each data element
  + Another common case
  + Transform data by performing some kind of operation on each element
  
## Type Relationships

+ LINQ is type-safe, so for LINQ queries to compile, types must match up
  + Range variable type comes from source data
  + Resulting data type depends on `select` clause return value
+ Using `var` can allow the compiler to select the best type for the result value (but make sure to use wisely)

## Standard Query

+ Filtering
  + Allows you to select only elements matching a given condition
  + Most common filter keyword is `where`
+ Ordering data
  + LINQ queries usually maintain order of the source data
  + Commonly done with `orderby`
+ Grouping
  + `group DATA by DATA.PROPERTY`
  + Returns a sequence of sequence: `IEnumerable<IGrouping<ResultType>>`
+ Finding overlap or commonalities between data sets
  + `join`
  + Different join types kind of like SQL

## Lambda Expressions

+ Query comprehension syntax
  + What we've been doing so far
  + Get translated into C# operations
+ Can also write more idiomatic C# operations directly using lambda expressions and **extension methods**:
```csharp
IEnumerable<Customer> query =
  from c in customers
  where c.State = "PA"
  select c;
```
is equivalent to:
```csharp
IEnumerable<Customer> query =
  customer.where(c => c.State = "PA");
```
+ Comprehension syntax is a smaller subset of all of the extension methods
+ Example extension methods:
  + `Distinct()`
  + `Take()`: takes only the specified number of elements
  + `Skip()`: skip the specified number of elements from the beginning of the sequence
  + `OrderBy()`: same as `order by` in comprehension syntax

## Complex Queries

+ Each extension method returns an `IEnumerable`, so they can be chained:
```csharp
IEnumerable<string> chained = customers.Skip(5).Take(3);
```
+ Can also chain queries in comprehension syntax with `into` keyword

## LINQ to SQL

+ LINQ to SQL converts LINQ query to a query that can be executed by database engine
+ Usually need some libraries to handle the database connection

## Takeaways

+ LINQ is really cool
+ Also really useful:
  + Strongly typed
  + Easier to switch between data sources since query language is universal
+ Next steps:
  + Continue learning about C#
  + Make sure to use LINQ where appropriate
