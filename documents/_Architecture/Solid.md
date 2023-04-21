---
title: Solid
layout: default
---
# Solid (Book, Shape, Bird, Printer, Delivery)



| Topic | Example | Relies On |Explanation |
|-------|- |------------|
| Single Responsibility Principle (SRP) | Book | Class | A class should have only one reason to change. |
| Open/Closed Principle (OCP) | Shape | Abstract Base Class | A class should be open for extension but closed for modification. |
| Liskov Substitution Principle (LSP) | Bird | Exception| Subtypes should be substitutable for their base types. |
| Interface Segregation Principle (ISP) | Printer | Interfaces | Clients should not be forced to depend on methods they do not use. |
| Dependency Inversion Principle (DIP) | Delivery | Interface - Data Factory | High-level modules should not depend on low-level modules. Both should depend on abstractions. |

## Single Responsibility Principle

```C#  
//  to hold information about a book and provice a method
//  to get a string representation of that information.
public class Book ?? 
{
    public string Title { get; set; }
    public string Author { get; set; }
    public int Year { get; set; }
    public int Pages { get; set; }

    public string GetBookInfo() 
       => $"{Title} by {Author}, {Year} ({Pages} pages)";
    
}

```

## Open Closed Principle
  
```C#  
    // Open for extension by allowing derived classes like
    // Rectangle and Square to define
    // their own implementation of the Area method. 
    public abstract class Shape {
        public abstract double Area();
    }

    public class Rectangle : Shape {
        public double Width { get; set; }
        public double Height { get; set; }

        public override double Area() 
            => Width * Height;
    }

    public class Square : Shape {
        public double Side { get; set; }

        public override double Area() 
            => Side * Side;
    }

    // Closed for modification since it does not need to be modified to
    // support new shapes. It simply accepts an array of Shape objects
    // and calculates the total area using the Area method of each shape,
    // regardless of its type. New shapes can be added without modifying
    // the existing code, making it easy to extend the functionality of the application.
    public class AreaCalculator {
        public double TotalArea(Shape[] shapes) 
            => shapes.Sum(s => s.Area());
    }
``` 

## Liskov Substitution Principle 

```C#
// Defines a virtual method Fly that returns a string
// describing how the bird is flying. 
public abstract class Bird {
    public string Name { get; set; }

    public virtual string Fly() 
        => $"{Name} is flying";
}

// Finch is a sub type of bird and can fly
// Says yes to Liskov for it is a valid subtype
public class Finch : Bird {
    public override string Fly()
           => "Flutters away";
}

// Ostrich is a subytype of bird but cannot fly. 
// Usage breaks the Liskov principle
public class Ostrich : Bird {
    public override string Fly() 
        => throw new NotImplementedException("Ostriches cannot fly");
}

public class BirdShow {
    public string Perform(Bird bird) => bird.Fly();
}
```

## Interface Segregation Principle  

```C#  
// Defines a method Print 
public interface IPrinter { void Print(string document); }

// Defines a method Scan
public interface IScanner { void Scan(string document); }

// Implements both interfaces since it can print and scan documents.
public class Photocopier : IPrinter, IScanner {
    public void Print(string document) => Console.WriteLine($"Printing {document}");

    public void Scan(string document) => Console.WriteLine($"Scanning {document}");
}


// However, a client that only needs to print documents should not be forced
// to depend on the Scan method.To avoid this, the MultiFunctionMachine class
// is introduced, which takes separate instances of an IPrinter and an IScanner
// as constructor arguments.This allows clients to use only the methods they
// need without depending on unnecessary methods. This makes the code more
// modular and flexible, and it also prevents changes to one interface from
// affecting clients that depend on another interface.
public class MultiFunctionMachine : IPrinter, IScanner {
    private IPrinter _printer;
    private IScanner _scanner;

    public MultiFunctionMachine(IPrinter printer, IScanner scanner) 
        => (_printer, _scanner) = (printer, scanner);

    public void Print(string document) => _printer.Print(document);
    public void Scan(string document) => _scanner.Scan(document);
}
```

## Dependancy Inversion Principle

```C#
// Defined delivery operation named ship.
public interface IDelivery { void Ship();}

// Distinct version of ship
public class AirDelivery : IDelivery {
    public void Ship() => Console.WriteLine("Air delivery");
}

// Distinct version of ship
public class LandDelivery : IDelivery {
    public void Ship() => Console.WriteLine("Land delivery");
}


// Depends on the IDelivery interface, not on the concrete classes
// that implement this interface. This allows the Order class to
// work with any delivery class that implements the IDelivery
// interface, without knowing the details of how the delivery is
// actually performed. This design allows for greater flexibility
// and extensibility, as new delivery classes can be added without
// modifying the existing code.
public class Order {
    private IDelivery _delivery;

    public Order(IDelivery delivery) => _delivery = delivery;

    public void Ship() => _delivery.Ship();
}
```

