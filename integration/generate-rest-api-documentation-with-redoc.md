# Generate REST API Documentation With Redoc

__Category: Integration__

You can generate REST API documentation in HTML format using Redoc.

The commands here assume you have created a YAML file with an API specification using the OpenAPI format.

### Install Redoc

You can use redoc cli by installing `redoc-cli` globally with npm or yarn. For example: 
  - `npm install --global redoc-cli` 
  - `yarn global add redoc-cli`

### Dynamically serve API documentation 

Use `redoc-cli` to dynamically serve content from an OpenAPI spec in YAML format:

```shell
npx redoc-cli serve -w ./orbiks-openapi-spec.yaml
```

Alternatively, using an OpenAPI spec in JSON format:

```shell
yarn run 
npx redoc-cli serve -w ./orbiks-openapi-spec.json
```

Browse the API spec at: http://127.0.0.1:8080/

### Generate static API documentation

Use `redoc-cli build` to generate static API documentation without any dependencies:

```shell
npx redoc-cli build ./orbiks-openapi-spec.yaml -o orbiks-open-api-spec.html
```

See the following for more details:

* [Redoc](https://github.com/Redocly/redoc)
* [Redoc CLI options](https://github.com/Redocly/redoc/blob/master/cli/README.md)
* [OpenAPI Specification](https://swagger.io/specification/)
