---
title: Gang of Four Design Pattern
layout: default
---

| **Category**   | **Description**                                                                 |
|----------------|---------------------------------------------------------------------------------|
| Creational     | Deal with object creation mechanisms, trying to create objects in a manner suitable to the situation. |
| Structural     | Deal with object composition or the way objects are combined to form larger structures. |
| Behavioral     | Deal with object interaction and responsibility, focusing on how objects communicate and interact with each other. |


| **Pattern Name** | **Category** | **Description** |
|------------------|--------------|-----------------|
| Abstract Factory | Creational   | Provides an interface for creating families of related or dependent objects without specifying their concrete classes. |
| Builder          | Creational   | Separates the construction of a complex object from its representation, allowing the same construction process to create different representations. |
| Factory Method   | Creational   | Defines an interface for creating an object, but lets subclasses alter the type of objects that will be created. |
| Prototype        | Creational   | Specifies the kinds of objects to create using a prototypical instance, and creates new objects by copying this prototype. |
| Singleton        | Creational   | Ensures a class has only one instance and provides a global point of access to it. |
| Adapter          | Structural   | Converts the interface of a class into another interface clients expect, allowing classes to work together that couldn't otherwise because of incompatible interfaces. |
| Bridge           | Structural   | Decouples an abstraction from its implementation so that the two can vary independently. |
| Composite        | Structural   | Composes objects into tree structures to represent part-whole hierarchies, allowing clients to treat individual objects and compositions of objects uniformly. |
| Decorator        | Structural   | Attaches additional responsibilities to an object dynamically, providing a flexible alternative to subclassing for extending functionality. |
| Facade           | Structural   | Provides a unified interface to a set of interfaces in a subsystem, making the subsystem easier to use. |
| Flyweight        | Structural   | Uses sharing to support large numbers of fine-grained objects efficiently. |
| Proxy            | Structural   | Provides a surrogate or placeholder for another object to control access to it. |
| Chain of Responsibility | Behavioral | Avoids coupling the sender of a request to its receiver by giving more than one object a chance to handle the request. |
| Command          | Behavioral   | Encapsulates a request as an object, thereby allowing for parameterization of clients with queues, requests, and operations. |
| Interpreter      | Behavioral   | Given a language, defines a representation for its grammar along with an interpreter that uses the representation to interpret sentences in the language. |
| Iterator         | Behavioral   | Provides a way to access the elements of an aggregate object sequentially without exposing its underlying representation. |
| Mediator         | Behavioral   | Defines an object that encapsulates how a set of objects interact, promoting loose coupling by keeping objects from referring to each other explicitly. |
| Memento          | Behavioral   | Without violating encapsulation, captures and externalizes an object's internal state so that the object can be restored to this state later. |
| Observer         | Behavioral   | Defines a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically. |
| State            | Behavioral   | Allows an object to alter its behavior when its internal state changes, making the object appear to change its class. |
| Strategy         | Behavioral   | Defines a family of algorithms, encapsulates each one, and makes them interchangeable, allowing the algorithm to vary independently from clients that use it. |
| Template Method  | Behavioral   | Defines the skeleton of an algorithm in an operation, deferring some steps to subclasses, allowing them to redefine certain steps without changing the algorithm's structure. |
| Visitor          | Behavioral   | Represents an operation to be performed on the elements of an object structure, allowing new operations to be defined without changing the classes of the elements on which it operates. |


| **SOLID Principle** | **Description** | **Related GoF Patterns** |
|---------------------|-----------------|--------------------------|
| Single Responsibility Principle (SRP) | A class should have only one reason to change, meaning it should have only one job or responsibility. | None directly, but promotes cohesion and separation of concerns. |
| Open/Closed Principle (OCP) | Software entities should be open for extension but closed for modification. | Decorator, Strategy, Observer |
| Liskov Substitution Principle (LSP) | Objects of a superclass should be replaceable with objects of a subclass without affecting the correctness of the program. | None directly, but promotes proper inheritance. |
| Interface Segregation Principle (ISP) | Clients should not be forced to depend on interfaces they do not use. | None directly, but promotes the use of multiple, specific interfaces. |
| Dependency Inversion Principle (DIP) | High-level modules should not depend on low-level modules. Both should depend on abstractions. | Abstract Factory, Factory Method, Dependency Injection |
