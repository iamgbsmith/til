# Install Gradle On MacOS

__Category: Gradle__

Gradle should be installed manually on macOS to ensure precise control over the specific version.

Download the latest Gradle distribution from https://gradle.org/releases and extract to a suitable location.

Edit .bash_profile file in the user directory

```shell
vi ~/.bash_profile
```

Add the following: 

```shell
GRADLE_HOME=/path/to/gradle/gradle-7.1.1;
export GRADLE_HOME
export PATH=$PATH:$GRADLE_HOME/bin
```

Restart the shell and confirm Gradle is installed:

```shell
gradle -v
```

```shell
Welcome to Gradle 7.1.1!

Here are the highlights of this release:
 - Faster incremental Java compilation
 - Easier source set configuration in the Kotlin DSL

For more details see https://docs.gradle.org/7.1.1/release-notes.html


------------------------------------------------------------
Gradle 7.1.1
------------------------------------------------------------

Build time:   2021-07-02 12:16:43 UTC
Revision:     774525a055494e0ece39f522ac7ad17498ce032c

Kotlin:       1.4.31
Groovy:       3.0.7
Ant:          Apache Ant(TM) version 1.10.9 compiled on September 27 2020
JVM:          11.0.1 (AdoptOpenJDK 11.0.1+13)
OS:           Mac OS X 10.16 x86_64

```
