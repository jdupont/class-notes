# [Learning Node.js](https://www.amazon.com/Learning-Node-js-Hands-Applications-JavaScript/dp/0321910575)

## Node.js Basics

+ JavaScript Basics
  + This part of the book is a bit outdated with the introduction of ES5 and ES6
  + Mostly covers things I’ve already learned
+ Asynchronous vs Synchronous Programming
  + Synchronous programming
    + Typical way of doing things
    + Major disadvantage: programs spend much of their time doing nothing (e.g., waiting on file system)
    + OS can still switch between processes (or threads), but that has a lot of overhead
  + Asynchronous programming is an answer to this problem
    + Instead of sequential statements
    + Callbacks that execute when each operation is done
+ Node error handling patterns
    + Throwing/catching exceptions doesn’t work because a catch statement in a callback won’t envelop the context of thrown exception
    + So, callback usually takes error object as first parameter
    + If error is null, operation completed properly
    + If error is not null, callback needs to deal with the problem
    + Dealing with errors in callback
      + If non-null, return (probably print error to console too).
      + If null, do what you do.

## Modules

+ Every file is a module
+ Easy to define your own modules

## async

+ Tired of callback hell? 
+ Async.waterfall to have the same flow as callbacks without the nesting
+ Other async options for other flows
+ Powerful way to manage timing of asyncs

## Streams

+ Read and write files with streams
+ Typical read flow:

  1) Create stream
  2) Add events listeners for specific events like `readable` and `end`

+ Typical write flow:

  1) Create stream
  2) Write to stream which will notify other listeners
  
+ Streams are a more "node" way of reading files which leverage the asynchronous model better

## Different web abb paradigm

+ Old way:
  1) Client sends page request to server
  2) Server builds that page
  3) Sends the page back to the client
+ New way:
  1) Client sends page request to server
  2) Server responds with barebones template and javascript code
  3) Client executes template and javascript
  4) Client code requests data from server (often RESTful)
  5) Client assembles page from template and data on client-side
+ Often single-page applications

## RESTful APIs

+ RESTful:
  + **RE**presentational
  + **S**tate
  + **T**ransfer
+ Typically has four main kinds of operations:
  + PUT: create documents
  + GET: retrieve documents
  + POST: update documents
  + DELETE: remove documents

## Deployment

+ Most basic: just run it
+ But, not robust. Does not deal with crashes or other problems
+ Still naive:
  + Put it in an infinite loop that restarts on crash
  + Better, but still not robust:
    + What about constant, reoccuring crashes?
    + What about ridiculous resource usage?
+ Best:
  + Use somebody else's deployment system
  + They've dealt with these problems before
  
## Multi-processor

+ Node is fundamentally single-threaded
+ So, how to take advantage of multiple cores?
+ Balance load across multiple processes, each running on its own core
+ Must manage memory across cores

## Outside of the Web

+ Node can also be used for things other than web programming
+ For example, command line scripts
+ Not sure if this happens in practice (or why you would choose node over something like Python)
