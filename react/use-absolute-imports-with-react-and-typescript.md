# Use Absolute Imports With React And TypeScript

__Category: React__

__Note:__ This TIL assumes you have scaffolded your React project using Vite.

Import statements in React projects typically use relative paths which becomes cumbersome with deeply nested directory structures. To make it easier to import other classes in your project, you should configure absolute imports. 

This needs to be done in two places.

### Add node types to your project

Add the `@types/node` package to your project. 

```shell
yarn add @types/node
```

You will import `path` from this package in vite.config.js.

### Update vite.config

Edit `vite.config.ts` to add aliases. The following sets up aliases for assets, components, features and pages. Add new aliases as necessary.

```javascript
// Add path import
import * as path from 'path'

export default defineConfig({
plugins: [react()],
  resolve: {
    alias: [
      { find: '@assets', replacement: path.resolve(__dirname, 'src/assets') },
      { find: '@components', replacement: path.resolve(__dirname, 'src/components') },
      { find: '@features', replacement: path.resolve(__dirname, 'src/features') },
      { find: '@pages', replacement: path.resolve(__dirname, 'src/pages') },
    ],
  },
  // etc
}
```

### Update tsconfig.json

The TS compiler will need to be told how to resolve paths for aliases. Edit `tsconfig.json` to add the paths.

```javascript
{
  "compilerOptions": {
    "target": "ES2020",
    // etc

    /* Imports */
    "paths": {
      "@assets/*": ["./src/assets/*"],
      "@components/*": ["./src/components/*"],
      "@features/*": ["./src/features/*"],
      "@pages/*": ["./src/pages/*"],
    }

  },
  "include": ["src"],
  "references": [{ "path": "./tsconfig.node.json" }]
}
```

These changes will take affect when you restart your dev server.

### Using aliases

Once you have configured aliases, you can import classes as follows:

```javascript
import Header from '@components/Header'
```
