# [C# Essential Training: Syntax and OOP](https://www.lynda.com/C-tutorials/Extending-class-create-new-class/642480/689749-4.html)

## What is C#?

    + Microsoft announced in July 2000 along with .NET Framework
    + .NET framework
        + Framework Class Library: Provides the means to execute code written in a variety of languages,
        including C#. Also provides a standard library.
        + Common Language Runtime: Application virtual machine focused on what is needed to run your code.
    + Running C#
        + Compiled to intermediate product (bytecode)
        + CLR executes bytecode after running it through Just-In-Time compiler
        + So, managed code

## The Basics

    + REPL in Visual Studio: C# interactive window
    + Declaring variables:
        + Standard declaration with `type name` as is usual 
        + Also `var` declaration with `var name`, which uses **implicit typing** from the assignment
    + Everything is an object (including primitives)
    + `String.Format` for formatting strings
    + Parsing strings into numbers: all numeric types have a `.Parse()` method
    + `out` parameters - send variables back out of a method. See `TryParse`, for example

## Working with Classes

    + Namespaces: prevent naming collisions (in the same way they work in other languages)
    + Member variables:
        + **Field**: simplest kind of member variable
        + **Auto-Property**:
            + Simplest kind of property
            + `{ get; set; }`
            + Getters and setters with no logic
        + **Property**:
            + Backing variable (holds the value of the property)
            + `get` and `set` manipulate the backing variable
            + `value` is what's being passed in to the setter
    + Function-bodied Expression:
        + Different way of defining functions
        + Arrow function (or lambda)
        + More concise

## Object-Oriented Features

    + `base` instead of `super`
    + `virtual` and `override`
    + Can have properties in interfaces
    + Extension methods
 
## Conclusion

    + Takeaways:
        + Some differences in features and syntax from Java (which I'm much more familiar with)
        + Otherwise, nothing shocking in this course
    + Next steps:
        + Continue down LinkedIn's C# Learning Path
        + Find some more advanced C# classes to take
