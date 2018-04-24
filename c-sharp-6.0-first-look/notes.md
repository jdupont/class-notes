# [C# 6.0 First Look](https://www.lynda.com/C-tutorials/C-6-0-First-Look/397759-2.html)
  
## Expression-level Language Features

  + `nameof`
    + Renaming is a common refactoring
    + But, names in strings can get left behind (e.g., `ArgumentException`s)
    + `nameof` extracts variable name to a string
    + Also has the benefit of compile-time checking
  + String interpolation
    + `$"blahblah"` indicates interpolated string
    + Feels like backtick strings in JS
    + Has formatting options as well
  + Null conditional operator
    + `?.`
    + Returns null if null (short-circuited)
    + Otherwise performs requested operation
    + Also array access: `?[index]`
    + Combines will with null-coalescing operator `??`
    + Can be chained
  + Index initializers:
    + Old approach:
    
```csharp
var oldDict = new Dictionary<string, string>
{
  { "Name", "Rob DeNiro" },
  { "ArtistType", "Mafia" },
  { "FamousQuote", "Insult him a little bit" }
}
```

    + New approach:
    
```csharp
var newDict = new Dictionary<string, string>
{
  ["Name"] = "Rob DeNiro",
  ["ArtistType"] = "Mafia",
  ["FamousQuote"] = "Insult him a little bit"
}
```

    + Can be used for any object supporting an indexer `[]`
  + Overload resolution changes:
    + See [here](https://stackoverflow.com/questions/35114291/c6s-improved-overload-resolution-clarification) for details
    + Now return type and some improved generics information can come into play when needed

## Statement-level Language Features

+ `await` in `catch` and `finally` clauses
  + Logging errors is a common use case
  + Probably need more concurrency experience to understand the full benefits of this
+ Exceptions filters
  + Enter `catch` clauses based on proprties of exceptions: 
  
```csharp
catch (Exception e) when (e.Message == "Catch me")
```
  
  + Cool!

## Member Declaration and Initialization

+ Auto-property initializers
  + Old:
  
```csharp
class Artist
{
  public Artist()
  {
    Name = "Rob";
  }
  
  public string Name { get; set; }
}
```
  
  + New: 
  
```csharp
class Artist
{
  public string Name { get; set; } = "Rob";
}
```
  
+ Getter-only auto-properties
  + Creates read-only backing field
  + Allows fine-grained control of mutability in your objects
  + Just omit the `set`:
  
```csharp
public string Name { get; } = "Readonly value";
```
  
+ Expression-bodied function members
  + Arrow expressions with fat arrow `=>`
  + More concise
+ Static `using`
  + Import static members into scope
  + For example: `using static Console;`
  
  
## New Features in Visual Studio 2015

  + New editing experience
    + Improved syntax IntelliSense
    + Light bulb for suggested syntax clean-up
    + Some inline refactoring (like renaming)
  + Improved debugging
    + Edit code during debugging
    + LINQ expressions in watch/immediate window
