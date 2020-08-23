# Java Licensing Policy

*This article was written around the time Oracle moved to a new licensing model for Java 9 in 2017. It has been revised for 2020.*

## Background
Since 1995, the Java ecosystem has been built on a high quality free (zero-cost) JDK available from Oracle, and previously Sun Microsystems. Major updates to Java versions were infrequent and support for past versions was offered many years after the initial release of the JDK at no cost to users.
 
### Oracle JDK
In a potential trap for the unwary, from September 2017 following the release of Java 9, Oracle has moved to a new license which requires [commerically licensing](https://www.oracle.com/java/technologies/javase/jdk-faqs.html) the Oracle JDK for use in a production environment. Software vendors will need to continue upgrading Java, moving to a new version every six months, optionally deploying patch releases between new versions.

## Alternatives to using the commercial JDK from Oracle
 
### AdoptOpenJDK builds
[AdoptOpenJDK](https://adoptopenjdk.net) is a community group which provides prebuilt unbranded builds of Open Java Development Kit (OpenJDK) under the GPL license with a “Classpath Exception” making it safe for commercial use.

AdoptOpenJDK builds differ from OpenJDK Oracle builds in that they provide Long Term Support (LTS) releases. The Java 11 builds will continue for 4 years, one year after the next major release. Amazon, IBM, Microsoft, New Relic, Pivotal and Red Hat are vendors behind the AdoptOpenJDK Community.
 
### Amazon Corretto
[Amazon Corretto](https://aws.amazon.com/corretto) Amazon Corretto is a no-cost, multiplatform, production-ready distribution of OpenJDK. Corretto comes with long-term support that will include performance enhancements and security fixes. 

Amazon Corretto is certified to meet the Java SE standard and can be used as a drop-in replacement for many Java SE distributions. Amazon provides quarterly updates that include performance enhancements and security fixes critical for enterprise application development. There are no additional paid features or restrictions.

### Azul Zulu
[Azul Zulu](https://www.azul.com/products/zulu-community) is a branded build of OpenJDK without restrictions. Azul offer commercial support and with Zulu Community you get access to selected new OpenJDK features up to 6 months faster than other builds. Azul also maintains an archive of Zulu Community builds of OpenJDK that goes back to 2014.

### OpenJDK builds by Oracle
[OpenJDK](https://openjdk.java.net) is an open-source JDK considered safe for commercial use however there are strings attached. Builds from Oracle for a specific Java version are only available for the first six months after a release and to continue using the OpenJDK you must move to the next version of Java no more than one month after it is released.

## Recommendations
Given a choice, it is recommended that AdoptOpenJDK builds are used as these provide a commitment to long term support and are considered the least restrictive from a licensing perspective. 

AdoptOpenJDK will will also publish security patches meaning that risks associated with using older versions of the JVM will be reduced on the proviso that updates are deployed on an as-needed basis. At the time of writing, AdoptOpenJDK 14 is the latest version and 11 is the most recent LTS release.

See [AdoptOpenJDK.net](https://adoptopenjdk.net/about.html) for more details.
