# [C#: Design Patterns](https://www.lynda.com/C-tutorials/C-Design-Patterns/473890-2.html)

## Categories of Design Patterns

+ Three categories of patterns:
  + Creational: Hide creation logic
  + Structural: Class and object composition
  + Behavioral: Communication between objects
+ Laid out in GoF

## Factory Pattern

+ Abstract away the creation of objects and the concrete type created
+ Already covered in previous courses

## Abstract Factory Pattern

+ Abstract class or interface that defines the contract of object creators
+ Concrete factory actually implements the object creation

## Singleton Pattern

+ Ensuring a class has only one instance
+ Providing a global access point to that instance
+ Need to make sure things are thread-safe

## Decorator Pattern

+ Attaches responsibility to an object dynamically
+ Use composition to wrap objects with new features/behavior/attribtutes

## Iterator Pattern

+ Iterate through collections
+ Abstracts away the implementation details of the collection

## Observer Pattern

+ Defines a one-to-many dependency for information flow
+ One subject/publisher
+ Many observers

## Repository Pattern

+ Not GoF, but common in C#
+ A repository separates business logic from interactions with the underlying data source
+ Creates an abstraction layer between application and data

## Unit of Work Pattern

+ Not GoF
+ Pairs with the repository pattern
+ Keeps track of everything you need to do during a business transaction with the database
+ Solves concurrency and atomicity problems

## Takeaways

+ Covered a number of design patterns I was already familiar with
+ Also added some new patterns specific to .NET
+ As before, need to continue to learn more patterns and practice them in my everyday coding
