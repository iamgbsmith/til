# Show Timestamps In Bash History

__Category: Linux__

By default, the output from `history` does not show a timestamp when commands were run in bash.

To enable timestamps in history for the logged in user, update `~./bashrc` as follows:

```shell
echo 'export HISTTIMEFORMAT="%F %T "' >> ~/.bashrc
```

In the above:

* %F shows Date in the format ‘YYYY-M-D’ (year-month-date)
* %T shows Time in the format ‘HH:MM:S’ (hour:minutes:seconds)
* There is a space after %T and before " so that there is a space in your bash history between the time the command was executed and the command itself

To enable this change, activate as follows:

```shell
source  ~/.bashrc
```

To enable timestamps for all users, add the HISTTIMEFORMAT variable to `/etc/profile`