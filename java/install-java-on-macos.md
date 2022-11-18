# Install Java On macOS

__Category: Java__

Java no longer ships pre-installed on macOS. Rather than using `brew`, a better way to install Java on macOS is to download pre-built binaries from https://adoptium.net as this provides more flexibility with regards to Java versions and installation locations. 

The steps outlined here will install AdoptOpenJDK Java version 11 LTS (Long Term Support).

### Install and Configure the JDK

Download the latest macOS x64 JDK binary from https://adoptium.net/download/

Create an install directory for Java that will not be moved or deleted:

```shell
mkdir -p /Library/Java/JavaVirtualMachines
cd /Library/Java/JavaVirtualMachines
```

Extract the binary archive you downloaded to `/Library/Java/JavaVirtualMachines`

```shell
tar -xf OpenJDK17U-jdk_x64_mac_hotspot_17.0.5_8.tar
```

Edit ~/.bash_profile and add Java to your path:
```shell
JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-17.0.5+8
export PATH=$JAVA_HOME/Contents/Home/bin:$PATH
```

Confirm Java version:
```shell
java -version
```

```
openjdk version "17.0.5" 2022-10-18
OpenJDK Runtime Environment Temurin-17.0.5+8 (build 17.0.5+8)
OpenJDK 64-Bit Server VM Temurin-17.0.5+8 (build 17.0.5+8, mixed mode, sharing)
```

### Important considerations

* Always use LTS (Long Term Support) versions of Java as these will be supported for extended timeframes. LTS versions are most suitable for enterprise customers as they offer support for critical updates.
* __Avoid using Oracle Java Binaries if you do not want to commercially license their JVM.__

See [AdoptOpenJDK Prebuilt OpenJDK Binaries](https://adoptium.net) for more details.
