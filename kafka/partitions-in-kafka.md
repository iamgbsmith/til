# Partitions In Kafka

__Category: Kafka__

Apache Kakfa supports scaling through the use of partitions.

Partitoning splits a single topic log into multiple logs which can be run on different nodes in a Kafka cluster. Storing, writing, and processing of existing messages can then be spread across a cluster improving message throughput and fault tolerance.

* Messages without a key are distributed across partitions for a topic using a round-robin algorithm.
* Messages with a key will be sent to the destination partition based on a computed hash of the key. This ensures that messages with the same key are sent to the same partition, always in order.

Each partition has its own configuration for data retention allowing control of how long messages are retained within that partition. 

Log compaction retains only the latest message for each unique key within a partition.
