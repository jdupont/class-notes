# [C#: Delegates, Events, and Lambas](https://www.lynda.com/C-tutorials/Welcome/370499/408647-4.html)

## What They Are

+ Delegates:
  + A type that can hold function implementations
  + Type safe (enforced by method signature)
  + Like function pointers or JS callbacks
  + Created by specifying a method signature along with `delegate` type:
  
```csharp
public delegate int MyDelegate(int first, string second)
```
  
  + Assigned by pointing to a function implementation
  + Then called like any other function:
  
```csharp
MyDelegate f = func1;
f(1, "Test");
```
  
+ Events:
  + Asynchronous communication between parts of an application
  + Enables loose coupling and better responsiveness
  + Can be implemented using delegates to capture implementation of event subscribers
  + `event` keyword provides a way to create delegate chains of subscribers:
  
```csharp
// Subscriber
public delegate void CustomEventHandler(int a, string b);
// Event
public event CustomEventHandler customEvent;
// Subscribe to the event
customEvent += new CustomEventHandler(customEventHandler);
// Raise the event
customEvent(1,"a");
```
  
  + Common to create events by deriving from `EventHandler` class from .NET
+ Lambdas:
  + Another way of writing anonymous functions: `MyDelegate f = (first, second) => { return first + second.Length(); }`
  + Useful for brevity

## Anonymous Delegates

+ Declare delegate as shown above

```csharp
public delegate int MyDelegate(int first, string second)
```

+ Then provide implementation of delegate directly inline:

```csharp
MyDelegate f = delegate(int first, string second) {
  // Implementation here
};
```
+ Useful when function is small or not suitable for implementation as class method

## Composable Delegates

+ Create delegate chains
+ Use the `+` and `-`  operators
+ For example:

```csharp
MyDelegate first = func1;
MyDelegate second = func2;
MyDelegate third = func3;
MyDelegate all = func1 + func2 + func3;
```

+ Unhandled delegates skip remainder of chain
+ Results from one delegate in chain can influence another with `ref` parameters
