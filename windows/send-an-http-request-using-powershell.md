# Send An HTTP Request Using PowerShell

__Category: Windows__

You can send an HTTP request from PowerShell using the `Invoke-WebRequest` or `iwr` alias command. 

By default, HTTP GET requests will return the content and metadata such as response headers, content length, status code and description. Fields that are longer than a certain amount of characters will be truncated with a `...` symbol however these can be obtained by selecting the field and expanding it.

For example, the following will display all fields for an HTTP response: 

```command
iwr -Uri https://tradestie.com/api/v1/apps/reddit"
```

If you want to only show the content, select the `Content` field as follows:

```command
iwr -Uri https://tradestie.com/api/v1/apps/reddit | Select-Object -Expand Content
```

Alternatively, you can abbreviate this as follows:

```command
(iwr https://tradestie.com/api/v1/apps/reddit).Content
```

Alternatively, use the shorthand method `irm` (Invoke REST Method) which will print out JSON in a tabular format:

```command
irm https://tradestie.com/api/v1/apps/reddit
```
