# What Is CloudEvents

__Category: Integration__

CloudEvents is a specification from Cloud Native Computing Foundation (CNCF) for describing event data in common formats to provide interoperability across services, platforms, and systems. CloudEvents are transport agnostic (for example: HTTP, MQTT, WebSockets, SMTP, Kafka, AMQP) and can work with various event sources and consumers.

Core attributes for a CloudEvent are:

* `specversion` - the version of the CloudEvents specification being used
* `type` - the type of the event (for example: "user.created" or "order.updated")
* `source` - the URI of the event source
* `subject` - a subject or identifier for the event
* `id` - a unique event identifier
* `time` - UTC timestamp of when the event occurred
* `datacontenttype` - the MIME type for the event data

The following is a sample cloudEvent payload:

```json
{
    "specversion": "1.0.2",
    "type": "com.orbiks.order.updated",
    "source": "https://orbiks.com/orders/",
    "subject": "F-B4ADA4",
    "id": "B287-3165-9144",
    "time": "2023-10-22713:43:009",
    "comexampleextension1": "value",
    "comexampleothervalue": 5,
    "datacontenttype": "application/json",
    "data" : {
        "orderId": "F-B4ADA4",
        "URL": "https://orbiks.com/orders/F-B4ADA4"
    }
}
```

Important considerations:

* Publishers should ensure that events are kept small; not exceed 64KB in size; and avoid embedding large data items in the payload. The event payload should link to data items.
* Sensitive information should not be transmitted in an event payload without being encrypted.

CloudEvents 1.0 is supported by the following hyperscaler products: AWS EventBridge; Azure Event Grid; and Google Cloud Eventarc.

See [CloudEvents](https://cloudevents.io) for more details.
