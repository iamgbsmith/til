# Linting In TypeScript

__Category: TypeScript__

[ESLint](https://eslint.org/) is a popular JavaScript linting tool that helps with code quality and is the recommended linter for TypeScript code.

This TIL will setup ESLint and Prettier code formatting for a React project.

Create a `tsconfig.json` file in the project root directory. Add the following contents:

```json
{
  "compilerOptions": {
    "outDir": "dist", // where to put the compiled JS files
    "target": "ES2020", // which level of JS support to target
    "module": "CommonJS", // which system for the program AMD, UMD, System, CommonJS

    // Recommended: Compiler complains about expressions implicitly typed as 'any'
    "noImplicitAny": true, 
  },
  "include": ["src"], // which files to compile
  "exclude": ["node_modules"], // which files to skip
}
```

Add ESLint and Prettier dependencies:

```shell
yarn add -D eslint typescript @typescript-eslint/parser @typescript-eslint/eslint-plugin prettier
```

Create an ESLint configuration file called `.eslintrc` in the project root directory:

```shell
// .eslintrc
"root": true,
"parser": "@typescript-eslint/parser",
"plugins": [
  "@typescript-eslint"
],
"extends": [
  "eslint:recommended",
  "plugin:@typescript-eslint/eslint-recommended",
  "plugin:@typescript-eslint/recommended"
],
"rules": {
  "@typescript-eslint/no-unused-vars": "error",
  // to enforce using type for object type definitions, can be type or interface 
  "@typescript-eslint/consistent-type-definitions": ["error", "type"], 
  "no-console": "warn",
  "no-loops/no-loops": "error" 
},
"env": {
  "browser": true,
  "es2021": true
}
```

When using rules, are three modes in eslint: off, warn, and error.

* "off" means 0 (turns the rule off completely)
* "warn" means 1 (turns the rule on but won't make the linter fail)
* "error" means 2 (turns the rule on and will make the linter fail)

Create a file called `.eslintignore` in the project root directory which will list the files and directories to ignore when linting:

```shell
# Avoid linting the following directories and files
node_modules
dist
```

In the scripts section for `package.json` add the lint command:

```
"scripts": {  
  "lint": "tsc --noEmit && eslint src/**/*.ts{,x}"
},
```

Create a file called `.prettierrc` for defining code formatting options:

```shell
{
  "semi": true,
  "singleQuote": true,
  "arrowParens": "avoid",
  "trailingComma": "none",
  "printWidth": 120
}
```

In the scripts section for `package.json` add the prettier command:

```
"scripts": {  
  "lint": "tsc --noEmit && eslint src/**/*.ts{,x}",
  "format": "prettier --ignore-path .gitignore --write \"**/*.+(js|ts|json)\""
},
```

If using yarn, run linting with the command:

```shell
yarn lint
```

Or, if using npm, run linting as follows:

```shell
npm run lint
```
