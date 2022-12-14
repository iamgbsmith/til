# Commonly Used HTTP Status Codes

__Category: Web__

There are over seventy HTTP status codes with five main classes defined as part of the standard.

### Status code classes

* 1xx codes indicate the request was received and understood
* 2xx codes indicate the request was successfully accepted and understood
* 3xx codes indicate further action needs to be taken to complete the request
* 4xx codes indicate bad syntax or the request cannot be fulfilled
* 5xx codes indicate the server failed to fulfil the request

### Commonly used codes

| HTTP Status Code | Description |
|------------------|-------------|
| 101 - Switching Protocols | The requester has asked to switch protocols. |
| 200 - OK | The request was successfully processed. |
| 201 - Created | The resource was successfully created. |
| 301 - Moved Permanently | Links or records returning this response should be updated.|
| 302 - Found | The resource requested has been temporarily moved to the URL given by the Location header. |
| 304 - Not Modified | The resource has not been modified since it was last requested. |
| 400 - Bad Request | The request was invalid. |
| 401 - Unauthorized | Authentication credentials were missing or incorrect. |
| 403 - Forbidden | The user does not have permission to access the resource. |
| 404 - Not Found | The requested resource could not be found. |
| 405 - Method Not Allowed | The resource was accessed using an unsupported method. |
| 429 - Too Many Requests | The user has sent too many requests in a given amount of time. |
| 500 - Internal Server Error | There was a problem with the server. Try again later. |
| 503 - Service Unavailable |	The service is overloaded or temporarily offline for maintenance. Try again later. |

See [List of HTTP status codes](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes) for more details.