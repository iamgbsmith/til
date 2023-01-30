# Generate TypeScript Types From An OpenAPI Spec

__Category: Integration__

You can generate TypeScript types from an OpenAPI spec using `openapi-typescript`. 

Generating from a local spec:

```shell
npx openapi-typescript orbiks.yaml --output orbiks.ts
```

Generating from an remote spec:

```shell
npx openapi-typescript https://petstore3.swagger.io/api/v3/openapi.yaml --output petstore.d.ts
```

__Note:__ Before running the tool you must ensure your spec is valid.

See [openapi-typescript](https://github.com/drwpow/openapi-typescript) for more details.
