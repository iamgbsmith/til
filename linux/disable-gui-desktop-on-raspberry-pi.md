# Disable GUI Desktop On Raspberry Pi OS

__Category: Linux__

You can temporarily disable the GUI desktop on Raspberry Pi OS as follows:

```shell
systemctl stop lightdm
```

To restart the GUI desktop:

```shell
systemctl start lightdm
```

To permanently disable the GUI desktop, launch system configuration:

```shell
sudo raspi-config
```

From the menu, select "System Options" then "Boot / Auto Login".

To boot to the console, select the "Console" option and save settings.

Restart the OS for changes to take affect.
