# Validating An OAuth Token 

Spring Security OAuth2 provides an endpoint to validate a JWT token. The JWT should be an access token as an __attempt to validate a refresh token will result in "Token was not recognised" being returned.__

`https://server:host/authorization-service/oauth/check_token?token=`

## Validate a token

```
curl https://server:host/authorization-service/oauth/check_token?
token=eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJhdWQiOlsiYXVyYSJdLCJ1c2VyX25hbWUiOiJTTUlUSFIiLCJzY29wZSI6WyJyZWFkIiwid3JpdGUiXSwiaXNzIjoiY29tcmFkIiwiZXhwIjoxNTg5NDU4MTc0LCJhdXRob3JpdGllcyI6WyJST0xFX0NPTlNVTFQiLCJST0xFX1BSRUFVVEhfVVNFUiIsIlJPTEVfU1UiLCJST0xFX1ZFUklGSUNBVElPTiJdLCJqdGkiOiIwNDc3MjY1Yi0wMGFmLTRkN2YtODA2YS02MTJmZThkMzE0YWQiLCJjbGllbnRfaWQiOiJ3ZWItYXBwLWNvbXBsZXRlbHktdHJ1c3RlZCJ9.aFE-GuZ5IFEdIeNWjXxy5hfvmsTYk6RBVcP0_pSlqXzdXc7EiT-eTEOwxphYswlLf8D-HfR8rgeT5ZCJ41WbTzZkHviQBpZ1bRQwUq4z2qy6FbgsN-uvMKldVrR1PjRVIF54-K5wjfOLe33FYcv3dQW3dY6SXEZe8FiN22aYNOckl9ecKtURNGa7ybvGuPHn8Y7WusNwFfKvhkM4M7DeCs8CwyPocGt4AZ071q4qYHRiW44xADL0VxMkirYJI61jxWOZL20gDmUO0kX0R9mDw2ivCjDvTfQXeJOdAXSi-miCR5Zv6Z07kHlRqkHfGCAIcyzLAg79Ng0mPcS62-gRIw`
```

Sample response:

```json
{"aud":["aura"],"user_name":"SMITHR","scope":["read","write"],"iss":"microspan","active":true,"exp":1589458174,"authorities":["ROLE_PROJECT_MANAGER","ROLE_ANALYST"],"jti":"0477265b-00af-4d7f-806a-612fe8d314ad","client_id":"a-web-application"}
```

