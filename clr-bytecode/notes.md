# [CLR Bytecode](https://www.lynda.com/Windows-tutorials/CLR-Bytecode/614297-2.html)

## Intermediate Language

+ AKA bytecode AKA IL
+ Language of the CLR

## ILdasm: The .NET Disassembler

+ Utiity that allows developers to examine bytecode
+ Part of each .NET SDK
+ Works on .exe
+ Feed `ildasm` the executable and out pops the IL
+ Cool!

## ILasm: The .NET Assembler

+ ILasm
+ Takes IL and makes it an exe or dll
+ Roundtrip: ILasm <==> ILdasm
+ Also cool!!

## EMAC CLI Spec

+ ECMA-335 defines CLI (common language interface)
+ .NET CLR adheres to ECMA-335

## CLI Bytecode

+ Entirely stack-based (no registers)
+ All locals
+ Parameters live on execution stack
+ Elements are slots (not machine words)
+ All names are fully-resolved and assembly qualified

## Data Types & Directives

+ From spec
+ Some examples of data types:
  + `void`
  + `bool`
  + `string`
  + `char`
  + `float32`
  + etc
+ Some examples of directives:
  + `.assembly extern`: link to another assembly
  + `.assembly`: this assembly
  + `.module`: a module
  + `.namespace`
  + etc
  
## Classes

+ `.class` directive defines a class
+ Various modifiers (interfaces, visibility, abstract, etc)
+ Value types will look different (think structs)
+ `.field` for fields:
  + Again, variety of modifiers
  + Visibility
  + Constants
  + Literals

## Other Directives

+ `.method`
  + Access control
  + names
  + instance
  + etc
  + managed vs unmanaged
  + synchronized
+ `.property`
  + Two directives:
    + `.get`
    + `.set`
  + Indexers are implemented as properties
  
## CLI Opcodes and Operands

+ Everything is stack-based
+ Locals array (abstraction next to the stack)

```
.locals init ([0] class [mscorlib]System.Random.rand, [1] bool V_1)
```

+ Method parameters (happen in the same way as the locals array)
+ Stack manipulation ops: `pop`, `ldloc`, etc
+ Control flow ops:
  + Make decisions based off the top of the stack
  + Ifs, switch, jumps, calls, etc:
  
```
call void [mscorlib] System.Console::WriteLine(string)
```

+ Object operands:
  + `newobj` --> reference objects
  + `initobj` --> value type
  + etc
+ Exception operands
  + `.try`
  + `fault`
  + `finally`
  + etc

## Generics

+ Generics are preserved in metadata (unlike C++ templates which make copies)
+ Preserved in IL (unlike the terrible implementation in Java)
