# Quality Of Service Levels

__Category: MQTT__

MQTT (Message Queue Telemetry Transport) is an ISO standard (ISO/IEC PRF 20922) publish-subscribe based "light weight" messaging protocol for use on top of the TCP/IP protocol. It is intended for connections with remote locations where the network bandwidth is limited and a small code footprint is required.

Quality of Service (QoS) refers to an agreement between the publisher (sender) and subscriber (client/s) regarding the guarantees of delivering a message. When subscribing to a topic, the request should include a numeric QoS value. Clients should choose a level which suits their network reliability.

MQTT defines three QoS levels for message delivery:

### At most once (0)

With level 0, the sender will use a "fire and forget" and does not wait for an ACK from the client. In some situations, messages may be lost so this is best for applications where data loss is not critical.

### At least once (1) 

With level 1, the sender stores the message until it receives a acknowledgement receipt from the client. Since an MQTT message may be published more than once, if an ACK was not received the client application should be capable of handling duplicate incoming messges. This is the most frequently used service level because it balances resource usage with message delivery semantics.

### Exactly once (2) 

With level 2, a message can only be sent once and and ACK must be received from a client. The overhead of level 2 means message transfer takes longer to complete.