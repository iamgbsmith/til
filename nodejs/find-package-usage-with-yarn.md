# Find Package Usage With Yarn

__Category: Nodejs__

Yarn provides the ability to show why or whether a package is used directly or indirectly by a project.

Use the syntax `yarn why packagename` to show details. For example:

```shell
yarn why acorn
```

Sample output:

```shell
[1/4] 🤔  Why do we have the module "acorn"...?
[2/4] 🚚  Initialising dependency graph...
[3/4] 🔍  Finding dependency...
[4/4] 🚡  Calculating file sizes...
=> Found "acorn@8.8.0"
info Has been hoisted to "acorn"
info Reasons this module exists
   - Hoisted from "react-scripts#webpack#acorn"
   - Hoisted from "react-scripts#terser-webpack-plugin#terser#acorn"
   - Hoisted from "react-scripts#eslint#espree#acorn"
   - Hoisted from "react-scripts#jest#@jest#core#jest-config#jest-environment-jsdom#jsdom#acorn"
=> Found "acorn-node#acorn@7.4.1"
info This module exists because "react-scripts#tailwindcss#detective#acorn-node" depends on it.
=> Found "acorn-globals#acorn@7.4.1"
info This module exists because "react-scripts#jest#@jest#core#jest-config#jest-environment-jsdom#jsdom#acorn-globals" depends on it.
✨  Done in 0.58s.
```
