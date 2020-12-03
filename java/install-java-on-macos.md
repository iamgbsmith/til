# Install Java On macOS

Java no longer ships pre-installed on macOS. Rather than using `brew`, a better way to install Java on macOS is to download pre-built binaries from https://adoptopenjdk.net as this provides more flexibility with regards to Java versions and installation locations. 

The steps outlined here will install AdoptOpenJDK Java version 11 LTS (Long Term Support).

### Install and Configure the JDK

Download the latest macOS x64 JDK binary from https://adoptopenjdk.net/index.html

Create an install directory for Java that will not be moved or deleted:

```shell
mkdir -p /Library/Java/JavaVirtualMachines
cd /Library/Java/JavaVirtualMachines
```

Extract the binary archive you downloaded:

```shell
tar -xf OpenJDK11U-jdk_x64_mac_hotspot_11.0.8_10.tar.gz
```

Edit ~/.bash_profile and add Java to your path:
```shell
JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-11.0.8+10
export PATH=$JAVA_HOME/Contents/Home/bin:$PATH
```

Confirm Java version:
```shell
java -version
```

```
openjdk version "11" 2018-09-25
OpenJDK Runtime Environment AdoptOpenJDK (build 11+28)
OpenJDK 64-Bit Server VM AdoptOpenJDK (build 11+28, mixed mode)
```

### Important considerations

* Always use LTS (Long Term Support) versions of Java as these will be supported for extended timeframes. LTS versions are most suitable for enterprise customers as they offer support for critical updates.
* __Avoid using Oracle Java Binaries if you do not want to commercially license their JVM.__

See [AdoptOpenJDK Prebuilt OpenJDK Binaries](https://adoptopenjdk.net) for more details.
