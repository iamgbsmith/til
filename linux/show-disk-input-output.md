# Show Disk Input Output

__Category: Linux__

You can show operating system CPU load and disk input/output (IO) using `iostat`. Default output includes a CPU load section and a disk IO section. This TIL will focus on the disk IO.

To show all information in MBs `-m` using exended format `-x` for disk IO:

```shell
iostat -m -x
```

To show 3 reports in MBs, producing output every 3 seconds:

```shell
iostat -m 3 3 -x
```

To display the output only for disk using `-d` in MBs, updating every 2 seconds:

```shell
watch -d -n2 iostat -d -m
```

Sample output:

```shell
Linux 5.10.103-v7+ (raspberrypi)        22/10/22        _armv7l_        (4 CPU)

Device             tps    MB_read/s    MB_wrtn/s    MB_read    MB_wrtn
loop0             0.16         0.01         0.00         14          0
loop1             0.02         0.00         0.00          1          0
loop2             0.01         0.00         0.00          0          0
loop3             0.00         0.00         0.00          0          0
mmcblk0           2.67         0.11         0.06        282        151
```
