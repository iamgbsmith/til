# Find Which Process Is Using A Port

__Category: Windows__

You can find which process is using a port by using the `netstat` and `tasklist` commands. For example, to find which process is using port 3389, look for an entry for TCP with a status of LISTENING from the output of the following:

```shell
cmd /c 'netstat -ano | find "3389"'
```

The output of this will be a list of matching processes with the right-most column showing the Process ID (PID).

Assume the PID for the process running on port 3389 is 1624, search the tasklist:

```shell
cmd /c 'tasklist /svc | find 1624"'  
```

The output from this command will be the name of the process in the right-most column.
