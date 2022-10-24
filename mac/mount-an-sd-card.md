# Mount An SD Card

__Category: Mac__

You can use an SD card as another filesystem on macOS. This TIL will mount a card formatted using the journaled file system.

Identify the attached SD card using `diskutil list`.

Ouput:

```text
/dev/disk2 (external, physical):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:     FDisk_partition_scheme                        *128.2 GB   disk2
   1:                  Apple_HFS ⁨Samsung⁩                 128.2 GB   disk2s1
```

In this example, `/dev/disk2s1` is the device on the SD card to mount to a pre-existing directory at `~/mnt`.

Mount using the following command, where -t specifies the filesystem type of "hfs":

```shell
sudo mount -t hfs /dev/disk2s1 ~/mnt
```

List the contents of the newly mounted SD card:

```
ls -la ~/mnt
```

To unmount the disk:

```shell
diskutil unmountDisk /dev/disk2s1
```
