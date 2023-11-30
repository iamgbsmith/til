# Convert JSON To CSV Using PowerShell

__Category: Windows__

You can use the `ConvertFrom-Json` PowerShell command to convert JSON to a different format.

Assuming a file called `input.json` in the current directory, use the following command to convert to `output.csv` in your temp directory:

```shell
Get-Content input.json | ConvertFrom-Json | Export-Csv C: \Temp\output.csv -NoTypeInformation
```

__Note:__ The above will convert simple JSON data structures. See [ConvertFrom-Json](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-7.4) for details on how to convert more complex JSON data structures to different formats.
