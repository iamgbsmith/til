# Create an Azure APIM Subscription

__Category: Azure__

Azure API Subscriptions provide API consumers with secure access to APIs using subscription keys. Client applications that need to integrate with APIs must supply a valid subscription key in HTTP requests.

To create or modify a subscription for an APIM instance using the Azure Portal:

Open API Management.

Select "Subscriptions".

Press "Add subscription".

Enter the following details:

* Name (this should not contain any spaces, and optionally could be a UUID)
* Display name
* Scope (this should be the minimum level required for the subscription)
* API
* User (leave this blank if desired)

For security reasons, only allow tracing on subscriptions intended for debugging purposes. API will automatically disable tracing 1 hour after it is enabled on a subscription.

Press "Create" and you will see the new subscription in the list. To obtain the API keys, press the elipsis and select "Show/hide keys.

See [Create subscriptions in Azure API Management](https://learn.microsoft.com/en-us/azure/api-management/api-management-howto-create-subscriptions) for more details.
