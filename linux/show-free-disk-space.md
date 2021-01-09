# Show Free Disk Space

__Category: Linux__

You can show how much disk space is free on all mounted file systems by using the `df` command.

Use `df` with the argument `-h` to show output in "human-readable" format.

```bash
df -h
```

The output will be similar to the following:

```bash
Filesystem      Size  Used Avail Use% Mounted on
/dev/root        15G   12G  2.5G  82% /
devtmpfs        211M     0  211M   0% /dev
tmpfs           216M     0  216M   0% /dev/shm
tmpfs           216M  5.9M  210M   3% /run
tmpfs           5.0M  4.0K  5.0M   1% /run/lock
tmpfs           216M     0  216M   0% /sys/fs/cgroup
/dev/mmcblk0p1   43M   23M   20M  53% /boot
tmpfs            44M     0   44M   0% /run/user/1000
```