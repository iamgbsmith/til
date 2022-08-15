# JVM Thread Dumps On Windows

__Category: Java__

JVM thread dumps can be used to inspect the internal state of a Java process and determine whether any threads are deadlocked or spiking the CPU. A thread dump can be performed at the command line on Windows.

Get the process ID (PID) for the running JVM using Task Manager or PowerShell:

```shell
Get-Process java
```

### Create a thread dump using jstack

With the PID, perform the thread dump using `jstack` and send the output to a file:

```shell
jstack <PID> > thread-dump-output.txt
```

### Create a thread dump with key commands

Alternatively, from a running console window, press Ctrl + Shift + Pause which will print the thread dump directly to the console.
