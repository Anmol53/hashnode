---
title: "Apache Kafka Brief Board"
seoTitle: "Master Apache Kafka: Key Concepts, Features, and Best Practices for Yo"
seoDescription: "Refresh your Apache Kafka knowledge with this concise guide. Covering architecture, components, features, and commands to help you ace your interview."
datePublished: Wed Jan 08 2025 19:58:32 GMT+0000 (Coordinated Universal Time)
cuid: cm5obo5is000109mncrre9hv3
slug: kafka
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1736365439208/b0c6b658-3dc6-4eb2-bfb1-897df8d12d28.png
tags: interview, streaming, kafka

---

## **Overview**

* **Kafka**: A distributed event-streaming platform designed for high-throughput and fault-tolerant data pipelines and real-time data processing.
    
* **Core Concepts**:
    
    * **Producer**: Sends records to Kafka topics.
        
    * **Consumer**: Reads records from Kafka topics.
        
    * **Broker**: A Kafka server managing storage and distribution.
        
    * **Topic**: Logical channels for organizing messages.
        
    * **Partition**: A subdivision of a topic for parallelism.
        
    * **Offset**: Unique identifier for messages in a partition.
        

---

## **Key Components**

1. **Producer**:
    
    * Pushes messages to topics.
        
    * Can specify the partition (or let Kafka auto-assign).
        
    * Provides **acknowledgment modes**:
        
        * `acks=0` (no acknowledgment).
            
        * `acks=1` (leader acknowledgment).
            
        * `acks=all` (all replicas acknowledge).
            
2. **Consumer**:
    
    * Pulls messages from topics.
        
    * Tracks the **offset** for consumed messages (via Kafka or custom storage).
        
    * Belongs to a **Consumer Group**:
        
        * Enables load balancing among consumers.
            
        * Each partition is consumed by only one consumer in a group.
            
3. **Broker**:
    
    * Kafka server handling message storage and replication.
        
    * Distributes load and ensures durability.
        
4. **Topic**:
    
    * Organizes messages logically.
        
    * **Replication Factor**: Number of copies of the topic across brokers (fault-tolerance).
        
    * **Partitions**:
        
        * Enable parallelism.
            
        * Each partition is assigned to a broker.
            
5. **ZooKeeper** (legacy):
    
    * Manages metadata, leader election, and configuration.
        
    * Being replaced by **Kafka Raft (KRaft)** in newer versions.
        

---

## **Core Features**

* **High Throughput & Scalability**: Handles millions of messages per second.
    
* **Durability**: Messages are written to disk and replicated.
    
* **Fault-Tolerance**: Replication ensures data availability even if brokers fail.
    
* **Log-Based Storage**:
    
    * Messages are appended to the end of a log.
        
    * Retention policies: time-based or size-based.
        

---

## **Key APIs**

1. **Producer API**: Publishes messages to topics.
    
2. **Consumer API**: Subscribes to topics and processes messages.
    
3. **Streams API**: Builds stream-processing applications.
    
4. **Connect API**: Connects Kafka to external systems (e.g., databases, file systems).
    

---

## **Common Patterns**

* **Pub-Sub**:
    
    * Producers publish messages.
        
    * Multiple consumers can subscribe.
        
* **Message Queue**:
    
    * Each message is processed by one consumer in a group.
        
* **Event Sourcing**:
    
    * Log all state changes as events for replayability.
        

---

## **Important Configurations**

* **Producer**:
    
    * `batch.size`: Controls batch size for improved throughput.
        
    * `linger.ms`: Delays sending messages to increase batching.
        
* **Consumer**:
    
    * `auto.offset.reset`: Behavior for unreadable offsets (`latest`/`earliest`).
        
    * `enable.auto.commit`: Automatically commits offsets (default: true).
        

---

## **Monitoring Metrics**

* **Lag**: Difference between produced and consumed offsets.
    
* **ISR (In-Sync Replicas)**: Brokers with the latest partition data.
    
* **Under-replicated Partitions**: Partitions with fewer replicas than the replication factor.
    

---

## **Common Commands**

* List topics: `kafka-topics.sh --list --bootstrap-server <broker>`
    
* Create a topic:
    
    ```bash
    kafka-topics.sh --create --topic <topic_name> \
      --bootstrap-server <broker> \
      --partitions <num> --replication-factor <num>
    ```
    
* Produce messages: `kafka-console-producer.sh --topic <topic> --bootstrap-server <broker>`
    
* Consume messages: `kafka-console-consumer.sh --topic <topic> --bootstrap-server <broker>`
    

---

## **Pros & Use Cases**

* **Pros**:
    
    * High performance and scalability.
        
    * Fault tolerance and durability.
        
    * Flexible APIs for multiple use cases.
        
* **Use Cases**:
    
    * Real-time analytics.
        
    * Event sourcing.
        
    * Log aggregation.
        
    * Data integration pipelines.
        

---

## **Gotchas**

* Ensure proper replication for fault tolerance.
    
* Monitor consumer lag to avoid data processing delays.
    
* Balance partitioning for optimal resource utilization.