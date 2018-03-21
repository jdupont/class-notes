# [Nail Your C# Developer Interview](https://www.lynda.com/C-tutorials/Overview/604242/634130-4.html)

## C# Questions

+ Reference vs Value
  + What's a **reference type**?
    + Reference type stores a reference to the actual data
    + Examples of reference types are classes, interfaces, delegates, objects, and strings.
  + What's a **value type**?
    + Value types actually hold values
    + Examples include `enum`, `bool`s, other primitive types
+ What's an **interface**?
  + Contract: specifies methods of a class
  + No implementation
+ What's an **abstract class**?
  + Class that can't be instantiated
  + Signficant differences from interfaces (worth comparing)
+ What's a **static class**?
  + Unit of organization for methods not associated with particular objecs
  + Can't be instantiated or extended
+ What are **generics**?
  + Ability to specify type as a parameter
  + Improves type checking, code reuse, etc

## Object-Oriented Questions

+ What's **polymorphism**?
  + Presenting the same interface for different underlying forms
  + For example, `Animal` class being extended to `Dog` and `Cat`. Same interface, different behavior.
+ What's **encapsulation**?
  + Preventing access to implementation details
+ What's **inheritance**?
  + Child extends parent
+ Four pillars of OOP
  + Abstraction
  + Polymorphism
  + Inheritance
  + Encapsulation
  
## .NET Questions

+ What's the **Common Language Runtime**?
  + Virtual machine component of .NET
  + Manages execution of .NET code
+ What's the **Framework Class Library**?
  + Reusable code for .NET (standard library)
+ What's **.NET**?
  + Managed execution environment to build and run applications
  + Consists of two major components: CLR & FCL
+ What's **managed code** vs **unmanaged code**?
  + Managed code: Compiles to intermediate language (e.g., bytecode) and then has execution managed by a VM
  + Unmanaged code: Compiles directly to machine code and then runs on machine directly
+ **Boxing**
  + Boxing is the process of converting a value type to an object type
  + Unboxing is the reverse
  + Prior to generics, this was how it was done
  
## ASP.NET Questions

+ Common question topics:
  + Page life-cycle events
  + Page life-cycle stages
  + ASP.NET vs MVC
  + Advantages of razor
+ Revisit this when I have more ASP.NET knowledge

## Database Questions

+ What's an **inner join**?
  + select records that have matching values in both tables
  + SQL: `SELECT * FROM table1 INNER JOIN table2 ON table1.column = table2.column;`
+ **Join** in general
  + Examples: **Left Join**, **Right Join**, **Full Outer Join**
  + Have an idea of what each join does
+ **Stored Procedures**
  + Batch of SQL statements stored in database
  + Can have performance benefits

## Design Pattern Questions

+ What's **[Dependency Injection](https://stackoverflow.com/questions/130794/what-is-dependency-injection)**?
  + Exactly what it sounds like. Instead of one class being responsible for creating its own dependencies,
  they are supplied from an external source
  + Loose coupling
  + Testing
  + Closely related to **[inversion of control](https://stackoverflow.com/questions/6550700/inversion-of-control-vs-dependency-injection)**
+ Be familiar with a variety of patterns and where they might be used
