# Run Commands In The Background

__Category: Linux__

Linux or macOS can run commands in the background using the `&` symbol after the command. You can use this for commands that are long running.

For example, to run `top` in the background:

```shell
top &
```

List background commands showing the job and process id using the `jobs -l` command.

```shell
jobs -l

[1]+ 31872 Stopped (tty output): 22top
```

Bring the command back to the foreground use the `fg` command with the id of the job.

```shell
fg 1
```
