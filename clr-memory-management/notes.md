# [CLR Memory Management for Developers](https://www.lynda.com/Windows-tutorials/CLR-Memory-Management-Developers/614301-2.html)

## Memory Management

+ Two general strategies: Manual vs Automatic
  + _Manual_: All memory management is the programmer's job
  + _Automatic_: All memory management is the system's job
+ There are tradeoffs:
  + Manual
    + Programmer error
    + Costs programmer time
  + Automatic
    + Management from GC is not always appropriate for every program
    + Adds overhead
    
## Glossary

+ _Allocator_: Responsible for obtaining memory on the heap
+ _Collector_: Determines what is eligible for release and releases it
+ _References_: Handles to blocks of allocated memory
+ _Activation Record_ or _Stack Frame_: Block of memory for a method/function/procedure. Typically on the stack.
+ _Object_: Space allocated for an entity
+ _ Heap_: Complete amount of space not dedicated for something else
+ _Page_: An OS-determined chunk of the heap. Paging can have ramifications for caching and therefore performance.
+ _Granule_: Smallest amount of allocable memory (often a machine word)
+ _Safety_: No live objects can be released.
+ _Throughput_: Number of objects that can be allocated/deallocated in a system in a given amount of time
+ _Pause time_: How long the GC needs to stop execution in order to do its job
+ _Space Overhead_: How much additional memory does the GC need for doing its job?
+ _Completeness_: Do we reclaim all eligible space?

## Fundamentals

+ Three basic tasks of any memory management system
  + Obtain memory
  + Use memory
  + Release memory
+ Three kinds of storage (usually logic rather than physical distinctions)
  + Static (bound to memory at compile time)
    + Code
    + Statics
    + Globals
  + Stack (procedure records on stack)
    + Locals
    + Calls
  + Heap (its not static and its not the stack)
    + Everything else
    + Usually objects
+ Needs to answer several core questions:
  + How do I know what to allocate and deallocate?
  + When do I allocate and deallocate?
  + How do I manage allocated storage?
  
## Automatic Memory Management: The General Principles

+ Four basic types of GC algorithms:
  + Reference counting
  + Mark & Sweep
  + Mark & Compact
  + Copying
+ Most modern languages use a hybrid approach

## Reference Counting

+ Each object carries its own ref count
+ When count == 0, object gets released
+ Big Questions
  + Who is responsible for increment and decrement operations?
  + What is the max number of references?
+ Consequences:
  + Cost is distributed throughout app
    + Usually no need for a GC pause
    + Can sometimes have paues because of destruction storms. One object with many refs to other objects is
    collected so all other objects get collected too
  + No runtime cost
  + Time overhead within app when using objects (but overhead is low)
  + Possible concurrency contention when updating ref count
  + Does not address heap fragmentation
  + Cannot deal with cyclical references
+ Cycles (ouch)
  + Objects with cyclical references never get collected
  + Non-trivial to solve
  
## Mark & Sweep

+ Mark phase: identify (mark) which objects are live
+ Sweep phase: reclaim unmarked (dead) objects
+ Marking:
  + Start with one reference
  + Move through to all other places
  + Where to start?
    + Thread stack
    + Static references
+ Sweeping:
  + Pause
  + Delete everything not in use
+ Key Questions
  + How many threads for GC?
    + 1 with both mark & sweep
    + 2 with 1 for mark and 1 for sweep
    + Multiple threads for each
  + How big is the heap? (Big heap, long sweep)
+ Consequences
  + Overhead for mark
  + Entire heap must be referencable
  + Mark & Sweep cost increase with heap size
  
## Mark & Compact

+ Mark phase: identify (mark) live objects
+ Compact phase: rearrange the heap to reduce fragmentation
+ Key Questions
  + Do I need to compact (how fragmented)?
  + Concurrency: how many threads?
  + Object references: can objects move? (necessary for compaction)
+ Consequences:
  + Overhead for mark
  + Faster allocation
  + Less fragmentation so much better memory usage
  + Compaction costs (pauses)
  + Long-lived objects move a lot (ouch)
  + May need multiple passes

## Copying

+ AKA arena collector
+ Overview:
  + Split memory into a FROM space and a TO space
  + Start allocating in FROM space and leave TO space alone
  + When FROM space is full, run a mark pass
  + Copy live objects FROM to TO
  + Then, deallocate all of FROM
  + Lather rinse repeat
+ Why:
  + Fast allocation
  + Fast reclamation
+ Big Question
  + How many spaces?
  + Concurrency?
  + Can objects move?
+ Consequences
  + Fast allocation
  + No fragmentation
  + Lose half of the heap
  + Less heap, more GC passes
  + Large copying costs

## Generational: A Hybrid Approach

+  Core assumptions
  + Large heaps with many live objects takke a long time to examine
  + Most objects are very short lived
  + Objects allocated together tend to live and die together
+ Overview
  + Break heap into parts (generations)
  + Promote objects into older generations during mark phases
  + Then what's left is garbage
+ Consequences
  + Fast(er)
  + More overhead
  + Older objects may not be collected
  + Programs which don't follow assumptions won't work well
+ Finalizers
  + Some objects need to clean themselves up
  + Memory is handled automatically
  + But other resources are not (e.g. file handles, sockets)
  + Don't do this:
    + Nondeterministic
    + Not garaunteed to execute at all
    + Potentially resurrect objects

## CLI Memory Management

+ Auomatically managed heap
+ Here's what the spec says:
  + Not much
  + GC could be there, but not mandated
  + Does garauntee that managed objects won't be overwritten or collected?
  + Rest is "implementation detail"
+ Finalize
  + `virtual` method of `System.Object`
  + By default, does nothing
  + If not there, not placed in finalize queue
  + In in there, placed in queue, maybe finalized at some point (or maybe not)
  + Intended for non-memory resources
  + Never (almost never) use this --> just use `IDisposable`
+ But not that finalizers are part of the spec
+ Disposing should usually suppress finalization

## CLR on windows

+ Memory management details for Windows .NET runtime
+ Windows .NET CLR GC Principles:
  + GC should occur frequently enough to keep heap usage low
  + GC should be infrequent enough to minimize overhead
  + GC should be productive (each cycle should reclaim significant memory)
  + Each GC cycle shold be first
  + Managed code developrs shouldn't need to know about GC details
+ CLR GC Depends on the CLR being used:
  + Workstation runtime: one managed heap
  + Server runtime: one managed heap per CPU
+ Both use:
  + 3 generation GC
  + Mark-sweep heap for large objects (not compacted!!)
+ A few other heaps for internal use:
  + JIT-compiler heap
  + CLR Loader heap
+ Generations: Gen 0, Gen1, Gen2
+ CLR self-tunes size of generations on the fly
+ Each pass:
  
  1) Mark phase
  2) Plan compaction
  3) Relocation
  4) Compact
  5) Sweep
+ Compiler info also helps inform and tune GC
