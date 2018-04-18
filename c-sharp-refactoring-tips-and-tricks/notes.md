# [C# Refactoring Tips and Tricks(https://www.lynda.com/C-tutorials/Welcome/612186/716226-4.html)

## What is refactoring?

+ Making internal changes to software system without affecting external behavior
+ Reasons to refactor:
  + Improve maintainability
  + Remove dead or useless code
  + Optimize code
  + Reduce technical debt

## Prior to Refactoring

+ Create a baseline
  + Useful for comparing after having made changes
  + Gives you something to revert back to if you screw up
+ Set up an environment for the refactoring
  + Version control
  + Probably need a refactoring branch (don't refactor in the main branch)
  + Tools can also help with refactoring:
    + IDEs have built in support for some operations, like renaming
    + Can also add other tools like Resharper
+ Create a refactoring plan
+ Set up tests

## Optimizing Code

+ Can be very tricky
+ Make sure to measure
+ Instructor talks about a few specific strategies but:
  + Much deeper topic than can be covered in this one course
  + Some of these feel like micro-optimizations that are probably unwarranted for the vast majority of C# programs

## Cleaning Up Code

+ Code smell: any symptom in a codebase that could possibly indicate a deeper problem
+ Sounds like this guy read *Code Complete*

## Takeaways

+ Not really about C#
+ Really about refactoring strategies
+ Should probably read Martin Fowler's seminal book about refactoring to get a better view of this important process
