# Excessive Xcode Disk Usage

If you are developing on a Mac you will find that Xcode uses a lot of disk space for intermediate build information, project indexes and iOS simulators. It is not unusual for more than 60GB of simulators to be installed on your Mac with each one taking between 2.5GB and 3.5GB.

A quick way to recover disk space is to examine the contents of `~/Library/Developer/Xcode/iOS\ DeviceSupport/` 

```shell
ls -la
drwxr-xr-x   5 gregsmith  staff   160 13 Feb  2019 12.1.1 (16C50)
drwxr-xr-x   5 gregsmith  staff   160 16 Feb  2019 12.1.2 (16C101)
drwxr-xr-x   5 gregsmith  staff   160  7 Apr  2019 12.1.4 (16D57)
drwxr-xr-x   5 gregsmith  staff   160 17 Jun  2019 12.2 (16E227)
drwxr-xr-x   5 gregsmith  staff   160  7 Sep  2019 12.3.1 (16F203)
drwxr-xr-x   5 gregsmith  staff   160 22 Sep  2019 12.4.1 (16G102)
drwxr-xr-x   5 gregsmith  staff   160 28 Sep  2019 13.1 (17A844)
drwxr-xr-x   5 gregsmith  staff   160 20 Oct  2019 13.1.2 (17A860)
drwxr-xr-x   5 gregsmith  staff   160 26 Oct  2019 13.1.3 (17A878)
drwxr-xr-x   5 gregsmith  staff   160 15 Nov  2019 13.2 (17B84)
drwxr-xr-x   5 gregsmith  staff   160 14 Dec  2019 13.2.3 (17B111)
drwxr-xr-x   5 gregsmith  staff   160  6 Feb  2020 13.3 (17C54)
drwxr-xr-x   5 gregsmith  staff   160 11 Apr  2020 13.4 (17E255)
drwxr-xr-x   5 gregsmith  staff   160  1 Jun 08:37 13.4.1 (17E262)
drwxr-xr-x   5 gregsmith  staff   160 27 Jun 18:58 13.5.1 (17F80)
```

Delete directories for the iOS simulators that you are not using as build targets. 

If required, you can re-install the iOS simulators for targets you need at a later date.