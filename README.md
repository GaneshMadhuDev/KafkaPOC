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
