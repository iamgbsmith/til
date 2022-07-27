# OAuth 2.1 Grant Types

__Category: Security__

OAuth 2.1 has been amended to improve security and retire legacy grant types from the core spec. 

Key changes are as follows:

* Support for the Resource Owner Password grant type is removed.
* Support for the Implicit grant type is removed.
* OAuth redirect URIs must using exact string matching for comparison.
* Proof Key for Code Exchange (PKCE) is required for clients using the Authorization Code grant type and should be used by mobile apps.
* Refresh tokens for public clients must be cryptographically bound to the client or one-time use.
