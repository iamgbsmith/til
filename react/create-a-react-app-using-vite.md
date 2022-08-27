# Create A React App Using Vite

__Category: React__

### Why should you use Vite?

Vite is a build tool which provides a performant development experience including instant server start, Hot Module Replacement (HMR), and a fast bundler called esbuild. 

Compared to React apps that are scaffolded using CRA, Vite can be up to one third of the size on disk and because it uses the browser-native ES (ECMAScript) modules for linking to JavaScript files it does not need to rebuild the entire bundle after each file change. 

__Note:__ Vite requires Node.js versions 14.18+ or 16+.

### Create a React app
You can create a React app using Vite through the interactive mode or by specifying all options.

Create a React app using interactive mode:

```shell
yarn create vite
```

Create a React app with TypeScript support using Vite as follows:

```shell
yarn create vite my-project --template react-ts
```

Change to the project directory and run:

```shell
cd my-project
yarn
yarn dev
```

Browse to the app on the default Vite port at http://localhost:5173

See [Your first Vite project](https://vitejs.dev/guide/#scaffolding-your-first-vite-project) for more details.
