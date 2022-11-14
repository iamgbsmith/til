# Upgrade From Web Security Configurer Adaptor

__Category: Spring__

Spring Security 5.7 and higher has deprecated the `WebSecurityConfigurerAdapter` class. 

You must now implement a new configuration using the `EnableWebSecurity` class annotation. This example uses a database user repository.

Create a class called `SecurityConfiguration` as follows:

```java
// Imports deleted for brevity

@Configuration
@EnableWebSecurityy(prePostEnabled = true, securedEnabled = true)
public class SecurityConfiguration {

    /**
     * Requests for URIs will be approved for authenticated users. Fine-grained overrides can be set in
     * controller endpoints.
     */
    @Bean
    public SecurityFilterChain filterChain(HttpSecurity http) throws Exception {
        http.authorizeHttpRequests((authorize) -> authorize.anyRequest().authenticated())
            .httpBasic(withDefaults())
            .formLogin(withDefaults());
        return http.build();
    }

    /**
     * Configure URIs to serve without requiring authentication.
     */
    @Bean
    public WebSecurityCustomizer webSecurityCustomizer() {
        return (web) -> web.ignoring().antMatchers(
                "/error",
                "/css/*",
                "/img/*");
    }

    /**
     * Create an authentication manager which uses a JDBC authentication provider. 
     */
    @Bean
    public AuthenticationManager authenticationManager(HttpSecurity http, DatabaseUserDetailsService userDetailsService)
            throws Exception {
        return http.getSharedObject(AuthenticationManagerBuilder.class)
                .userDetailsService(userDetailsService)
                .passwordEncoder(encoder())
                .and()
                .build();
    }

    /**
     * Password encoder using the default BCrypt encoder.
     */
    @Bean
    public PasswordEncoder encoder() {
        return PasswordEncoderFactories.createDelegatingPasswordEncoder();
    }

}
```

In the above example, user details are loaded from the database using the service below:

```java
// Imports deleted for brevity

@Service
public class DatabaseUserDetailsService implements UserDetailsService {

    @Autowired
    private UserDao userDetailsDao;

    // implementation of loadUserByUsername()

}
```