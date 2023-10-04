# Install An MSI Package Silently

__Category: Windows__ 

You can install an MSI package silently using the `msiexec` command with the `/i` and `/quiet` (no UI) flags:

```shell
msiexec.exe /i "c:\path\to\your\file.msi" /quiet
```

To instaall an MSI package silently with verbose logging:

```shell
msiexec.exe /i "c:\path\to\your\file.msi" /L*V "C:\path\to\package-install.log" /quiet
```
