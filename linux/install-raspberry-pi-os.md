# Install Raspberry Pi OS

__Category: Linux__

Raspberry Pi OS (formerly called Raspbian) is a Debian-based computer operating system for Raspberry Pi. The steps outlined here should be followed to install Linux onto a Pi, boot it, then connect it to over a WiFi network. 

Download Raspbian Stretch with desktop from https://www.raspberrypi.org/software/operating-systems/ and extract the zip file. An SD card of 8GB or more capacity is recommended for Raspberry Pi OS

Use [Balena Etcher](https://www.balena.io/etcher/) to write the image of Raspbian to the Micro SD card.

### Enable SSH

In order to SSH onto the Pi, create an empty file called `ssh` in /boot on the image (this will be /Volumes/boot when accessing from a Mac). This will enable SSH when the Pi is booted.

### Enable WiFi

To preconfigure the Pi to connect to a WiFi network, create a file called `wpa_supplicant.conf` in the root of the boot volume with the following contents. 

```shell
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=<TWO_LETTER_ISO_COUNTRY_CODE>

network={
    ssid="<WIFI_NETWORK_NAME>"
    psk="<WIFI_PASSWORD>"
    key_mgmt=WPA-PSK
}
 ```

### Boot the Pi and connect to it

Insert the SD card into the Pi and boot the device. 

Assuming there is only one Pi on the network, you will be able to SSH to `raspberrypi.local`. If there is more than one Pi on the network you may need to perform a seach using `nmap`.

Connect to the Pi over SSH with `ssh pi@raspberrypi.local` using a default password of __raspberry__

Once authenticated, use `passwd` to change the password to something strong.
