# What Is SCIM

__Category: Security__

System for Cross-Domain Identity Management (SCIM) is an API specification for user management to facilitate easier provisioning of users and groups for custom applications from identity management systems. SCIM's intent is to reduce the cost and complexity of user management operations by providing a common user schema, an extension model, and a service protocol.

The SCIM 2.0 specification recommends implementation of at least two endpoints `/Users` and `/Groups` which are used to create, update, and delete objects. The SCIM consists of a predefined schema for common attributes including group name, username, first name, last name, and email.

Some additional endpoints include:

* `/ServiceProviderConfig` - for obtaining the service provider's configuration.
* `/ResourceTypes` - used to discover the types of resources available on a SCIM service provider.
* `/Me` - an alias for operations against a resource mapped to an authentication subject.

See [IETF System for Cross-domain Identity Management Protocol](https://datatracker.ietf.org/doc/html/rfc7644) for more details.