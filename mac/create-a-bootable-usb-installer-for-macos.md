# Create A Bootable USB Installer For MacOS

__Category: Mac__

You can create a bootable USB installer for macOS as follows:

* Download the macOS installation image from Apple. You can do this by opening App Store and searching for the operating system you want to install. For example: macOS Big Sur or macOS Monterey. If the OS version is unavailable, search for a previous version at https://support.apple.com/en-us/HT211683
* Once you have downloaded the OS, open a terminal session and type the following (where `NameOfUSBDevice` should be substituted for the device to create the bootable install image on:

## Prepare USB Media

### Big Sur

```shell
sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/NameOfUSBDevice/
```

### Monterey

```shell
sudo /Applications/Install\ macOS\ Monterey.app/Contents/Resources/createinstallmedia --volume /Volumes/NameOfUSBDevice/
```

Change the name of the `Install xx` to match the OS you have downloaded and want to install.

## Install from USB

Insert the USB drive containing the bootable installer into your Mac before restarting.

### Apple Silicon

* Turn on your Mac and hold the power button until you see the startup options window showing bootable volumes.
* Select the volume containing the bootable installer, then click Continue.
* When the macOS installer opens, follow the onscreen instructions.

### Intel Processor

* Press and hold the `option (Alt) ⌥` key immediately after turning on or restarting your Mac.
* Release the Option key when you see a dark screen showing bootable volumes.
* Select the volume containing the bootable installer. 
* Choose your language, then click Continue and follow the prompts.

See [See How to create a bootable installer for macOS](https://support.apple.com/en-au/HT201372) for more details.