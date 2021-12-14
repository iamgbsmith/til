# List Project Dependencies
 
__Category: Gradle__

You can display the dependency tree for a project from the command line or by generating a searchable report using the `--scan` option.

### Display dependencies for the test runtime classpath configuration

```shell
gradle -q dependencies --configuration testRuntimeClasspath
```

__Note:__ The dependencies task selector will only execute the dependencies task on a single project. You must include the `--project` flag to select a project other than the root project.

### Display details on a specific dependency

Assume you want to see specifics related to a dependency that you think exists across all configurations in your project. For example, the `log4j` dependency:

```shell
gradle dependencyInsight --dependency log4j
```

### Generate a dependency report at gradle.org

Including the `--scan` option will generate a web based searchable report at gradle.org.


```shell
gradle dependencyInsight --dependency log4j --scan
```

See [Viewing and debugging dependencies](https://docs.gradle.org/current/userguide/viewing_debugging_dependencies.html) for more details.
