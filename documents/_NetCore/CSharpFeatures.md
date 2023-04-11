---
title: C# Features
layout: default
--- 
# C# Features
### C# 7 

| Feature| Description | Example |
|-|-|-|
| Tuples | Allows returning multiple values from a method, simplifying code that deals with multiple variables.| ```csharp (int, int) Divide(int dividend, int divisor) { return (dividend / divisor, dividend % divisor); } var result = Divide(10, 3); Console.WriteLine($"Quotient: {result.Item1}, Remainder: {result.Item2}");``` |
 | Pattern matching| A powerful way of matching against data in your code. | ```csharp object obj = "Hello, world!"; if (obj is string str) { Console.WriteLine(str.ToUpper()); }``` |
 | Ref locals and returns| Allows a reference to a local variable to be passed by reference as a method argument, and return a reference from a method. | ```csharp ref int Find(int value, int[] array) { for (int i = 0; i < array.Length; i++) { if (array[i] == value) { return ref array[i]; } } throw new ArgumentException("Value not found in array."); } int[] numbers = { 1, 2, 3, 4, 5 }; ref int refToValue = ref Find(3, numbers); Console.WriteLine(refToValue); refToValue = 42; Console.WriteLine(numbers[2]);``` |
Local functions| Allows defining methods inside other methods. | ```csharp void Foo() { int x = 10; int y = 20; int z = Add(x, y); Console.WriteLine($"The sum of {x} and {y} is {z}"); int Add(int a, int b) { return a + b; } }``` |
Out variables| Allows declaring a variable as an output variable in the argument list of a method, instead of declaring it before the method call. | ```csharp bool TryParse(string s, out int result) { if (int.TryParse(s, out result)) { return true; } else { return false; } } string input = "123"; if (TryParse(input, out int value)) { Console.WriteLine($"Parsed value: {value}"); } else { Console.WriteLine("Could not parse input."); }``` |
Deconstruction| Allows decomposing objects into individual variables, simplifying code that needs to access individual members of an object. | ```csharp public class Person { public string FirstName { get; set; } public string LastName { get; set; } } // Deconstruct a Person object into separate variables var person = new Person { FirstName = "John", LastName = "Doe" }; var (firstName, lastName) = person; Console.WriteLine($"First Name: {firstName}"); Console.WriteLine($"Last Name: {lastName}");``` |

### C# 7.1

| Feature | Description| Example |
|-|-|-|
| Async main method| Allows using the async keyword on the Main method, simplifying asynchronous console applications. | ```csharp class Program { static async Task Main() { Console.WriteLine("Start"); await Task.Delay(1000); Console.WriteLine("End"); } }``` |
Default expressions| Allows setting a default value for a method parameter, simplifying method calls that omit that parameter. | ```csharp void Foo(string name = "John") { Console.WriteLine($"Hello, {name}!"); } Foo(); // Output: Hello, John!``` |
  Inferred tuple element names | Allows specifying tuple element names using `var` and `new` syntax. | ```csharp var person = (firstName: "John", lastName: "Doe"); var fullName = $"{person.firstName} {person.lastName}"; Console.WriteLine(fullName); // Output: John Doe``` |
  Pattern matching for generics | Allows using pattern matching with generics to simplify code. | ```csharp void Foo<T>(T obj) { if (obj is IEnumerable<int> numbers && numbers.Count() > 0) { Console.WriteLine($"First number: {numbers.First()}"); } else { Console.WriteLine("Object is not an IEnumerable<int> with any elements."); } } List<int> list = new List<int> { 1, 2, 3 }; Foo(list); // Output: First number: 1``` |
  Reference semantics with value types | Allows reference semantics to be used with value types, simplifying code that needs to pass value types by reference. | ```csharp ref int GetMax(ref int a, ref int b) { return ref (a >= b ? ref a : ref b); } int x = 1, y = 2; ref int max = ref GetMax(ref x, ref y); Console.WriteLine(max); max = 3; Console.WriteLine(x); // Output: 2, 3``` |


### The C# 7.2

| Feature | Description| Example |
|-|-|-|
|Non-trailing named arguments | Allows specifying named arguments in any order, not just at the end of the argument list.  | ```csharp void Foo(int a, int b, int c) { Console.WriteLine($"{a} {b} {c}"); } Foo(c: 1, a: 2, b: 3); // Output: 2 3 1``` |
|Leading underscores in numeric literals | Allows the use of leading underscores in numeric literals to improve readability.| ```csharp int billion = 1_000_000_000; Console.WriteLine(billion); // Output: 1000000000```|
|private protected access modifier | Allows a member to be accessed by derived types that are declared in the same assembly as the declaring type, and by the declaring type itself or its derived types. | ```csharp class Base { private protected int x; } class Derived : Base { void Foo() { x = 10; } }```|
|Span<T> as a return type  | Allows returning a Span<T> from a method, enabling efficient access to a contiguous range of memory.| ```csharp Span<int> GetSpan(int[] array, int start, int length) { return new Span<int>(array, start, length); } int[] array = { 1, 2, 3, 4, 5 }; Span<int> span = GetSpan(array, 1, 3); Console.WriteLine(string.Join(",", span)); // Output: 2,3,4``` |

### C# 8

| Feature | Description| Example |
|-|-|-|
| Nullable reference types| Allows annotating reference types as nullable or non-nullable, helping to eliminate null reference exceptions at compile-time.| ```csharp #nullable enable string? name = null; if (name != null) { Console.WriteLine(name.Length); } else { Console.WriteLine("Name is null."); }```|
| Switch expressions| A more concise syntax for switch statements, allowing them to be used as expressions.| ```csharp static string GetColor(int value) => value switch { 1 => "Red", 2 => "Green", 3 => "Blue", _ => throw new ArgumentException("Invalid value.") }; Console.WriteLine(GetColor(1)); // Output: Red```|
| Ranges| Allows selecting a range of elements from a collection, using a new syntax for the indexing operator.| ```csharp int[] array = { 1, 2, 3, 4, 5 }; int[] subarray = array[1..4]; Console.WriteLine(string.Join(",", subarray)); // Output: 2,3,4```|
| Indices| Allows accessing elements from the end of a collection using a new syntax for the indexing operator.| ```csharp int[] array = { 1, 2, 3, 4, 5 }; int lastElement = array[^1]; Console.WriteLine(lastElement); // Output: 5```|
| Default interface methods| Allows interfaces to define implementation for their members, reducing the need for abstract classes.| ```csharp interface IFoo { void Bar() { Console.WriteLine("Bar"); } } class MyClass : IFoo { } MyClass obj = new MyClass(); obj.Bar(); // Output: Bar```|
| Using declarations| A more concise syntax for using statements, allowing them to be written as declarations.| ```csharp using var reader = new StreamReader("file.txt"); Console.WriteLine(reader.ReadLine());```|
| Async streams| Allows returning a stream of asynchronous data from a method, using the new IAsyncEnumerable<T> interface.| ```csharp async IAsyncEnumerable<int> GenerateSequenceAsync() { for (int i = 0; i < 20; i++) { await Task.Delay(100); yield return i; } } await foreach (int number in GenerateSequenceAsync()) { Console.WriteLine(number); }```|
| Null-coalescing assignment| Allows assigning a value to a variable if it is null, using a new ??= operator.| ```csharp int? x = null; x ??= 42; Console.WriteLine(x); // Output: 42```|
| Readonly members| Allows fields, properties, and indexers to be declared as readonly, ensuring they can only be assigned a value in the constructor or object initializer.| ```csharp class MyClass { public readonly int x = 42; }```|
| Disposable ref structs| Allows creating disposable structs, making it possible to use them as a resource handle.| ```csharp using var resource = new MyResource();```|
| Stackalloc in nested expressions and statements | Allows using stackalloc in nested expressions and statements, improving performance in some scenarios.| ```csharp void Foo(int length) { Span<int> numbers = stackalloc int[length]; for (int i = 0; i < length; i++) { numbers[i] = i; } Console.WriteLine(string.Join(",", numbers)); } Foo(5); // Output: 0,1,2,3,4```|
| Readonly members with structs| Allows declaring struct members as readonly, preventing them from being modified after initialization.| ```csharp struct Point { public readonly int X; public readonly int Y; public Point(int x, int y) { X = x; Y = y; } }```|
| Null-coalescing assignment with ternary| Allows using the null-coalescing operator with the ternary operator, simplifying code that assigns a value based on a null check.| ```csharp string name = null; string message = name != null ? $"Hello, {name}!" : "Name is null."; Console.WriteLine(message); // Output: Name is null.```|
| Async disposable| Allows defining asynchronous cleanup for disposable objects using the new IAsyncDisposable interface.| ```csharp async Task Foo() { await using var resource = new MyResource(); // Do something with resource... }```|
| Using variables declaration| Allows declaring variables inside using statements, reducing the scope of the variable to the using block.| ```csharp using var streamReader = new StreamReader("file.txt"); string line; while ((line = await streamReader.ReadLineAsync()) != null) { Console.WriteLine(line); }```|
| Static local functions| Allows declaring local functions as static, improving performance by avoiding unnecessary closure allocations.| ```csharp int Foo(int x) { return Add(x, x); static int Add(int a, int b) { return a + b; } } Console.WriteLine(Foo(5)); // Output: 10```|
| Extension everything| Allows defining extension methods for any type, not just classes and interfaces.| ```csharp static class StringExtensions { public static bool IsUpperCase(this string s) { return !string.IsNullOrEmpty(s) && s.ToUpper() == s; } } Console.WriteLine("ABC".IsUpperCase()); // Output: True```|
| Default interface method implementations| Allows interfaces to define default implementations for their members, reducing the need for duplicate code in implementing classes.| ```csharp interface IFoo { void Bar() { Console.WriteLine("Bar"); } } interface IBar : IFoo { } class MyClass : IBar { } MyClass obj = new MyClass(); obj.Bar(); // Output: Bar```|
| Pattern matching enhancements| Adds new patterns to pattern matching, including property patterns, tuple patterns, and more.| ```csharp object obj = "Hello, World!"; if (obj is string { Length: var length }) { Console.WriteLine($"Length: {length}"); }```|


### C# 9

| Feature| Description| Example|
|---------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Init-only properties| Allows properties to be set only during object initialization, using a new init keyword.| ```csharp class Point { public int X { get; init; } public int Y { get; init; } } Point p = new Point { X = 1, Y = 2 }; Console.WriteLine($"{p.X}, {p.Y}"); // Output: 1, 2```|
| Top-level statements| Allows writing code at the top level of a file without needing to define a class or namespace.| ```csharp Console.WriteLine("Hello, World!");```|
| Pattern matching enhancements| Adds new patterns to pattern matching, including simple type patterns, logical patterns, and more.| ```csharp object obj = "Hello, World!"; if (obj is not null and string { Length: 5 }) { Console.WriteLine("Match!"); }```|
| Target-typed new expressions| Allows omitting the type of an object when using the new operator, if it can be inferred from the context.| ```csharp List<int> list = new();```|
| Lambda discard parameters| Allows using a single underscore character as a discard parameter in lambda expressions.| ```csharp Action<int> action = _ => Console.WriteLine("Done!");```|
| Improved target typing| Improves type inference in several scenarios, including ternary expressions and LINQ queries.| ```csharp object obj = true ? new List<int>() : new Dictionary<string, int>();```|
| Relational pattern matching| Adds new operators to pattern matching, allowing comparisons such as greater than, less than, and in-between.| ```csharp int number = 5; if (number is >= 1 and <= 10) { Console.WriteLine("Match!"); }```|
| Logical patterns| Allows combining patterns using logical operators such as and, or, and not.| ```csharp object obj = "Hello, World!"; if (obj is not null and string s and { Length: 5 }) { Console.WriteLine(s); }```|
| Native integers| Adds new integer types that map directly to the hardware's native integer types, allowing for more efficient and predictable code.| ```csharp using System.Runtime.Intrinsics; using System.Runtime.Intrinsics.X86; bool CompareEqual(NativeVector<int> a, NativeVector<int> b) => Sse2.CompareEqual(a, b).AsByte().MoveMask() == 0b1111;``` |
| Function pointers| Adds a new type, the function pointer type, allowing C-style function pointers to be used in C# code.| ```csharp delegate*<int, int> func = &MyFunction; int result = func(5); Console.WriteLine(result);```|

