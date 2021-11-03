# Write IMG File To SD Card From The Command Line

__Category: Mac__

The `dd` utility provides the ability to write an img file to an SD card from the command line. You may need to do this for example, when creating a bootable image on an SD card for use in a Raspberry Pi.

Identify the attached SD card using `diskutil list`.

In this example, `/dev/disk3` is the SD card to flash. 

Write the img file to the device as follows:

```shell
sudo dd if=/path/to/some-image-file.img of=/dev/disk3 bs=1m
```

You can check the progress of the operation by pressing ctrl + T to show how many bytes have been written to the card. Copying the img file to the SD card may take some time depending on how large the file is.

__Note:__  If there is an existing partition on the SD card you may see a "Resource busy" error message when you try to write the image. If this happens, unmount it using `diskutil unmountDisk /dev/disk3` and try executing the `dd` command again.
