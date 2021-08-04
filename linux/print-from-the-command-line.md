# Print From The Command Line

__Category: Linux__

You can send a file to a printer from the command line on Linux using the versatile `nc` (netcat) command. Most printers expose port 9100 on the network.

For example, assuming a printer IP address of 192.168.1.128:

```shell
nc 192.168.1.128 9100 < /path/to/mydocument.pdf
````

Alternatively, use the printer name on the network or add an alias for it to your hosts file.

Note, the same command also works on macOS.