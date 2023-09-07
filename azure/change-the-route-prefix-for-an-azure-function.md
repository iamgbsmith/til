# Change The Route Prefix For An Azure Function

__Category: Azure__

Azure functions use `/api` as the route prefix (context root) by default. You can either remove this from the path or use an alternative value by editing the `host.json` file for your function.

Edit `host.json` to remove the route prefix from the path:

```json
{
  "version": "2.0"
  //...
  "extensions": {
    "http": {
      "routePrefix": ""
    }
  }
  //..
}
```

Edit `host.json` to use a different route prefix. In the following configuration, `/service` will be used:

```json
{
  "version": "2.0", 
  //...
  "extensions": {
    "http": {
      "routePrefix": "/service"
      }
  }
}
```
