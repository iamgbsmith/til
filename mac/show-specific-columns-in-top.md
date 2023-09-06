# Show Specific Columns In Top

__Category: Mac__

You can show specific columns (stats) when using the `top` command on macOS.

For example, to show the process name, PID, CPU use, memory use, CPU time, and process state:

```shell
top -stats command,pid,cpu,threads,mem,time,state
```

Available stats you can show are:

```shell
pid, command, cpu, cpu_me, cpu_others, csw, time, threads, ports, mregion, mem, rprvt, purg, vsize, vprvt, kprvt, kshrd, pgrp, ppid, state, uid, wq, faults, cow, user, msgsent, msgrecv, sysbsd, sysmach, pageins, boosts, instrs, cycles
```
