# [C# Essential Training Part 2](https://www.lynda.com/C-tutorials/What-you-should-know/642481/690741-4.html)

## Unit Testing and TDD

+ Test Driven Development (TDD)
  + Create repeatable tests
  + Write code
  + See if tests work
  + Goal: 100% test coverage
+ Unit tests and TDD are fundamental to Agile Programming

## Arrays and Collections

+ Curly brace initializers available for arrays:

```
var groceryList = new string[4] { "Milk", "Eggs", "Cheese", "Apples" };
```

+ Can resize arrays with `Array.Resize()` (not sure why you'd want to do that instead of a `List` though)
+ `ref` keyword passes variables by reference
+ Multidimensional arrays are different from what I'm used to so be aware of that
+ LINQ
  + **L**anguage **IN**tegrated **Q**uery
  + Hooks up to the .NET collection classes
  + This is really cool
+ Dictionaries, sets, etc

## Flow Control

+ `if`, `if-else`, `switch`, etc. Pretty standard.
+ `for`, `foreach`, `while`, `do-while` loops. Also pretty standard.

## Exception Handling

+ Runtime Exceptions. Also also pretty standard.
+ `using` statements:
  + analogous in many ways to `try-with-resources` in Java
  + Leverages `IDisposable`
+ `@` for raw strings
+ `try-catch-finally`. Pretty standard as well.

## Getting to Production

+ NuGet Package Management:
  + Distrubtes packages with a registry
  + Integrated in VS
+ Logging is a good idea
+ Different build options for production and debugging

## Conclusion

+ So far, so good. Pretty standard introductory level language features.
+ Next Steps:
  + [LINQ specific course](https://www.lynda.com/LINQ-tutorials/LINQ-C-Essential-Training/397357-2.html)
