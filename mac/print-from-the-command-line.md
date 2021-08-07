# Print From The Command Line

__Category: Mac__

You can send a file to a printer from the command line on macOS using the `lpr` command.

For example, assuming a printer name of "office-printer":

```shell
lpr -P office-printer -E -r /path/to/mydocument.pdf
````

In the above, `-P` specifies the printer name, `-E` will forces an encrypted connection if supported by the printer, `-r` removes the file on completion of spooling.