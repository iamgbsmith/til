# Clear Gradle Cache
 
__Category: Gradle__

The Gradle cache stores a local copy of dependencies and is located at `%USERPROFILE%\.gradle\caches` on Windows and `~/.gradle/caches/` on Mac and Linux. 

Over time it may go stale or require cleanup to recover disk space.

To clear the cache on Mac/Linux:

```shell
rm -rf ~/.gradle/caches/
```

Alternatively, run the following command for your project:

```shell
./gradlew cleanBuildCache
```

Dependencies will be downloaded when they are needed and cached for future use.
