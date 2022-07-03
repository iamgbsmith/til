# Run Multiple Commands Concurrently

__Category: Nodejs__

You can run multiple commands in a project using `concurrently`. Output for different commands will be shown in the console with a numbered prefix (for example [1] or [2]). 

Install the `concurrently` package:

```shell
yarn add concurrently
```

Update scripts in `package.json` to:

```json
"scripts": {
  "start": "concurrently \"yarn start:client\" \"yarn start:server\"",
  "start:client": "react-scripts start",
  "start:server": "cd .\server && node src/index.js"
}
```

__Note:__ You must surround separate commands with quotes.

See [Concurrently](https://yarnpkg.com/package/concurrently) for more details.
