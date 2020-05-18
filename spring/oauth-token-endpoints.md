# OAuth Token Endpoints 

Spring Security OAuth2 provides endpoints for authentication and authorization with OAuth.

| Endpoint              | Functionality   |
| --------------------- |-----------------| 
| `/oauth/authorize`      | The authorization endpoint where a resource owner logs in and grants authorization to the client |
| `/oauth/token`          | Used to obtain an access token or refresh token from the authorization server |
| `/oauth/confirm_access` | User posts approval for grants here                           |
| `/oauth/error`          | Used to render errors in the authorization server             |
| `/oauth/check_token`    | Used by Resource Servers to check an access token or refresh token for validity |
| `/oauth/token_key`      | Exposes the public key used by the authorization server for signing JWT tokens |

Access Tokens and Refresh Tokens in Spring OAuth are in the format of a JSON Web Token (JWT). 

JWTs are an open, industry standard RFC 7519 method for representing claims securely between two parties.

See [JSON Web Tokens](https://jwt.io) for more details.