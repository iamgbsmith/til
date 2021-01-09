# Java Licensing Policy

__Category: Java__

*This article was written around the time Oracle moved to a new licensing model for Java 9 in 2017. It has been revised for 2020 around the same time that [AdoptOpenJDK was transferred to the Eclipse Foundation and renamed to Eclipse Adoptium.](https://blog.adoptopenjdk.net/2020/06/adoptopenjdk-to-join-the-eclipse-foundation/) It is not legal advice and you should consult a lawyer if in doubt.*

## Background
Since 1995, the Java ecosystem has been built on a high quality free (zero-cost) JDK available from Oracle, and previously Sun Microsystems. Major updates to Java versions were infrequent and support for past versions was offered many years after the initial release of the JDK at no cost to users.
 
### Oracle JDK
Oracle’s changes to Java licensing has resulted in enterprises re-evaluating their requirements for a stable Java distribution with reliable support at a reasonable cost. In a potential trap for the unwary, from September 2017 following the release of Java 9, Oracle has moved to a new license which requires [commercially licensing](https://www.oracle.com/java/technologies/javase/jdk-faqs.html) the Oracle JDK for use in a production environment. 

## Alternatives to using the commercial JDK from Oracle

### AdoptOpenJDK/Eclipse Adoptium builds
[AdoptOpenJDK/Eclipse Adoptium](https://adoptopenjdk.net) is a community group which provides prebuilt unbranded builds of Open Java Development Kit (OpenJDK) under the GPL license with a “Classpath Exception” making it safe for commercial use.

AdoptOpenJDK/Eclipse Adoptium builds differ from OpenJDK Oracle builds in that they provide Long Term Support (LTS) releases. The Java 11 builds will continue for 4 years, one year after the next major release. Amazon, IBM, Microsoft, New Relic, Pivotal and Red Hat are vendors contributing to the project. [Commercial support](https://adoptopenjdk.net/support.html) can be purchased if required.
 
### Amazon Corretto
[Amazon Corretto](https://aws.amazon.com/corretto) is a no-cost, multiplatform, production-ready distribution of OpenJDK. Corretto comes with long-term support that will include performance enhancements and security fixes. 

Amazon Corretto is certified to meet the Java SE standard and can be used as a drop-in replacement for many Java SE distributions. Amazon provides quarterly updates that include performance enhancements and security fixes critical for enterprise application development. There are no additional paid features or restrictions.

### Azul Zulu
[Azul Zulu](https://www.azul.com/products/zulu-community) is a branded build of OpenJDK without restrictions. Azul offer commercial support and with Zulu Community you get access to selected new OpenJDK features up to 6 months faster than other builds. Azul also maintains an archive of Zulu Community builds of OpenJDK that goes back to 2014.

### OpenJDK builds by Oracle
[OpenJDK](https://openjdk.java.net) is an open-source JDK considered safe for commercial use however there are strings attached. Builds from Oracle for a specific Java version are only available for the first six months after a release and to continue using the OpenJDK you must move to the next version of Java no more than one month after it is released.

## Recommendations
AdoptOpenJDK/Eclipse Adoptium should be your first choice as an alternative to the Oracle JDK for the following reasons:
* It is backed by some of the largest organisations and vendors globally.
* It provides a reliable source of OpenJDK binaries with a long term future through LTS versions.
* It is the most comprehensive in its coverage of operating systems and architectures.
* There is a strong commitment to backporting security fixes with extensive use of regression, functional, system, load, application and performance tests that can be reviewed by the community.
* It will provide OpenJDK builds for Java 8 through to September 2023 in contrast to Oracle who will cease to supply updates beyond December 2020.

See [AdoptOpenJDK.net](https://adoptopenjdk.net/about.html) for more details.
