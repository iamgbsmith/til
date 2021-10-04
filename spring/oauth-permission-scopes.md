# OAuth Permission Scopes
 
 __Category: Spring__
 
OAuth2 Permission Scopes can be enabled in a Spring Resource Server by either using global security configuration or method security in a controller endpoint.
 
Use global security configuration for coarse-grained access controls. Use the method security approach when you need fine-grained access controls.
 
## Using Global Security Configuration
 
```java
@Override
public void configure(HttpSecurity http) throws Exception {
    http
        .authorizeRequests()
        .antMatchers(HttpMethod.GET,"/orders/**").access("#oauth2.hasScope('orders:read')") // Orders and all subresources
        .antMatchers(HttpMethod.POST,"/parts").access("#oauth2.hasScope('parts:write')")
        .anyRequest().authenticated()
        .and().csrf().enable()
        // etc
}
```
 
## Using Method Security
 
```java
@PreAuthorize("#oauth2.hasScope('orders:read')")
@GetMapping("/orders/{id}")
public User getUser(@PathVariable Long id) {
    // get order details
}
 
@PreAuthorize("#oauth2.hasScope('parts:write')")
@PostMapping("/parts")
public String createPart(Part part) {
    // create a part
}
```
 
You will also need to add the following annotation to your `ResourceSecurityConfiguration` implementation to enable pre/post-processing annotations.
 
```java
@EnableGlobalMethodSecurity(prePostEnabled = true)
```
