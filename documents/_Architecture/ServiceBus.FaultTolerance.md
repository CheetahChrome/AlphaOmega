---
title: SB -  Service Bus handling fault tolerance
layout: default
---
# Azure Service Bus handling fault tolerance

Azure Service Bus provides several features to handle fault tolerance and ensure reliable message delivery. Here are some key aspects:

| Subject                            | Explanation                                                                                         |
|------------------------------------|-----------------------------------------------------------------------------------------------------|
| Message Retention                  | Azure Service Bus retains messages for a specific duration, ensuring message availability.         |
| Duplicate Detection                | Service Bus prevents accidental duplication of messages through configurable duplicate detection.  |
| Dead-letter Queue (DLQ)            | Messages that cannot be processed successfully are moved to the Dead-letter queue for inspection. |
| Partitioning                       | Partitioned queues and topics improve throughput and fault tolerance by distributing load.        |
| Availability Zones                 | Premium tier supports deploying Service Bus namespace across Availability Zones for high availability.|
| Auto Forwarding                    | Auto-forwarding rules redirect messages between queues or topics for load balancing or failover.  |
| Message Sessions                   | Message sessions ensure strict ordering or grouping of related messages during processing.         |
| Timeouts and Retry Policies        | Setting timeouts and retry policies allows handling transient failures more effectively.           |
| Transaction Support                | Service Bus supports transactions to ensure messages are either fully processed or not at all.    |
| Backup and Disaster Recovery       | Implement backup and disaster recovery strategies for critical applications' data safety.         |
| Monitoring and Alerting            | Azure Monitor provides insights into performance and health, and alerts can be set up for issues. |
