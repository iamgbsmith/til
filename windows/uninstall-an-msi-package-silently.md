# Uninstall An MSI Package Silently

__Category: Windows__ 

You can uninstall an MSI package silently using the `msiexec` command with the `/x` and `/quiet` (no UI) flags:

```shell
msiexec /x "c:\path\to\your\file.msi" /quiet
```

If you no longer have the MSI package, uninstall using the ProductCode (Product GUID):

```shell
msiexec /x {ProductCode} /quiet
```

You can list product codes using PowerShell as follows:

```shell
get-wmiobject Win32_Product | Format-Table IdentifyingNumber, Name
```
