# Spring Boot Application Profiles

__Category: Spring__

Profiles allow you to specify different configuration values for Spring Boot applications depending on the environment they are being run in. For example: development, testing or production. 

It is assumed that application property or yaml files use the naming convention application-dev.properties or application-dev.yml (where dev could be subsituted for test, prod, or other).

__Tests for an application should be run using a profile appropriate for the environment. Never use a production profile for testing purposes.__
 
Use either of the following approaches for specifying an active profile.

### Command-line argument (JVM Options)

```shell
-Dspring.profiles.active=dev
```
 
### Environment variable

```shell
export SPRING_PROFILES_ACTIVE="prod"
```

### ActiveProfile annotation

Annotate the class used for starting the application or running a test with the profile you wish to use.

```java 
@ActiveProfiles({"test"})
public class BaseTest {
}
``` 

### Property file

Set the active profile in `application.properties` as follows:

```shell
spring.profiles.active=prod
```

See [Set the Active Spring Profiles](https://docs.spring.io/spring-boot/docs/current/reference/html/howto.html#howto-set-active-spring-profiles) for more details.