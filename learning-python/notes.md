# [Learning Python](https://www.lynda.com/Python-tutorials/Learning-Python/661773-2.html)

## Fundamentals

+ Interpreted language:
  + Is not compiled and built into an executable before running
  + Is interpreted as runtime
+ Variable types are inferred based on contents of variable
+ Strongly typed -- can't implicity convert between types
+ Variables are scoped by function
  + Can use `global` variables in local scope using `global` keyword
  + Can delete variables with `del`
  + Good discussion of [overall scoping rules](https://stackoverflow.com/questions/291978/short-description-of-the-scoping-rules):
    + LEGB
    + **Local**: Names assigned in any way within a function or lambda (but without `global`)
    + **Enclosing-function Locals**: Name in the local scope of any and all statically enclosing functions (`def` or `lambda`),
    from inner to outer
    + **Global** (module): Names assigned at the top-level of a module file, or by executing a global statement in a def within the file
    + **Built-in**: Names preassigned in the built-in names module : `open`, `range`, `SyntaxError`, ...
  + So, **blocks are not scopes**. A variable declared in an `if` will be hoisted to the next applicable LEGB scope.
  
## Python Basics
  
+ Functions
  + Objects that can be passed around
  + Can have default values in arguments
  + Can call functions with named parameters instead of following parameter order
  + Also have variable object lists
+ Conditional structures:
  + `while` and `for` loops -- that's it
  + `for` is different from what I'm used to:
    + `for` is an iterator
    + Not counter based, but can get an index with `enumerate`
```python
for x in range(5, 10):
```
  + `break` and `continue`
+ Classes:
  + `class` keyword
  + Has inheritance (including multiple inheritance)
  + `self` keyword in definitions of instance methods
+ `import`
  + `from` -- what module
  + `import` -- which peice to import

## Working with Dates and Time

+ `date`, `time`, `datetime` classes: pretty standard reasoning here
+ `timedelta`
  + A span of time
  + Use this to perform time-based mathematics
+ `calendar` class: perform calendar manipulations and calculations

## Working with Files

+ Python knows about files without any `import`s
+ Look up API if needed

## Working with Web Data

+ `urllib` and `request` for getting data from the web
+ `json` for working with JSON
+ Also has facilities for working with other kinds of structured data, like HTML

## Useful Things to Remember:

+ Python has a REPL
+ Calling `main` only if main:
```python
def main():
    print("Hello world.")
    
if __name__ == "__main__":
    main()
```

## Takeaways

  + Some significant differences between Python and other languages I'm used to working with:
    + Syntactical differences: For example, no `do-while` loop
    + Philosophical differences: For example, why there's no `do-while` loop
    + Practical differences: For example, interpreted vs compiled
  + Next steps: 
    + Let's build something in Python
    + Figure out where my weak spots are
    + Get a bit more of an overall picture of Python in practice
