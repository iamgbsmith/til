# Install Azure CLI On Windows

__Category: Azure__

The Azure CLI is used to interact with Azure services from the command line.

### Install on Windows

Installation can be done using an MSI file in Powershell. You must run the command as Administrator.

```shell
$ProgressPreference = 'SilentlyContinue'; Invoke-WebRequest -Uri https://aka.ms/installazurecliwindows -OutFile .\AzureCLI.msi; Start-Process msiexec.exe -Wait -ArgumentList '/I AzureCLI.msi /quiet'; Remove-Item \AzureCLI.msi
```

Alternatively, download the MSI file from https://aka.ms/installazurecliwindows and install manually.

Once installed, launch a new PowerShell.

Show the installed version:

```shell
az --version
```

### Update on Windows

Updates to the CLI are released on a regular basis. You can upgrade to the latest version as follows:

```shell 
az upgrade
```

### Uninstall on Windows

Uninstall the Azure CLI from the Windows "Apps and Features" list.

If you do not plan to reuse the CLI in future, remove the data directory from your profile as follows:

```shell
del C:\Users\<username>\.azure\msal_token_cache.bin 
del C:\Users\<username>\.azure\msal_token_cache.json
```

See [Install Azure CLI on Windows](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-windows?tabs-powershell) for more details.
