# Skip Tests During Builds

__Category: Gradle__

Good programming practice requires running tests as part your builds.

If however, you need to perform a basic compilation in Gradle without executing tests, run with the `-x` (exclude) parameter as follows:

```shell
gradle build -x test
```
