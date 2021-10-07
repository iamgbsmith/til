# Ensure All JUnit Tests Are Running

__Category: Gradle__

In some situations, mixing legacy JUnit4 (Vintage) and newer JUnit5 (Jupiter) tests may prevent tests written using JUnit5 from being executed.

To ensure all tests are run, add the `includeEngines` directive to the test section in the `gradle.build` file.

```shell
test {
    useJUnitPlatform {
        includeEngines("junit-jupiter", "junit-vintage")
    }
}
```

You can validate the status of Gradle builds and test execution using the `--info` parameter to log more output from the build process.
