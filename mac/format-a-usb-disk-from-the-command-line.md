
# Format A USB Disk From The Command Line

__Category: Mac__

You can format a USB disk from the command line. Identify the disk to format using the `diskutil list` command.

To format using Extended Journaled (JHFS+) format:

```shell
diskutil eraseDisk JHFS+ DiskName /dev/DiskId
```

To format using ExFAT:

```shell
diskutil eraseDisk ExFAT DiskName /dev/DiskId
```
