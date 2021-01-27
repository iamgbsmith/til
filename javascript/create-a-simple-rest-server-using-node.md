# Create A Simple REST Server Using Node

__Category: JavaScript__

You can create a simple Node REST server using minimal code for the purposes of serving JSON. This example assumes you have installed Node.js and Yarn.

Create a `package.json` file with the following:

```javascript
{
  "name": "simple-rest-server",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
    "express": "^4.17.1"
  },
  "scripts": {
    "start": "node app.js"
  }
}
```

Create the application entrypoint file:

```shell
touch app.js
```

In the `app.js` file add the following, with an `app.get()` method for each REST endpoint that returns JSON:

```javascript
var express = require('express');

var app = express();app.listen(3000, () => {
  console.log('Server running on port 3000');
});

app.get('/cars', (req, res, next) => {
  res.json([
    {'car': 'BMW M3 Competition'}, 
    {'car': 'Honda Civic Type R'}, 
    {'car': 'Ford Mustang GT'}, 
    {'car': 'Porsche 911 GT3'}, 
    {'car': 'Volkswagen Golf GTI Clubsport'}
  ]);
});

var app = express();app.listen(3000, () => {
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

```shell
[{"car":"BMW M3 Competition"},{"car":"Honda Civic Type R"},{"car":"Ford Mustang GT"},{"car":"Porsche 911 GT3"},{"car":"Volkswagen Golf GTI Clubsport"}]
```
