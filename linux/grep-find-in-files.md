# Grep Find In Files

You can search for a specific string in files recursively using `grep`.

### Example 1

Search files in the current directory for the word "array". Match whole words. Print out the line number and filename where a match is found.

```shell
grep -nw "array" *
```

__Note:__ You can omit the double quotes if the string literal you are searching for is one word.

### Example 2

Recursively search files from a specific directory for the word "array". Match whole words. Print out the line number and filename where a match is found.

```shell
grep -rnw "array" /path/to/somewhere/
```

__Note:__ You can omit the double quotes if the string literal you are searching for is one word.

### Example 3

Search recursively files from the current directory for the word "array" in all files which have the extension `.js`. Match whole words. Print out the line number and filename where a match is found.

```shell
grep --include=\*.js -rnw "array" ./ 
```

Exclude specific files by using the `--exclude=` argument. For example: `--exclude=\*.js`

In the above examples:

* `-r` searches recursively
* `-n` prints the line number
* `-w` matches the whole word
