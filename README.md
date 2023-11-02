# KafkaPOC
To demonstrate Kafka use cases
1. kafka was originally built for massive log processing. It retains messages until expiration and lets consumers pull messages at their own pace.

2. Unlike its predecessors, Kafka is more than a message queue, it is an open source event steaming platform for various cases.

3. Log  processing - 

4. Data Streaming in recommendations - 

5. System monitoring and alerting - 

6. CDC change data capture -

7. System migration -

8. Topics

A stream of messages belonging to a particular category is called a topic. Data is stored in topics.

Topics are split into partitions. For each topic, Kafka keeps a mini-mum of one partition. Each such partition contains messages in an immutable ordered sequence. A partition is implemented as a set of segment files of equal sizes.

2	
Partition

Topics may have many partitions, so it can handle an arbitrary amount of data.

3	
Partition offset

Each partitioned message has a unique sequence id called as offset.

4	
Replicas of partition

Replicas are nothing but backups of a partition. Replicas are never read or write data. They are used to prevent data loss.

Brokers

Brokers are simple system responsible for maintaining the pub-lished data. Each broker may have zero or more partitions per topic. Assume, if there are N partitions in a topic and N number of brokers, each broker will have one partition.

Assume if there are N partitions in a topic and more than N brokers (n + m), the first N broker will have one partition and the next M broker will not have any partition for that particular topic.

Assume if there are N partitions in a topic and less than N brokers (n-m), each broker will have one or more partition sharing among them. This scenario is not recommended due to unequal load distri-bution among the broker.

6	
Kafka Cluster

Kafka’s having more than one broker are called as Kafka cluster. A Kafka cluster can be expanded without downtime. These clusters are used to manage the persistence and replication of message data.

7	
Producers

Producers are the publisher of messages to one or more Kafka topics. Producers send data to Kafka brokers. Every time a producer pub-lishes a message to a broker, the broker simply appends the message to the last segment file. Actually, the message will be appended to a partition. Producer can also send messages to a partition of their choice.


Consumers

Consumers read data from brokers. Consumers subscribes to one or more topics and consume published messages by pulling data from the brokers.

9	
Leader

Leader is the node responsible for all reads and writes for the given partition. Every partition has one server acting as a leader.

10	
Follower

Node which follows leader instructions are called as follower. If the leader fails, one of the follower will automatically become the new leader. A follower acts as normal consumer, pulls messages and up-dates its own data store.
