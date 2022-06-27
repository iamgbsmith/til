# Add Polyfill Modules For Webpack

__Category: React__

Prior to webpack version 5, Nodejs polyfills were included by default. 

If you see the following error when starting a React project which uses webpack version 5 or higher, you may need to manually add dependencies to your project.

```shell
Module not found: Error: Can't resolve 'url' in [...]

BREAKING CHANGE: webpack<5 used to include polyfills for node.js core modules by default.
```

Add the missing module (for example, `url`):

```shell
yarn add url
```

Other modules that may need to be added include `assert` and `buffer`.
