# [C# 7.0: First Look](https://www.lynda.com/C-tutorials/C-7-First-Look/555879-2.html)

## Literals and Separators

+ Binary Literals
  + Already had hex literals: `0x`
  + Now have binary literals: `0b`
+ Digit Separators
  + Underscore separators in numeric literals: `int separated = 1_000_000;`
  + Helpful for binary
+ Local Functions
  + Kind of like JS
  + Functions defined in local scope will be local
  + Not sure about these motivating examples though
  
## Tuples

+ Already in C# prior to 7.0:
  + Reference tuples, which are a static, generic `Tuple` class
  + Reference type
  + Immutable after creation
  + Limited to length 8 with ability to (painfully extend) by using another `Tuple` as 8th parameter
  + Looks like:
  
```csharp
var tuple = new Tuple<string, string>("First string.", "Second string.");
var first = tuple.Item1;
var second = tuple.Item2;
```

+ And here's what's new:
  + Value tuple
  + Mutable
  + Tuple literals
  + Looks like:
  
```csharp
var tuple = ("first string", "second string");
var first = tuple.Item1;
var second = tuple.Item2;
```

  + Can also name tuple items:

```csharp
var tuple = ( name: "Joe", age: 5);
var name = tuple.name;
var age = tuple.age;
```

## Deconstructors

+ With value tuples:

```csharp
var (name, address, city, zip) = contact.GetAddressInfo();
```

+  With objects (that implement the appropriate `Deconstructor`s):

```csharp
Person p = new Person("John", "Quincy", "Adams", "Boston", "MA");

// Deconstruct the person object.
var (fName, lName, city, state) = p;
```

## Patterns

+ Syntactic elements that check if an object has a certain shape
+ `type` patterns:
  + Looks like:

```csharp
public class Square()

if (shape is Square s)
{
  // Can use s in here as a Square
}
```

  + Can also be used in a `switch`:
  
```csharp
 switch (shape)
    {
        case Square s:
            return s.Side * s.Side;
        case Circle c:
            return c.Radius * c.Radius * Math.PI;
        case Rectangle r:
            return r.Height * r.Length;
        default:
            throw new ArgumentException(
                message: "shape is not a recognized shape",
                paramName: nameof(shape));
    }
```
  + Can also add `when` clauses:
  
```csharp
case Square s when s.Side == 0:
```

+ `const` patterns:

```csharp
const double value = double.NaN;
if (o is value) Console.WriteLine("o is value");
```

## Ref returns:

+ Already have `ref` parameters, which create an alias to a variable
+ Now also have `ref` returns, which again creates an alias to a variable and returns that

## Out Variable Inline Declaration

+ Previously `out` parameters had to be declared and initialized prior to being passed into a function
+ Now, declare variable where it is being passed:

```csharp
CreateName(out string name);
```

## Expression-bodied members

+ 6.0 added expression-bodied function members
+ Now can also do: destructors, finalizers, and constructors
+ Also `throw` expressions:
  + Previously, `throw` had to be a statement
  + So, it couldn't be used in places that required expressions, like with the null coalescing operator
+ Now, can use `throw` wherever an expression is expected:
  + Null coalescing operator
  + Ternary operator
  + Lambda expression
