# Get Weather Information From The Command Line

__Category: Windows__

You can get weather information from the command line using PowerShell. Requests are sent to `wttr.in` although there may be limitations with showing output due to character encoding of responses by PowerShell. 

The following will obtain weather for London:

```command
(Invoke-WebRequest https://wttr.in/London).Content
```

If you omit the location you will get the report for your current location based on your IP address. For example:

```command
(Invoke-WebRequest https://wttr.in).Content
```

Alternatively, use the shorthand method `irm` (Invoke REST Method):

```command
irm https://wttr.in/London
```

See [chubin/wttr.in](https://github.com/chubin/wttr.in) for more details.
