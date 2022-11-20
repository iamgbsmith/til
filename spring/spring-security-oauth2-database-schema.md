# Spring Security OAuth2 Database Schema

__Category: Spring__

Spring Security provides support for running an OAuth2 Authorization Server. 

To store OAuth2 client details you need to create the following tables:

* oauth2_authorization
* oauth2_authorization_consent
* oauth2_registered_client

Create a file called `oauth-authorization-schema.sql` as follows:

```sql
/*
IMPORTANT:
    If using PostgreSQL, update ALL columns defined with 'blob' to 'text',
    as PostgreSQL does not support the 'blob' data type.
*/
CREATE TABLE oauth2_authorization (
    id varchar(100) NOT NULL,
    registered_client_id varchar(100) NOT NULL,
    principal_name varchar(200) NOT NULL,
    authorization_grant_type varchar(100) NOT NULL,
    attributes blob DEFAULT NULL,
    state varchar(500) DEFAULT NULL,
    authorization_code_value blob DEFAULT NULL,
    authorization_code_issued_at timestamp DEFAULT NULL,
    authorization_code_expires_at timestamp DEFAULT NULL,
    authorization_code_metadata blob DEFAULT NULL,
    access_token_value blob DEFAULT NULL,
    access_token_issued_at timestamp DEFAULT NULL,
    access_token_expires_at timestamp DEFAULT NULL,
    access_token_metadata blob DEFAULT NULL,
    access_token_type varchar(100) DEFAULT NULL,
    access_token_scopes varchar(1000) DEFAULT NULL,
    oidc_id_token_value blob DEFAULT NULL,
    oidc_id_token_issued_at timestamp DEFAULT NULL,
    oidc_id_token_expires_at timestamp DEFAULT NULL,
    oidc_id_token_metadata blob DEFAULT NULL,
    refresh_token_value blob DEFAULT NULL,
    refresh_token_issued_at timestamp DEFAULT NULL,
    refresh_token_expires_at timestamp DEFAULT NULL,
    refresh_token_metadata blob DEFAULT NULL,
    PRIMARY KEY (id)
);
```

Create a file called `oauth-authorization-consent-schema.sql` as follows:

```sql
CREATE TABLE oauth2_authorization_consent (
    registered_client_id varchar(100) NOT NULL,
    principal_name varchar(200) NOT NULL,
    authorities varchar(1000) NOT NULL,
    PRIMARY KEY (registered_client_id, principal_name)
);
```

Create a file called `oauth2-registered-client.sql` as follows:

```sql
 CREATE TABLE oauth2_registered_client (
     id varchar(100) NOT NULL,
     client_id varchar(100) NOT NULL,
     client_id_issued_at timestamp DEFAULT CURRENT_TIMESTAMP NOT NULL,
     client_secret varchar(200) DEFAULT NULL,
     client_secret_expires_at timestamp DEFAULT NULL,
     client_name varchar(200) NOT NULL,
     client_authentication_methods varchar(1000) NOT NULL,
     authorization_grant_types varchar(1000) NOT NULL,
     redirect_uris varchar(1000) DEFAULT NULL,
     scopes varchar(1000) NOT NULL,
     client_settings varchar(2000) NOT NULL,
     token_settings varchar(2000) NOT NULL,
     PRIMARY KEY (id)
 );
```


The content for these files can be obtained from the dependency `spring-security-oauth2-authorization-server-0.3.0.jar` JAR file. Table definitions exist in the packages `org.springframework.security.oauth2.server.authorization.client` and `org.springframework.security.oauth2.server.authorization`.

Over time, the SQL structure for these tables may change as the version for the JAR is incremented.
