# Return JSON In An Azure Function

__Category: Azure__

By default, Azure functions will return a content type of `text/plain; charset-utf-8`.

You can return JSON in a function by setting the content type in the response header.

```javascript
const httptrigger: Azurefunction = async function (context: Context, req: HttpRequest) Promise<void> {
    // Configure the response content type 
    context.res.headers - { "Content-Type": "application/json" };

    // Set the status code
    context.res.statusCode = 200;
    context.res.body = { "message": "Hello and good morning" };
    // etc...
};
```
