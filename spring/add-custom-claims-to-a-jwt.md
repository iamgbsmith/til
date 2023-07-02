# Add Custom Claims To A JWT

__Category: Spring__

Spring Authorization Server provides the ability to add custom claims to a JWT access token. 

This example is applicable for projects using Spring Authorization Server 1.0 or higher. It will add a `tenant_id` claim and granted authorities (roles) to the signed JWT.

```java
@Bean
public OAuth2TokenCustomizer<JwtEncodingContext> tokenCustomizer() {
    return context -> {
        Authentication principal = context.getPrincipal();
        if (Objects.equals(context.getTokenType().getValue(), "access_token") && principal instanceof UsernamePasswordAuthenticationToken) {
            Set<String> authorities = principal.getAuthorities().stream()
                    .map(GrantedAuthority::getAuthority).collect(Collectors.toSet());
            User user = (User) principal.getPrincipal();
            context.getClaims().claim("authorities", authorities)
                    .claim("tenant_id", getTenantId());
        }
    };
}
```
