# Log HTTP Requests In Express Using Pino

__Category: Nodejs__

HTTP requests can be logged in Express using Pino, Log4js, Morgan, Winston, or Bunyan. This example will setup a logger using Pino (HTTP version).

Install the package dependency:

```shell
yarn add pino-http
```

Create a logger using `pino-http` in your Express controller:

```javascript
const app = require('express')();
const logger = require('pino-http')();

app.use(pino);

app.get('/', function (req, res) {
  logger.info(req, res);
  res.send('Hello world!');
})

app.listen(3000)
```

Send a request using curl or Postman to http://localhost:3000/

Sample console output from the logger in Nodejs (pretty printed here for readability):

```json
{
  "level": 30,
  "time": 1664866585645,
  "pid": 2115,
  "hostname": "Bobs-MacBook-Pro.local",
  "req": {
    "id": 1,
    "method": "GET",
    "url": "/cars",
    "query": {},
    "params": {},
    "headers": {
      "user-agent": "PostmanRuntime/7.29.2",
      "accept": "*/*",
      "cache-control": "no-cache",
      "postman-token": "ada67f28-4a85-4f20-add3-4f63bd627370",
      "host": "localhost:3000",
      "accept-encoding": "gzip, deflate, br",
      "connection": "keep-alive"
    },
    "remoteAddress": "::1",
    "remotePort": 59886
  },
  "res": {
    "statusCode": 200,
    "headers": {
      "x-powered-by": "Express",
      "content-type": "application/json; charset=utf-8",
      "content-length": "193",
      "etag": "W/\"c1-nL139Lw9kWK1xNv9F5Ggp4UaF3Q\""
    }
  },
  "responseTime": 7,
  "msg": "request completed"
}
```

See [Pino with Express](https://github.com/pinojs/pino/blob/master/docs/web.md#express) for more details.
