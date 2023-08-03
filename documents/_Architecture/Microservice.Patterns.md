---
title: Microservice Pattern
layout: default
---
# Microservice Pattern
 
Here's a summarized overview of some common microservices architecture design patterns:

| Design Pattern | Description |
|-|-|
| Service Decomposition | Divide the application into small, loosely coupled services, each responsible for a specific business capability. |
| API Gateway | Implement a single entry point for clients to interact with multiple microservices. |
| Service Registry and Discovery | Use a central service registry to allow services to register themselves and discover other services dynamically. |
| Load Balancing | Distribute incoming requests across multiple instances of a service to ensure even utilization of resources. |
| Circuit Breaker | Implement a circuit breaker pattern to handle failures and prevent cascading failures across services. |
| Event Sourcing | Store the state of a system as a sequence of events instead of current state snapshots. |
| Command Query Responsibility Segregation (CQRS) | Separate the read and write operations in a system using different models for reading data (queries) and writing data (commands). |
| Saga Pattern | Manage distributed transactions in a microservices environment by breaking them into smaller, isolated steps (sagas). |
| Database per Service | Each microservice has its own dedicated database, ensuring data isolation and independent evolution of services. |
| Choreography and Orchestration | In event-driven systems, choreography involves services collaborating by publishing and reacting to events, while orchestration involves a central component coordinating the interactions between services.|
| Bulkhead Pattern | Isolate failures in one part of the system from affecting others. This involves dividing the application into isolated sections (bulkheads) that have their own resources and dependencies. |
| Polyglot Persistence | Use different data storage technologies depending on the needs of each microservice. |

### Interview Notes

1. Service Decomposition - Breaking each into loosely coupled services per business need
2. Command Query Responsibility Segregation -  Seperate read/write operations within the business needs.
3. Saga pattern where needed - into  smaller work flows. 
4. Durable functions - stateful workflows.
  
