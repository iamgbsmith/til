# Enable CORS In Azure Static Web Apps

__Category: Azure__

You may need to enable CORS on your Azure static web app if you encounter an error similar to `Access to... has been blocked by CORS policy: No Access-Control-Allow-Origin' header is present on the requested resource` from your web front-end.

Edit `staticwebapp.config.json` to add `globalHeaders` configuration:

```json
"routes" : [
  {
    "route": "/home",
    "allowedRoles": ["authenticated"]
  }
],
"globalHeaders": {
  "Access-Control-Allow-Origin": "*",
  "Access-Control-Allow-Methods": "POST, GET, OPTIONS"
}
```

Inspect the `Access-Control-Allow-Methods` and `Access-Control-Allow-Origin` headers using PowerShell:

```shell
iwr -Uri https://www.microspan.dev | Select-Object -Expand Headers
```

Inspect the headers using curl:

```shell
curl -I -v https://www.microspan.dev
```

* Global headers do not affect API responses. Headers in API responses are preserved and returned to the client.
* Global headers are applied to each response, unless overridden by a route header rule (note: the union of both the headers from the route and the global headers will be returned).
* Headers can be applied at a route level if you do not require them to be global.
