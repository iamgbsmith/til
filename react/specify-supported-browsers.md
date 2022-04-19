# Specify Supported Browsers

__Category: React__

You can specify the supported browsers to target for your application in:

 * The `browserslist` section of `package.json`
 * The `.browserslistrc` config file in current or parent directories
 * The `BROWSERSLIST` environment variable

 Entries will control the JavaScript transpilation so that the generated code will be compatible and optimised for the browsers specified. In some cases, the generated code will differ between browsers, particularly for older browsers which use polfyills.

The following will configure supported browsers (using the last 2 versions) for production and development in `package.json`:

```javascript
"browserslist": {
  "production": [
      "last 2 Edge version",
      "last 2 Firefox version",
      "last 2 Chrome version",
      "last 2 Safari version",
      "last 2 Android version",
      "last 2 ChromeAndroid version",
      "last 2 iOS version"
    ],
    "development": [
      "last 2 Edge version",
      "last 2 Firefox version",
      "last 2 Chrome version",
      "last 2 Safari version",
      "last 2 Android version",
      "last 2 ChromeAndroid version",
      "last 2 iOS version"
    ]
}
```

The `production` list will be used when creating a production build by running the `build` script, and the `development` list will be used when running the `start` script.

Other example values that can be specified:

* ```"not IE 11"``` (do not support a specific browser version)
* ```"> 5%"``` (browser versions with more than 5% use as tracked by global usage statistics)
* ```"Firefox > 95"``` (versions newer than 95)
* ```"iOS 14"``` (a specific version)
* ```"last 2 versions"``` (last 2 versions for each browser)
* ```"last 2 iOS major versions"``` (all minor/patch releases of last 2 major versions for a platform/browser)
* ```"Chrome 80 - 90"``` (inclusive range of versions for a browser)

__Note:__ You should periodically update caniuse-lite used in package.json with the following command:

```shell
npx browserslist@latest --update-db
```

This update will bring data about new browsers to polyfills tools like Autoprefixer or Babel and reduce unnecessary polyfills.

The same configuration for `browserslist` can also be used in Angular and Vue.js applications.

See [Browserslist](https://github.com/browserslist/browserslist) for more details.
