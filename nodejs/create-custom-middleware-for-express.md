# Create Custom Middleware For Express

__Category: Nodejs__

Express supports the use of custom middleware to run additional processing as part of the HTTP request filter chain sequence. An example of where you might need to use middleware is to validate a JSON Web Token (JWT).

Middleware should be added so that it runs early in the request processing sequence.

Create your middleware:

```javascript
/**
 * Check HTTP request to ensure it contains a valid JWT access token in the Bearer headers.
 * If found, check to see it has not expired. If expired, return HTTP 403, otherwise continue processing.
 */
module.exports = function accessTokenValidator(req, res, next) {
  if (req.headers.authorization && req.headers.authorization.match(/^Bearer (.*)$/)) {
    const token = req.headers.authorizationHeader.substring("Bearer ".length);
    // Pass the JWT to a helper method called decodeJWT (defined somewhere else)
    const expiryTime = decodeJWT(token, 'exp');
    if (Date.now() > expiryTime) {
      res.send(403, "Invalid access token token. The token has expired.");
    } else {
      next();
    }
  } else {
    // No access token, return unauthorized
    res.send(401, "Access token not supplied.");
  }
};
```

Add your custom middleware to Express:

```javascript
const express = require('express');
const accessTokenValidator = require('./middleware/accessTokenValidator');

var app = express();

// Validate access tokens early in the request processing sequence
app.use(accessTokenValidator);

// Serve content from the specified base dir
app.use(express.static('/path/to/files'));

app.listen(3000, () => {
  console.log('Server running on port 3000');
});
```
