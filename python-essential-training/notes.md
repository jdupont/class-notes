# [Python Essential Training](https://www.lynda.com/Python-tutorials/Python-Essential-Training/614299-2.html)

## The Zen of Python

+ `import this`
+ Guiding Statements:
  + Beautiful is better than ugly.
  + Explicit is better than implicit.
  + Simple is better than complex.
  + Complex is better than complicated.
  + Flat is better than nested.
  + Sparse is better than dense.
  + Readability counts.
  + Special cases aren't special enough to break the rules.
  + Although practicality beats purity.
  + Errors should never pass silently.
  + Unless explicitly silenced.
  + In the face of ambiguity, refuse the temptation to guess.
  + There should be one-- and preferably only one --obvious way to do it.
  + Although that way may not be obvious at first unless you're Dutch.
  + Now is better than never.
  + Although never is often better than *right* now.
  + If the implementation is hard to explain, it's a bad idea.
  + If the implementation is easy to explain, it may be a good idea.
  + Namespaces are one honking great idea -- let's do more of those!
+ Guido van Rossum
  + Benevolent Dictator for Life
  + Wrote the first Python interpreter and remains involved in the Python community to this day
  
## Language Overview

+ Expressions vs Statements
  + Expression: any combination of literals, identifiers, and operators (unit of evaluation)
  + Statement: any line of code (unit of execution)
+ Whitespace is significant
  + Indentation defines blocks
  + Verified by compiler
+ Objects: everything is an object

## Types and Values

+ Duck Typing
  + Form of dynamic typing
  + If it walks like a duck, it's a duck
  + Infer type of variable from value
+ `String` Type:
  + Class with various useful methods
  + `f` string -- that's pretty cool
+ Numeric Types:
  + Integer division: `7 // 3`
  + Otherwise leads to floating point by default
  + Also have arbitrary precision arithmetic classes
+ Boolean Type:
  + Built-in boolean type
  + Various other things evaluate to `False`
  + Usually, empty or 0 evaluates to `False`
+ Sequence/Aggregate Types:
  + List:
    + `[]`
    + Mutable sequence
    + Variable length
  + Tuples:
    + `()`
    + Immutable
  + Dictionary:
    + `{}`
    + Map
  + Can generate sequences with `range`
+ `type()` and `id()`
  + Everything is an object, so types are objects too
  + `id` returns an unique identifier for each object
  + `is` operator has `id` semantics
  + Also has `isinstance` for checking type

## Conditionals

+ Pretty much as expected
+ Ternary conditional operator:

```python
x = 'feed the bear' if hungry else 'Do not feed the bear'
```

## Functions

+ All functions return a value (even if that value is just `None`)
+ Can give default values to function parameters
+ Some trickiness with `id` when it comes to pass by value
+ Variable length arguments with `*args` or `**kwargs`
+ Generator function:
  + Returns a stream of values
  + `yield`
+ Also has function decorators

## Structured Data

+ Basic sequential types: lists and tuples
+ List is mutable; tuple is not
+ Also a dictionary type and a set type
+ Cool operations for intersections of sets
+ List comprehension:
  + Way of generating sequences from other sequences
  + Example:
  
```python
sequence = [round(pi, i) for i in original_sequence]
```

## Classes

+ `__init__` for constructor
+ `_` naming convention for class variables
+ `self` gets passed around for you
+ Doesn't have to be named `self` but everyone will be pretty confused if you don't
+ No visibility modifiers
+ Special method names like `__str__` (which is the equivalent of `toString`)
+ Can also have static variables by defining at class level
+ Has inheritance, including multiple inheritance

## Exceptions

+ `raise` an exception
+ `try`-`except`-`finally` as expected
+ Can also add an `else` clause to `try` blocks

## String Objects

+ Strings are immutable
+ String transformation methods return a separate string

## Takeaways

+ Great course for getting a pretty complete overview of features available in Python
+ Important to understand Python philosophy to make best possible use of Python
+ Next steps:
  + I took this for Python data science projects I'm doing, so I'll definitely apply it there
  + Maybe try out some HackerRank problems to see if I can leverage all of the language facilities available in Python
