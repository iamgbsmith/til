# Policies In Azure APIM

__Category: Azure__

Azure API Management Policies let you change the behavior of APIs using a combination of XML and C# code that is run during request and response processing. Policies are a collection of statements that are run sequentially on the request or response of an API.
There are more than 50 policy types that can be configured for use in API processing.

### Policy sections

Azure APIM defines four policy sections:
* `inbound` - Used to inspect an incoming request and run conditional logic based on the payload or headers.
* `backend` - Used to change the request before it is forwarded to a backend service. For example, converting an XML payload to ISON.
* `outbound` - Used to add a header to an outbound request.
* `on-error` - Used to handle errors or changes HTTP response codes depending on the error encountered during processing.

### Policy structure

An example of XML policy structure is as follows:

```xml
<policies>
  <inbound>
    <!-- statements to be applied to the request go here -->
  </inbound>
  <backend>
    <!-- statements to be applied before the request is forwarded to the backend service go here -->
  </backend> 
  <outbound>
    <!-- statements to be applied to the response go here -->
  </outbound> 
  <on-error>
    <!-- statements to be applied if there is an error condition go here -->
  </on-error>
</policies>
```

### Policy scopes

Azure APIM allows policies to be defined at different scopes. The following are from most broad to most narrow:

* Global (all APIs)
* Workspace (all APIs associated with a selected workspace)
* Product (all APIs associated with a selected product)
* API (all operations in an API)
* Operation (single operation in an API)

__Note:__ Policy inheritance and evaluation order in each policy section is configured by placement of the base element.
See [Policies in Azure API Management](https://learn.microsoft.com/en-us/azure/api-management/api-management-howto-policies) for more details.
