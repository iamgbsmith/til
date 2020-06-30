# Grep Find In Files

You can search for a specific string in files recursively using `grep`.

### Example 1

Search in a specific directory for the word "react". Match whole words. Print out the line number and filename where a match is found.

```shell
grep -nw /path/to/somewhere/ -e "react"
```

### Example 2

Search recursively from the current directory for the word "array" in all files with the extension .js. Match whole words. Print out the line number and filename where a match is found.

```shell
grep --include=\*.js -rnw ./ -e "array"
```

Exclude specific files by using the `--exclude=` argument. For example: `--exclude=\*.js`

In the above examples:

* `-r` searches recursively
* `-n` prints the line number
* `-w` matches the whole word
* `-e` is the string to search for
