# Node Project Setup

__Category: TypeScript__

TypeScript is a typed superset of JavaScript that compiles to plain JavaScript.

The steps here will setup a Node project using yarn and TypeScript then start an Express server on port 3000. The application will watch for changes in TypeScript code to trigger a TypeScript compilation then use nodemon to automatically reload JavaScript code.

```
mkdir my-node-project
```

Run yarn init and follow the prompts
```
yarn init
[follow prompts...]
```

Install TypeScript dev dependency
```
yarn add -D typescript
```

Initialise TypeScript
```
npx tsc --init
```

Install other dev dependencies
```
yarn add -D rimraf nodemon npm-run-all
```

Install Express
```
yarn add -D express @types/express
```

Configure `package.json`
```json
"scripts": {
    "clean": "rimraf dist",
    "build": "tsc",
    "watch:build": "tsc --watch",
    "watch:server": "nodemon './dist/index.js' --watch './dist'",
    "start": "npm-run-all clean build --parallel watch:build watch:server --print-label",
}
```

Configure `tsconfig.json`
```json
{
  "compilerOptions": {
    "target": "es5",       
    "module": "commonjs",  
    "strict": true,
    "esModuleInterop": true, 
    "skipLibCheck": true,                     
    "forceConsistentCasingInFileNames": true,
    "outDir": "./dist",    
  },
  "include": ["./src/**/*"],
  "exclude": [
    "node_modules"
  ]
}
```

Create `src/index.ts` file
```javascript
import express = require('express');

const app: express.Application = express();

app.get('/', function (req, res) {
  res.send('Hello World!');
});

app.listen(3000, function () {
  console.log('Listening on port 3000');
});
```

Start the server
```
yarn start
```

Browse to http://localhost:3000

Any changes you make to source files should be automatically recompiled and visible by refreshing the browser.

See [TypeScript in 5 minutes](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html) for more details.
