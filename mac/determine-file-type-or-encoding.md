# Determine File Type Or Encoding

__Category: Mac__

You may need to determine the file type or encoding for files which are missing an extension.

To show this for a file, run the following command:

```shell
file -I /path/to/file
```

Example output:

```shell
/path/to/file: image/png; charset=binary
```

The same command will also work on Linux.
