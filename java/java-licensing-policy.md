# Java Licensing Policy

*This article was written around the time Oracle moved to a new licensing model for Java in 2017.*

## Background
Since 1995, the Java ecosystem was built on a high quality free (zero-cost) JDK available from Oracle, and previously Sun Microsystems. Major updates to Java versions were infrequent and support for past versions was offered years after the initial release of the JDK at no cost. 
 
### Oracle JDK
From September 2017 following the release of Java 9, Oracle moved to a six-month release cycle for the Oracle JDK.
 
The inference from this policy change was that Oracle wanted to focus on moving Java forward with the cost of long-term support directly paid for by customers instead of giving it away for free. Software vendors would need to continue upgrading Java, moving to a new version every six months and deploying patch releases between new versions. 

Unfortunately, upgrading an underlying library or runtime presents a challenge as it typically requires extensive testing to ensure no regression in application funcionality or performance.
 
Alternatives to using the commercial JDK from Oracle exist and are as follows:
 
### OpenJDK builds by Oracle
As well as their commercial JDK, Oracle produce an OpenJDK build. It is zero-cost and considered safe for commercial use however there are strings attached. For Java 11, the expectation is there will be Java 11.0.0, then two security patches 11.0.1 and 11.0.2. The catch with OpenJDK is that builds from Oracle for a specific Java version are only available for the first six months after a release. Therefore if on Java 11, to continue using the OpenJDK from Oracle with security patches requires moving to Java 12 within one month of it being released; the cycle continues for future Java versions.
 
### AdoptOpenJDK builds
AdoptOpenJDK is a community group which provides free unbranded builds of OpenJDK under the GPL license with a “Classpath Exception” which makes these builds safe for commercial use. Unlike the OpenJDK builds by Oracle, these builds will continue for a much longer period for major releases providing Long Term Support (LTS) releases. The Java 11 builds will continue for 4 years, one year after the next major release. AdoptOpenJDK will provide builds on the proviso that other groups create and publish security patches in a source repository at OpenJDK. Both IBM and Red Hat have indicated that they intend to provide those security patches.
 
### Azul Zulu
Zulu is a branded build of OpenJDK with commercial paid-for support. In addition, Azul provides some Zulu builds for free as "Zulu Community", however there are no specific commitments as to the availability of those free builds.
 
## Is Java still free to use?
This is an area where there has been a great deal of uncertainty. Despite changes to distribution of the Oracle JDK in Java 9, Java is still available for free and can be used commercially at no cost if commercial support is not required. 

If an organisation requires commercial support for Java and it is using the Oracle JDK then it must pay a support fee to Oracle as outlined on their website at https://www.oracle.com/java/technologies/javase/jdk-faqs.html

Support or licensing fees will not be charged for companies who use OpenJDK or AdoptOpenJDK builds for the JVM.

__Given a choice, it is recommended that AdoptOpenJDK builds are used as these provide broad platform support and considered the least restrictive from a licensing perspective.__

See [AdoptOpenJDK.net](https://adoptopenjdk.net/about.html) for more details.
