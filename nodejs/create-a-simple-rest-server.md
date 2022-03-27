# Create A Simple REST Server

__Category: Nodejs__

You can create a simple Node.js REST server using minimal code for the purposes of serving JSON. This example assumes you have installed Node.js and Yarn.

Create a `package.json` file with the following:

```javascript
{
  "name": "simple-rest-server",
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

Create the application entrypoint file:

```shell
touch app.js
```

In the `app.js` file add the following, with an `app.get()` method for each REST endpoint that returns JSON:

```javascript
var express = require('express');

var app = express();

app.get('/cars', (req, res, next) => {
  res.json([
    {'id': '1', 'type': 'BMW M3 Competition'}, 
    {'id': '2', 'type': 'Honda Civic Type R'}, 
    {'id': '3', 'type': 'Ford Mustang GT'}, 
    {'id': '4', 'type': 'Porsche 911 GT3'}, 
    {'id': '5', 'type': 'Volkswagen Golf GTI Clubsport'}
  ]);
});

app.listen(3000, () => {
  console.log('Server running on port 3000');
});
```

Start the server:

```shell
yarn start
```

Hit the REST endpoint:

```shell
curl http://localhost:3000/cars
```

Output:

```json
[{"id":"1","type":"BMW M3 Competition"},{"id":"2","type":"Honda Civic Type R"},{"id":"3","type":"Ford Mustang GT"},{"id":"4","type":"Porsche 911 GT3"},{"id":"5","type":"Volkswagen Golf GTI Clubsport"}]
```
