# Install Snap On Linux

__Category: Linux__

Snap can be installed on Linux wit the following command:

```shell
sudo apt install snapd
```

You will need to reboot the OS for changes to take effect.

```shell
shutdown -r now
```

After rebooting, install the core snap in order to get the latest `snapd`:

```shell
sudo snap install core
```

Test that Snap works by installing the hello-world snap. If you are not the root user you will need to use sudo.

```shell
sudo snap install hello-world
```

Run the snap:

```shell
hello-world
```
