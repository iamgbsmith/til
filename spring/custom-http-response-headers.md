# Custom HTTP Response Headers

__Category: Spring__

Custom HTTP response headers can be added using a custom servlet filter in the filter chain.

```java
public class CustomHeaderFilter extends GenericFilterBean {

    private static final Logger LOGGER = LoggerFactory.getLogger(CustomHeaderFilter.class);

    @Override
    public void doFilter (ServletRequest request, ServletResponse response, FilterChain chain) throws IOException, ServletException {
        // Add custom header(s)
        response.setHeader("X-Custom-Response-Header", "Some-Value");
        response.setHeader("X-Another-Header", "Another-Value");
        chain.doFilter(request, response);
    }

}
```

Add the custom filter to the servlet filter chain by overriding the `configure` method in your security configuration which extends `WebSecurityConfigurerAdapter`.

```java
@Configuration
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {

    @Override
    protected void configure(HttpSecurity http) throws Exception {
        http.addFilterAfter(new CustomHeaderFilter(), BasicAuthenticationFilter.class);
    }

}
```