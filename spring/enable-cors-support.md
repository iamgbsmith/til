# Enable CORS Support

__Category: Spring__

Spring Boot can be configured to support Cross-Origin Resource Sharing (CORS) on either individual controller endpoints or controller classes. 

You can also enable at a global level in your `WebConfig` class.

### Add to a specific endpoint

Annotate the required endpoints with `CrossOrigin`.

```java
@RestController
@RequestMapping("/orders")
public class OrderController {

    @CrossOrigin
    @RequestMapping(method = RequestMethod.GET, path = "/{id}")
    public Order retrieve(@PathVariable Long id) {
        // ...
    }

    @RequestMapping(method = RequestMethod.DELETE, path = "/{id}")
    public void remove(@PathVariable Long id) {
        // ...
    }
}
```

### Add to a controller

In this case, CORS will apply to all endpoints in the `RestController` and cached for 30 minutes using the `maxAge` directive.

```java
@CrossOrigin(origins = "http://foobar.com", maxAge = 3600)
@CrossOrigin(origins = "*", allowedHeaders = "*", maxAge = 3600)
@RestController
@RequestMapping("/orders")
public class OrderController {

    @RequestMapping(method = RequestMethod.GET, path = "/{id}")
    public Order retrieve(@PathVariable Long id) {
        // ...
    }

    @RequestMapping(method = RequestMethod.DELETE, path = "/{id}")
    public void remove(@PathVariable Long id) {
        // ...
    }
}
```

### Enable from any origin to any endpoint in the application

Override the `addCorsMappings` method. In this example, it will use a wildcard matching any level of nesting on controller endpoint paths.

```java
@Configuration
@EnableWebMvc
public class WebConfig implements WebMvcConfigurer {

    @Override
    public void addCorsMappings(CorsRegistry registry) {
        registry.addMapping("/**");
    }
}
```

__Note:__ The Access-Control-Max-Age response header indicates how long the results of a preflight request (the information contained in the Access-Control-Allow-Methods and Access-Control-Allow-Headers headers) can be cached for. Set this value in Spring Boot using `maxAge` in seconds. For example: `maxAge=3600`.