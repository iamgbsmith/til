# Set Nodejs Version On Netlify

__Category: Gatsby__

Using an incorrect version of Nodejs in Netlify may result in the following error when performing a build:

```shell
error type-fest@2.5.4: The engine “node” is incompatible with this module. Expected version “>=12.20”. Got “12.18.0”
```

You can set the Nodejs version for Netlify builds in one of two ways: either by specifying the version in `.nvmrc` file in the base directory of your Gatsby site, or by setting `NODE_VERSION` in a Gatsby environment variable. 

See [Node.js and JavaScript](https://docs.netlify.com/configure-builds/manage-dependencies/#node-js-and-javascript) for more information.
