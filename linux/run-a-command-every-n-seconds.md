# Run A Command Every N Seconds

__Category: Linux__

Linux or macOS can run commands every n seconds using `watch`.

For example, to refresh the output of `vmstat` every 2 seconds:

```shell
watch -n2 vmstat
```

Highlight differences in output with the `-d` flag:

```shell
watch -d -n2 vmstat
```

Exit watching when the output changes with the `-g` flag:

```shell
watch -g -n2 vmstat
```
