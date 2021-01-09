# Add JAXB Dependencies

__Category: Java__

In Java versions higher than Java 8, JAXB dependencies for parsing JSON are no longer contained in the JDK/JRE. You must manually add them as a dependency to your project.

### Add to Gradle build file

Adding the following dependencies to your `gradle.build` file.

```shell
dependencies {
	implementation 'javax.xml.bind:jaxb-api:2.3.0'
	implementation 'com.sun.xml.bind:jaxb-impl:2.3.0'
	implementation 'com.sun.xml.bind:jaxb-core:2.3.0'
	implementation 'javax.activation:activation:1.1.1'
}
```
