# Count Characters Words And Lines In A File

__Category: Windows__

You can count the number of characters, words, and lines in a file using PowerShell.

Count the number of characters:

```shell
Get-Content some-file.txt | Measure-Object -Character | select-object -ExpandProperty Characters
```

Count the number of words:

```shell
Get-Content some-file.txt  | Measure-Object -Word | select-object -ExpandProperty Words
```

Count the number of lines:

```shell
Get-Content some-file.txt  | Measure-Object -Line | select-object -ExpandProperty Lines
```

Count everything showing the output in table format:

```shell
Get-Content some-file.txt  | Measure-Object -Character -Line -Word
```
