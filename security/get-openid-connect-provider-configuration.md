# Get OpenID Connect Provider Configuration

__Category: Security__

Openid-configuration is a well-known URI Discovery Mechanism for the Provider Configuration URI and is defined in the OpenID Connect specification. Details include supported scopes and grant types.

You can find details on provider OpenID Connect configuration for an authorization server by going to the url `https://[base-server-url]/.well-known/openid-configuration`

For example, Google configuration at https://accounts.google.com/.well-known/openid-configuration is as follows:

```json
{
 "issuer": "https://accounts.google.com",
 "authorization_endpoint": "https://accounts.google.com/o/oauth2/v2/auth",
 "device_authorization_endpoint": "https://oauth2.googleapis.com/device/code",
 "token_endpoint": "https://oauth2.googleapis.com/token",
 "userinfo_endpoint": "https://openidconnect.googleapis.com/v1/userinfo",
 "revocation_endpoint": "https://oauth2.googleapis.com/revoke",
 "jwks_uri": "https://www.googleapis.com/oauth2/v3/certs",
 "response_types_supported": [
  "code",
  "token",
  "id_token",
  "code token",
  "code id_token",
  "token id_token",
  "code token id_token",
  "none"
 ],
 "subject_types_supported": [
  "public"
 ],
 "id_token_signing_alg_values_supported": [
  "RS256"
 ],
 "scopes_supported": [
  "openid",
  "email",
  "profile"
 ],
 "token_endpoint_auth_methods_supported": [
  "client_secret_post",
  "client_secret_basic"
 ],
 "claims_supported": [
  "aud",
  "email",
  "email_verified",
  "exp",
  "family_name",
  "given_name",
  "iat",
  "iss",
  "locale",
  "name",
  "picture",
  "sub"
 ],
 "code_challenge_methods_supported": [
  "plain",
  "S256"
 ],
 "grant_types_supported": [
  "authorization_code",
  "refresh_token",
  "urn:ietf:params:oauth:grant-type:device_code",
  "urn:ietf:params:oauth:grant-type:jwt-bearer"
 ]
}
```

OpenID configuration metadata from the common authority's OpenID configuration document endpoint on Azure can be accessed at https://login.microsoftonline.com/common/v2.0/.well-known/openid-configuration

See [Openid-configuration](https://ldapwiki.com/wiki/Openid-configuration#:~:text=Openid%2Dconfiguration%20is%20a%20Well,the%20Identity%20Provider%20(IDP).) for more details.