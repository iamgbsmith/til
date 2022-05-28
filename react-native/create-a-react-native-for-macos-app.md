# Create A React Native For MacOS App

__Category: React Native__

React Native apps can be extended to run as a desktop app on macOS.


Create a React Native app for macOS from the command line as follows:

```shell
npx react-native init MyProject --template react-native-template-typescript
```

You should always use TypeScript as the template for React Native apps because it enhances readability and maintainability of code.

Navigate to the new project directory and install the macOS extension.

```shell
npx react-native-macos-init --overwrite
```

Start the app:

```shell
npx react-native run-macos
```

For convenience, add a script to run your project on macOS in `package.json`:

```json
"scripts": {
  "macos": "npx react-native run-macos",
},
```

Start the app using:

```shell
yarn macos
```

__Note: When your app does not start.__ If you see an error stating "ProjectName has not been registered", open `app.json` and change the value in the `name` field to lowercase.
