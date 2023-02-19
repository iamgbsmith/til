# Generate Client Libraries From An OpenAPI Spec

__Category: Integration__

AutoRest is a tool from Microsoft that provides a code generation framework for converting OpenAPI 2.0 and 3.0 specifications into client libraries for the services described by a specification.

Supported languages include C#, PowerShell, Go, Java, Node.js, TypeScript, and Python.

### Install AutoRest

AutoRest can be installed globally using npm or yarn.

```shell
yarn global add autorest
```

Confirm version

```shell
autorest --help
```

### Generating Clients with AutoRest

Assume an OpenAPI spec file called `vehicles.json`.

To generate Python code:

```
autorest --input-file=vehicles.json --python
```

To generate Python code using a namespace and different output folder:

```
autorest --input-file=vehicles.json --python --output-folder=vehiclesdk/v1 --namespace=vehicles.v1
```

### Supported languages

Specify one of the following language targets:

| Language     | Description   |
| ------------ |---------------| 
| --python     | Python        |
| --csharp     | C#            |
| --java       | Java          |
| --typescript | Typescript    |
| --go         | Golang        |
| --powershell | Powershell    |
    
### Updating AutoRest

You can update AutoRest to the latest version with the following command:

```shell
autorest --latest
```

See [AutoRest](https://github.com/Azure/autorest) and [Generating Clients with AutoRest](https://github.com/Azure/autorest/blob/main/docs/generate/readme.md) for more details.
