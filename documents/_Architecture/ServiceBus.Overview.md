---
title: SB - Service Bus Overview
layout: default
---
# Azure Service Bus Overview

| Topic | Overview |
|-|-|
| What is Azure Service Bus? | Azure Service Bus is a cloud-based messaging service provided by Microsoft Azure. It enables reliable and asynchronous communication between applications and services. Service Bus supports two main communication patterns: queuing and publish/subscribe messaging. |
| Messaging Patterns | Service Bus supports two main messaging patterns: 1) **Queue-based Messaging**: In this pattern, messages are sent to a queue and then processed by a single receiver. This ensures reliable and ordered message processing. 2) **Topic-based Messaging**: In this pattern, messages are published to a topic, and multiple subscribers can receive copies of the messages based on their subscriptions. Topic-based messaging allows for decoupling of publishers and subscribers. |
| Message Entities | Service Bus provides two types of message entities: 1) **Queues**: Queues store and forward messages to be processed by a single receiver. Messages are delivered in the order they were sent and processed by the receiver at their own pace. 2) **Topics**: Topics facilitate publish/subscribe messaging. Messages are sent to a topic and then delivered to multiple subscribers based on their subscriptions. Subscribers can filter messages based on defined properties. |
| Features | Azure Service Bus offers several key features: 1) **Message Sessions**: This feature allows grouping related messages together, ensuring they are processed by the same receiver and maintaining order. 2) **Duplicate Detection**: Service Bus can detect and remove duplicate messages based on a configurable time window. 3) **Dead-letter Queue (DLQ)**: Messages that cannot be processed are moved to the DLQ for inspection. 4) **Auto Forwarding**: Messages can be automatically forwarded from one entity to another for load balancing or failover scenarios. |
| Reliability and Fault Tolerance | Service Bus ensures reliable message delivery through features such as message retention and duplicate detection. It supports partitioned entities to improve scalability and fault tolerance. Additionally, the Premium tier offers support for Availability Zones, enabling high availability across multiple zones. |
| Protocol Support | Azure Service Bus supports multiple protocols for communication, including AMQP (Advanced Message Queuing Protocol), HTTPS, and WebSockets, making it accessible from various platforms and devices. |
| Security | Service Bus provides security features such as Shared Access Signatures (SAS) and Azure Active Directory (Azure AD) authentication. These features allow you to control access to the message entities and protect sensitive data. |
| Integration with Other Services | Azure Service Bus seamlessly integrates with other Azure services, including Logic Apps, Functions, and Event Grid, enabling you to build sophisticated event-driven solutions and workflows. |