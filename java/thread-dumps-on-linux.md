# Thread Dumps On Linux

Java thread dumps are useful to inspect the internal state of the JVM and determine whether any threads are deadlocked or spiking the CPU. A thread dump can be performed at the command line as follows:

Get the process ID:

```
ps -ef | grep java
```

From the output generated by the above command, use the process ID for the Java application to perform the thread dump to the console:

```
kill -3 <PID>
```

Alternatively, send the thread dump output to a file:

```
kill -3 <PID> > thread-dump-output.txt
```

__Important:__ Ensure you include the "-3" option on the kill command otherwise you might terminate the process.