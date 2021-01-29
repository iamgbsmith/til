# Listen For Authentication Events

__Category: Spring__

Spring Security provides the interface `AuthenticationEventPublisher` which can be used to listen for authentication events such as when a user successfully authenticates or fails to authenticate. For example, you might use the `publishAuthenticationFailure` method to send an alert after three invalid login attempts for a given user account.

Create a class which implements `AuthenticationEventPublisher`:

```java
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import org.springframework.security.authentication.AuthenticationEventPublisher;
import org.springframework.security.core.Authentication;
import org.springframework.security.core.AuthenticationException;

/**
 * Handle success or failure for authentication events.
 */
public class CustomAuthenticationEventPublisher implements AuthenticationEventPublisher {

    private static final Logger LOGGER = LoggerFactory.getLogger(CustomAuthenticationEventPublisher.class);

    public CustomAuthenticationEventPublisher() {
    }

    /**
     * On authentication success.
     */
    @Override
    public void publishAuthenticationSuccess(Authentication authentication) {
        LOGGER.debug("Authentication success for user {}", authentication.getPrincipal());
    }

    /**
     * On authentication failure. 
     * You can confirm the exception is a for bad credentials by inspecting the AuthenticationException.
     */
    @Override
    public void publishAuthenticationFailure(AuthenticationException exception, Authentication authentication) {
        LOGGER.debug("Authentication failure for user {}", authentication.getPrincipal());
    }
}
```

In your SecurityConfiguration class, add the authentication publisher to the authentication manager via the builder.

```java
//...

/**
 * Configures a JDBC user repository as an AuthenticationProvider.
 */
private void configureJDBCAuthenticationProvider(AuthenticationManagerBuilder authBuilder) throws Exception {
    authBuilder.userDetailsService(databaseUserDetailsService).passwordEncoder(
      PasswordEncoderFactories.createDelegatingPasswordEncoder());
    // Add an authentication event publisher to the authentication manager
    authBuilder.authenticationEventPublisher(new CustomAuthenticationEventPublisher());
}

//...
```