# Show CPU Load

__Category: Linux__

You can show CPU load (average) over time using the following command:

```shell
cat /proc/loadavg
```

To display the output from loadavg every 2 seconds:

```shell
watch -d -n2 cat /proc/loadavg
```

Sample output:

```shell
0.05 0.06 0.01 1/183 7463
```

### Columns in the output:

* Column 1 shows CPU and IO utilization for the last 1 minute
* Column 2 shows CPU and IO utilization for the last 5 minutes
* Column 3 shows CPU and IO utilization for the last 10 minutes
* Column 4 is the number of currently running and total running processes
* Column 5 is the last process ID (PID) run

### Interpreting the output:

* If the averages are 0.0, then the system is idle
* If the 1 minute average is higher than the 5 or 15 minute averages, load is increasing
* If the 1 minute average is lower than the 5 or 15 minute averages, load is decreasing
* Values should be less than the number of cores on the machine (i.e., less than 1.0 for a single core and less than 4.0 for a quad core machine)

