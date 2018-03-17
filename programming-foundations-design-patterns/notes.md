# [Programming Foundations: Design Patterns](https://www.lynda.com/Developer-Programming-Foundations-tutorials/Foundations-Programming-Design-Patterns/135365-2.html)

## What are design patterns?

+ Solutions to common software design problems
+ Shared vocabulary when communicating about designs
+ Origins
    + Gang of Four
    + Twenty-three original patterns
            
## Overall Design Principles:

+ Identify the aspects of your code that vary and separate them from what stays the same -- Encapsulate What Varies
+ Program to an interface, not an implementation
+ Favor composition over inheritance
+ Strive for loosely coupled designs between objects that interact
+ Classes should be open for extension but closed for modification -- Open/Closed Principle
+ Single responsibility principle: a class should have only one reason to change

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
        + Might need to change algorithms at **runtime**
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
        + **Loose coupling** between source of data (publisher) and consumers of data (subscribers)

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

## Singleton Pattern

+ Ensures that a class has only on instance
+ Provides a global access point to that class
+ Examples where this would be desirable:
    + Logging facilities
    + Preference and registry objects
+ Classic implementation
    + Private constructor
    + Static instance variable
    + Lazily instantiated when Singleton is needed
+ But **be careful**:
    + Classic singleton pattern is **not thread-safe**
    + Race condition with instantiation can lead to multiple copies floating around
+ So:
    + When to use:
        + Depends. Be careful, singletons can rapidly become an anti-pattern
    + How to use:
        + Depends on threading concerns
    + Why to use:
        + Ensures that resource is available only once in system

## State Pattern

+ Implementation of a state machine in a way that is extensible and readable
    + Each state is an object
    + Each state implements the same interface that contains all of the transitions as methods
+ So:
    + When to use:
        + You're implementing a state machine
    + How to use:
        + Context owns the current state
        + State is an interface
        + Each possible state implements the State interface, which represents the possible transitions between states
        + When transition occurs, ask the current state what to do: move to next state, invalid, stay on current, etc
        + 
    + Why to use:
        + Open/Closed principle with respect to adding new states or transitions
        + More readable

## Iterator Pattern

+ Provides a way to access the elements of an aggregate object sequentially without exposing the underlying implementation of elements
+ So:
    + When to use:
        + You're working with aggregate objects (e.g., arrays, lists, etc)
        + You need to iterate through the elements in the aggregate
        + You don't want to tie yourself down to the implementation of the aggregate
    + How to use:
        + Aggregate creates and returns iterator
        + Iterator knows how to iterate
    + Why to use:
        + Loose coupling between aggregate object and client
        + Can change either without having to change both

## Factories

+ If object creation is what varies, then we need to encapsulate that
+ Factories are responsible for object creation
+ So:
    + When to use:
        + Need to create objects
        + But, don't want to specify the concrete implementation of the object being created
        + For example, if which concrete type created depends on paramaters
    + How to use:
        + Factory
        + Factory creates objects and gives them to client
    + Why to use:
        + Reduces dependence on concrete implementation
        + Makes it easier to modify how object creation works in the future

## Conclusion

+ Takeaways:
    + Well having some familiarity with these could have spared me a lot of pain in the past
    + Powerful solutions to problems I've faced
    + Also a powerful way of talking about design
+ Next steps:
    + Make an active effort to use this in my everyday coding
        + Recognize these patterns when they are implemented in the real world (and understand why the designers chose these patterns)
        + Use these patterns to solve my own design problems
    + Take another design pattern class or read the Gang of Four original book
    
