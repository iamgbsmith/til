# Sync The System Clock With An NTP Server

__Category: Mac__

Sometimes when waking macOS from hibernation, the system clock can be incorrect.

You can sync the system clock which will update the date and time from an NTP server on macOS using the following command:

```shell
sudo sntp -sS pool.ntp.org
```
