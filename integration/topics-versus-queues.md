# Topics Versus Queues

__Category: Integration__

Queues and Topics are different communication patterns used in messaging systems or message brokers such as RabbitMQ, Apache Kafka, and Apache ActiveMQ.

Differences in characteristics are outlined in the following table.

| Characteristic     | Queue                 | Topic                 |
| ------------------ |-----------------------|-----------------------|
| Message delivery   | Messages are sent to a single consumer/subscriber, typically processed in FIFO order. | Messages are sent to multiple subscribers with no guarantees regarding ordering. |
| Message retention  | Messages are retained until they are processed by subscriber. Unprocessed or undeliverable messages are typically moved to a dead letter queue. | Messages are typically retained for a certain duration or until they are consumed by all subscribers. |
| Modality           | Used in a point-to-point scenario where a producer publishes a message for a specific consumer. | Used in a publish-subscribe (pub-sub) scenario where a producer publishes a message to a topic for multiple subscribers. |
| Message priority   | Messages can be assigned different priorities and the subscriber can process higher-priority messages first. | Some implementations allow for topic filtering although message priority is not typically a feature. |
| Use cases          | Used for tasks that need to be performed exactly once with guaranteed delivery such as order processing. | Used in scenarios where multiple consumers are interested in the same data such as broadcasting updates or ingesting sensor data. |

