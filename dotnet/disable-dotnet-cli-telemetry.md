# Disable DotNet CLI Telemetry

__Category: DotNet__

The .NET SDK includes a telemetry feature that [collects usage data](https://learn.microsoft.com/en-us/dotnet/core/tools/telemetry) and sends it to Microsoft when you use .NET CLI commands.

You can disable .NET telemetry at the command line by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to true.

```shell
set DOTNET_CLI_TELEMETRY_OPTOUT=true
```

To make this configuration permanent on your machine, add the setting to your system environment variables.
