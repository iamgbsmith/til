# Alternatives To The Oracle JDK

__Category: Java__

In 2017, Oracle’s changes to Java licensing resulted in enterprises re-evaluating their requirements for a stable Java distribution with reliable support at a reasonable cost. The following are non-commercial JDK alternatives.

### AdoptOpenJDK/Eclipse Adoptium builds
[AdoptOpenJDK/Eclipse Adoptium](https://adoptopenjdk.net) is a community group which provides prebuilt unbranded builds of Open Java Development Kit (OpenJDK) under the GPL license with a “Classpath Exception” making it safe for commercial use.

AdoptOpenJDK/Eclipse Adoptium builds differ from OpenJDK Oracle builds in that they provide Long Term Support (LTS) releases. The Java 11 builds will continue for 4 years, one year after the next major release. Amazon, IBM, Microsoft, New Relic, Pivotal and Red Hat are vendors contributing to the project. [Commercial support](https://adoptopenjdk.net/support.html) can be purchased if required.
 
### Amazon Corretto
[Amazon Corretto](https://aws.amazon.com/corretto) is a no-cost, multiplatform, production-ready distribution of OpenJDK. Corretto comes with long-term support that will include performance enhancements and security fixes. 

Amazon Corretto is certified to meet the Java SE standard and can be used as a drop-in replacement for many Java SE distributions. Amazon provides quarterly updates that include performance enhancements and security fixes critical for enterprise application development. There are no additional paid features or restrictions.

### Azul Zulu
[Azul Zulu](https://www.azul.com/products/zulu-community) is a branded build of OpenJDK without restrictions. Azul offer commercial support and with Zulu Community you get access to selected new OpenJDK features up to 6 months faster than other builds. Azul also maintains an archive of Zulu Community builds of OpenJDK that goes back to 2014.

### Microsoft builds of OpenJDK
The [Microsoft Build of OpenJDK](https://learn.microsoft.com/en-gb/java/openjdk/) provides a no-cost distribution of OpenJDK that is open source and available for free as a drop-in replacement for any other OpenJDK distribution. It includes Long-Term Support (LTS) binaries for Java 11 and Java 17 on x64 server and desktop environments on macOS, Linux, and Windows, AArch64/ARM64 on Linux and Windows. 

Container images for the Microsoft Build of OpenJDK are available at https://learn.microsoft.com/en-gb/java/openjdk/containers

### OpenJDK builds by Oracle
[OpenJDK](https://openjdk.java.net) is an open-source JDK considered safe for commercial use however there are strings attached. Builds from Oracle for a specific Java version are only available for the first six months after a release and to continue using the OpenJDK you must move to the next version of Java no more than one month after it is released.