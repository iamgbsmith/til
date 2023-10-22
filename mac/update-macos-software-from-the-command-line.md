# Update MacOS Software From The Command Line

__Category: Mac__

You can update software installed on macOS from the command line.

To show a list of available software updates, run the following command:

```shell
softwareupdate --list
```

To select and specific application to install updates for, identify the name of the update that was displayed from the output of the `--list` command. 

Install software updates with the following command:

```shell
softwareupdate --install [product-name]
```

For example, to update to Safari v17:

```shell
softwareupdate --install Safari17.0VenturaAuto-17.0
```

To install all software updates:

```shell
softwareupdate --install -all
```

__Note:__ You may be prompted to close applications prior to installing updates.
