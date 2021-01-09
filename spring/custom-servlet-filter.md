# Custom Servlet Filter

__Category: Spring__

Spring custom servlet filters can be used to intercept HTTP requests and perform actions against those requests or decorate a response. For example, a custom servlet filter could log the request method, URI and remote address then continue the filter chain processing.

```java
public class RequestResponseLoggingFilter extends GenericFilterBean {

    private static final Logger LOGGER = LoggerFactory.getLogger(RequestResponseLoggingFilter.class);

    @Override
    public void doFilter (ServletRequest request, ServletResponse response, FilterChain chain) throws IOException, ServletException {
        HttpServletRequest req = (HttpServletRequest) request;
        HttpServletResponse res = (HttpServletResponse) response;
        LOGGER.info("Logging Request {} : {} from endpoint {}", req.getMethod(), req.getRequestURI(), req.getRemoteAddr());
        chain.doFilter(request, response);
        LOGGER.info("Logging Response :{}", res.getContentType());
    }

}
```

Apply filters in the Web Security Configuration class specifying when to run in the filter chain with `addFilterBefore` or `addFilterAfter`

```java
@Override
protected void configure(final HttpSecurity http) throws Exception {
    RequestResponseLoggingFilter requestResponseLoggingFilter = new RequestResponseLoggingFilter();

    http
        .authorizeRequests()
        .antMatchers("/login", "/actuator/health").permitAll()
        .anyRequest().authenticated()
        .and()
        .addFilterBefore(requestResponseLoggingFilter, UsernamePasswordAuthenticationFilter.class);
        .formLogin().permitAll()
        .and()
        .httpBasic();
}
```
