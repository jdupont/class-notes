# Programming Foundations: Design Patterns

## What are design patterns?

+ Solutions to common software design problems
+ Shared vocabulary when communicating about designs
+ Origins
    + Gang of Four
    + Twenty-three original patterns
        
## What do you already know?

+ 8/10 Correct
+ Missed questions about the specifics of some design patterns
    
## Overall Design Principles:

+ Identify the aspects of your code that vary and separate them from what stays the same -- Encapsulate What Varies
+ Program to an interface, not an implementation
+ Favor composition over inheritance
+ Strive for loosely coupled designs between objects that interact
+ Classes should be open for extension but closed for modification -- Open/Closed Principle

## Strategy Pattern

+ Inheritance
    + "Is A" relationship
    + Often overused - can result in code that is inflexible and difficult to modify/extend
+ Interfaces
    + Can unfortunately lead to code duplication
+ Change “is a” to “has a”
+ Now easy to add and modify behaviors without changing other code because parent class does not know about the internals of the behavior
+ Can also change behaviors on the fly (at runtime)
+ So:
    + When to Use: 
        + A superclass needs to use a variety of algorithms (behaviors) in an interchangeable way
        + Might need to change algorithms at runtime
    + How to Use:
        + Superclass “has a” “behavior”
        + “Behavior” implements an algorithm
        + Superclass executes “behavior” to perform a given action
    + Why to Use:
        + Improves flexibility by not tying a superclass to a specific implementation of an algorithm
        + Improves reuse by reuse of behavior implementations

## Observer Pattern

+ Overall:
    + One publisher that owns data and notifies many subscribers when data changes
+ Publishers
    + Own the data
    + Data can change
    + Notifies subscribers
+ Subscribers (a.k.a Observers)
    + Do not own the data
    + Subscribe to publishers
    + Get updated when publishers change
+ So:
    + When to use?
        + Have data with one source of truth that many other pieces of code are interested in
    + How to use:
        + Create a publisher that has a collection of observers
        + When data changes in publisher, iterate through collection of observers and notify each one
    + Why to use:
        + Preserves one source of truth in data instead of duplicating data everywhere
        + Loose coupling between source of data (publisher) and consumers of data (subscribers)

## Decorator Pattern
+ Attaches additional responsibilities to an object dynamically
+ Provides a flexible alternative to subclassing for functionality
+ So:
    + When to use:
        + Need to add arbitrary behavior, possibly in multiple layers
    + How to use:
        + Components
        + Decorators
        + Decorators are components (e.g., Decorators extend Components)
        + Decorators wrap components and decorators
        + So, can add arbitrary number of decorators to any component.
    + Why to use:
        + Open/Closed Principle
        + More flexible for extension without having to rewrite existing code
