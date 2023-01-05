# What Are Virtual Threads

__Category: Java__

Java 19 introduced virtual threads which are lightweight threads that reduce the effort of writing, maintaining, and observing high-throughput concurrent applications on the JVM. They allow server applications to be written using a thread-per-request style to allow for scaling with near-optimal hardware utilisation.

A virtual thread is an instance of `java.lang.Thread` that runs Java code on an underlying OS thread but does not capture the OS thread for the code's entire lifetime. This means that many virtual threads can run their Java code on the same OS thread, effectively sharing it.

Virtual threads are intended to be short-lived and have shallow call stacks, performing operations such as a single HTTP client call or a single JDBC query. Support is also provided for thread-local variables and thread interruption.

See [JEP 425: Virtual Threads - Preview](https://openjdk.org/jeps/425) for more details.
