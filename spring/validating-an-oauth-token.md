# Validating An OAuth Token

Spring Security OAuth2 provides an endpoint to validate a JWT token. The JWT should be an access token as an **attempt to validate a refresh token will result in "Token was not recognised" being returned.**

`https://server:host/context-root/oauth/check_token?token=`

## Validate a token

Requests to validate a token are a POST request. If authorisation is enabled on the server you will need to supply basic auth credentials.

```
curl -X POST -u a-web-application:insecure-password https://server:host/context-root/oauth/check_token?token=access_token...`
```

Sample response:

```json
{
    "sub": "3a49ba90-281e-348a-8b81-d00cd607e13a",
    "aud": [
        "orbiks"
    ],
    "user_name": "smithr",
    "scope": [
        "read",
        "write"
    ],
    "active": true,
    "exp": 1589458174,
    "authorities": [
        "ROLE_PROJECT_MANAGER"
    ],
    "jti": "3Z1/a16KtsnoysbRJ5iVM41Pf+Y=",
    "client_id": "a-web-application"
}
```
