# Lock And Unlock User Accounts

__Category: Linux__

The `usermod` command is used for modifying user accounts. For example, you can lock and unlock accounts.

__Note: `usermod` will lock accounts but not prevent a user from gaining SSH access to a server unless the `--expiredate` parameter is supplied.__

### Lock a user account

To lock a user account you can use the -L option with the following command:

```shell
sudo usermod -L accountname
```

To lock a user account and prevent SSH access specify an expiry date in the past with `--expiredate`:

```shell
sudo usermod -L --expiredate 1970-01-02 accountname
```

### Unlock a user account

To unlock a user account you can use the -U option with the following command:

```shell
sudo usermod -U accountname
```

To unlock a user account and allow SSH access clear the expired date:

```shell
sudo usermod -U --expiredate '' accountname
```
