# Start Node On A Different Port

__Category: Nodejs__

The default port for Node.js is 3000. You can change this with an environment variable or through project configuration.

### Specify using an environment variable

You can retrieve environment variables in Node.js from the process.env object. For example, assume an environment variable called PORT.

```javascript
const PORT = process.env.PORT || 3000;
```

### Specify using project configuration

Install the `dotenv` package.

```console
yarn add dotenv
```

Create a text file called `.env` in the root directory of your project.

Add a value to it:

```text
PORT=8081
```

Add the following line to the top of your entry file to load the .env file:

```javascript
require('dotenv').config();
```

Read the value:

```javascript
// Load the value from the .env file, if it doesn't exist use port 3000
const PORT = process.env.PORT || 3000;
```
