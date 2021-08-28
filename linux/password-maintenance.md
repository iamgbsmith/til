# Password Maintenance

__Category: Linux__

You can change the password for a user account with the `passwd` command. Root users or accounts with sudo privileges can change passwords for other users. Regular users can only change their own password.

When using `passwd` you will be prompted to enter the current password, then the new password twice at the command line. Passwords are not shown on the screen when changing them.

### Change your password

Change your password with the following command:

```shell
passwd
```

### Change another user password

As a super-user, change the password for another user (in this example `randomusername`) with the following command:

```shell
sudo passwd accountname
```

### Force a user to change their password at next login

By default, passwords on Linux do not expire. You can force a user to change their password when they next login with the following command:

```shell
sudo passwd --expire accountname
```
__Note: Encrypted user passwords on Linux are stored in /etc/shadow__
