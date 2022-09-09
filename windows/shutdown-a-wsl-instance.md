# Shutdown A WSL Instance

__Category: Windows__

WSL instances can be listed from the Windows command prompt as follows:

```command
wsl -l
```

Output:

```command
Ubuntu-20.04 (Default)
docker-desktop
```

You can shutdown all running WSL instances matching a distro name from the host with the following command:

```command
wsl -t Ubuntu-20.04
```

Alternatively, from the WSL console type `exit` or `logout`.

__Note:__ When a WSL instance is started, it will be allocated a new IP address.
