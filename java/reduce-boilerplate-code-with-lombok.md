# Reduce Boilerplate Code With Lombok

__Category: Java__

Project Lombok is a library that can be used to significantly reduce the amount of boilerplate code written for Java classes. Lombok does this by using annotations added to the Java class for which common methods are needed including getters, setters, constructors and other utility methods.

Add the following dependencies to your Gradle build file.

```shell
compileOnly("org.projectlombok:lombok:${lombokVersion}")
testCompileOnly("org.projectlombok:lombok:${lombokVersion}")
annotationProcessor("org.projectlombok:lombok:${lombokVersion}")
testAnnotationProcessor("org.projectlombok:lombok:${lombokVersion}")
```

Add annotations to your classes as needed.

```java
import lombok.AllArgsConstructor;
import lombok.Builder;
import lombok.EqualsAndHashCode;
import lombok.Getter;
import lombok.NoArgsConstructor;
import lombok.Setter;
import lombok.ToString;

/**
 * Lombok example to auto-generate methods.
 */
@AllArgsConstructor
@NoArgsConstructor
@Builder
@Getter
@Setter
@ToString
@EqualsAndHashCode
public class Automobile {

    private UUID id;

    private String make;

    private String model;

    private BigDecimal price;

    private int cylinderCount;

    private int powerOutput;

}
```

In the above example, annotations specified at the class level will generate all the required methods.

See [Project Lombok](https://projectlombok.org) for more details.
