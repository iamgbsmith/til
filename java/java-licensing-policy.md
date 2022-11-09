# Java Licensing Policy

__Category: Java__

*This article was written around the time Oracle moved to a new licensing model for Java 9 in 2017. It has been revised for 2020 when [AdoptOpenJDK was transferred to the Eclipse Foundation and renamed to Eclipse Adoptium.](https://blog.adoptopenjdk.net/2020/06/adoptopenjdk-to-join-the-eclipse-foundation/) It is not legal advice and you should consult a specialist if in doubt.*

## Background
Up until 2017, the Java platform had been built on a high quality free JDK available from Sun Microsystems and Oracle. Major updates of Java were infrequent and support for past versions was offered many years after the initial release of the JDK at no cost to users.
 
## Oracle JDK
Oracle’s changes to Java licensing resulted in enterprises re-evaluating their requirements for a stable Java distribution with reliable support at a reasonable cost. In a potential trap for the unwary, from September 2017 following the release of Java 9, Oracle moved to a new license which requires [commercially licensing](https://www.oracle.com/java/technologies/javase/jdk-faqs.html) the Oracle JDK for use in a production environment. 

## Recommendations
[AdoptOpenJDK/Eclipse Adoptium](https://adoptopenjdk.net) ] should be your first choice as an alternative to the Oracle JDK for the following reasons:

* It is backed by some of the largest organisations and vendors globally.
* It provides a reliable source of OpenJDK binaries with a long term future through LTS versions.
* It is the most comprehensive in its coverage of operating systems and architectures.
* There is a strong commitment to backporting security fixes with extensive use of regression, functional, system, load, application and performance tests that can be reviewed by the community.
* It will provide OpenJDK builds for Java 8 through to September 2023 in contrast to Oracle who will cease to supply updates beyond December 2020.

* At the time of writing, Java 17 which is an LTS build, has been released.*

See [AdoptOpenJDK.net](https://adoptopenjdk.net/about.html) for more details.
