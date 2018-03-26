# [Learning C# Algorithms](https://www.lynda.com/C-tutorials/Using-exercise-files/604241/636298-4.html)

## Introduction

+ Why algorithms and data structures are important
  + Performance
  + Architechture
  + Interviews
+ When to use
  + Overall architecture
  + Reuse wherever possible
  
## Data Structures

+ Linked List
  + Structure
    + Nodes each linked to the next (and perhaps the previous)
    + Special nodes: head, tail
    + Variations: singly linked, doubly linked
  + Operations
    + Add (variations -- add at head, add at tail, etc)
    + Delete
    + Search
  + Comparison to array:
    + Flexible length (as opposed to arrays with fixed length)
    + No random element access
  + Built-in implementation in .NET: `LinkedList<>`
+ Stack
  + Structure:
    + Underlying structure irrelevant
    + Just remember: LIFO
  + Operations:
    + Push: push an element onto the head of the stack
    + Pop: pop an element from the head of the stack
    + Peek: look at the head element without removing it
  + Built-in implementation in .NET: `Stack<>`
+ Queue
  + Structure:
    + Underlying structure irrelevant
    + Just remember: FIFO
  + Operations:
    + Enqueue: Add to the back of the line
    + Remove (aka Dequeue): remove from the front of the line
    + Peek: may or may not have peek for front and/or back
  + Built-in implementation in .NET: `Queue<>`

## Search Algorithms

+ Binary Search
  + Key Preconditions:
    + Operate on sorted data structure
    + Data structure must allow arbitrary access in constant time
  + Main points:
    + Hit midpoint of structure
    + If midpoint greater than desired element, look to left. Otherwise look right.
    + Eventually either find element or realize it can't be there
  + Performance:
    + `log n` in average case
    + However, overhead of sorting array in the first place
  + Built-in .NET implementations for various collection classes
+ Linear Search
  + Key preconditions:
    + None really
    + Just need an iterable collection of elements
  + Main points:
    + This is easy: start at the beginning and go until you find the element or hit the end
    + Depending on which, return result
  + Performance:
    + `n` running time
    + Don't need to sort to start

## Takeaways

 + Basics of Data Structures and Algorithms
 + Finish up this C# Developer Learning Path
