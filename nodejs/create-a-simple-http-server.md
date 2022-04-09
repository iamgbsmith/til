# Create A Simple HTTP Server

__Category: Nodejs__

You can create a simple Node.js HTTP server using Express. This example will provide the ability to either serve web content in the /public directory where the application is started from, or serve web content from another directory specified at startup on port 3000.

Create a `package.json` file (excluding dependencies) with the following:

```javascript
{
  "name": "simple-http-server",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
  },
  "scripts": {
    "start": "node app.js"
  }
}
```

Add the latest version of express as a dependency:

```shell
yarn add express
```

Create a directory which will contain your web content:

```shell
mkdir public
```

Create a fille called `app.js` and add the following to it:

```javascript
var express = require('express');
var path = require('path');

var app = express();

// Read arguments passed in at the command line
const args = process.argv;

// If another path is supplied use it, otherwise use default location of /public
let baseDir = args.length === 3 ? args[2] : path.join(__dirname, '/public');

// Serve content from the specified base dir
app.use(express.static(baseDir));

app.listen(3000, () => {
  console.log('Server running on port 3000');
});
```

To load content from the default location of `[app-root]/public`, start the server as follows:

```shell
yarn start
```

To load content from a different loction, start the server passing in a directory location for the web content:


```shell
yarn start /path/to/web/content
```

Access the web site at http://localhost:3000
