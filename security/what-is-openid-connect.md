# What Is OpenID Connect

__Category: Security__

OpenID Connect (OIDC) is an identity layer on top of OAuth2 and places emphasis on authentication rather than authorization. It allows clients to verify the identity of a user based on the authentication performed by an Authorization Server. User claims such as name, email, or address may be shared on request. Single-page applications, native, and mobile apps can use OIDC to identify users.

OIDC uses the JSON Web Token (JWT) format and an extra token called the ID Token which encapsulates the identity claims in JSON format. It has an emphasis on authentication rather than authorization.

Scope for OIDC are:

* openid - returns the `sub` claim, which uniquely identifies the user. The `iss`, `aud`, `exp`, `iat`, and `at_hash` claims will also be present.
* profile - returns claims related to basic profile information including `name`, `family_name`, `given_name`, `middle_name`, `nickname`, `picture`, and `updated_at`.
* email - returns `email` and `email_verified` claim which is a boolean indicating whether the email address has been verified by the user.

In OIDC, the term “flow” is used in place of OAuth2 “grant”.

See [OpenID Connect (OIDC)](https://www.fortinet.com/resources/cyberglossary/oidc) for more details.
