# Set Timezone

__Category: Linux__

Use the following command if you need to determine which timezones are supported by the OS:

```
ls -la /usr/share/zoneinfo
```

```
drwxr-xr-x   2 root root  4096 Jan 14 22:23 Africa
drwxr-xr-x   6 root root 20480 Jan 14 22:23 America
drwxr-xr-x   2 root root  4096 Jan 14 22:23 Antarctica
drwxr-xr-x   2 root root  4096 Jan 14 22:23 Arctic
drwxr-xr-x   2 root root 12288 Jan 14 22:23 Asia
drwxr-xr-x   2 root root  4096 Jan 14 22:23 Atlantic
drwxr-xr-x   2 root root  4096 Jan 14 22:23 Australia
drwxr-xr-x   2 root root  4096 Jan 14 22:23 Brazil
drwxr-xr-x   2 root root  4096 Jan 14 22:23 Canada
-rw-r--r--   1 root root  2102 Sep 18  2019 CET
drwxr-xr-x   2 root root  4096 Jan 14 22:23 Chile
-rw-r--r--   1 root root  2294 Sep 18  2019 CST6CDT
-rw-r--r--   1 root root  2437 Sep 18  2019 Cuba
-rw-r--r--   1 root root  1876 Sep 18  2019 EET
-rw-r--r--   1 root root  1972 Sep 18  2019 Egypt
-rw-r--r--   1 root root  3531 Sep 18  2019 Eire
-rw-r--r--   1 root root   127 Sep 18  2019 EST
-rw-r--r--   1 root root  2294 Sep 18  2019 EST5EDT
drwxr-xr-x   2 root root  4096 Jan 14 22:23 Etc
drwxr-xr-x   2 root root 12288 Jan 14 22:23 Europe
drwxr-xr-x   2 root root  4096 Jan 14 22:23 Pacific
[...]
```

Set the timzeone using the following command:

```
sudo ln -sf /usr/share/zoneinfo/Pacific/Auckland /etc/localtime
```

__Note:__ The above commands were run on Debian Linux.
