# Show App Linux Service Runtimes

__Category: Azure__

App Service provides Linux hosting and container support. Supported languages include Nodejs, Java (JRE 8 & JRE 11), PHP, Python, .NET Core, and Ruby.

If the runtime required by your application is not supported with built-in images you can deploy a custom container.

You can show the current list of languages and their supported Linux runtimes on App Service with the following command:

```shell
az webapp list-runtimes --os-type linux
```
