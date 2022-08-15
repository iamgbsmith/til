# JVM Thread Dumps On Linux

__Category: Java__

JVM thread dumps can be used to inspect the internal state of a Java process and determine whether any threads are deadlocked or spiking the CPU. A thread dump can be performed at the command line on Linux.

Get the process ID for the running JVM:

```
ps -ef | grep java
```

### Create a thread dump using the kill command

With the PID, perform the thread dump using `kill`:

```
kill -3 <PID>
```

Alternatively, send the thread dump output to a file:

```
kill -3 <PID> > thread-dump-output.txt
```

__Important:__ Ensure you include the "-3" option on the kill command otherwise you might terminate the process.

### Create a thread dump using jstack

With the PID, perform the thread dump using `jstack` and send the output to a file:

```shell
jstack <PID> > thread-dump-output.txt
```
