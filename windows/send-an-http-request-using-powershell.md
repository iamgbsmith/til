# Send An HTTP Request Using PowerShell

__Category: Windows__

You can send an HTTP request from PowerShell using the `Invoke-WebRequest` command. 

By default, HTTP GET requests will return the content and metadata such as response headers, content length, status code and description. Fields that are longer than a certain amount of characters will be truncated with a `...` symbol however these can be obtained by selecting the field and expanding it.

For example, the following will display all fields for an HTTP response: 

```command
Invoke-WebRequest -Uri https://tradestie.com/api/v1/apps/reddit"
```

If you want to only show the content, select the `Content` field as follows:

```command
Invoke-WebRequest -Uri https://tradestie.com/api/v1/apps/reddit | Select-Object -Expand Content
```

Alternatively, you can abbreviate this as follows:

```command
(Invoke-WebRequest https://tradestie.com/api/v1/apps/reddit).Content
```
