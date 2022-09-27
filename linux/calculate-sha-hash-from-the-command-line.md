# Calculate SHA Hash From The Command Line

__Category: Linux__

You can calculate a SHA hash from plain text at the command line. These commands also work on macOS.

To calculate a SHA256 hash for the plan text value `mthuttSkijacket2018`:

```shell
echo -n "mthuttSkijacket2018" | shasum -a 256 | awk '{ print $1 }'
```

Output:

```shell
d7bcd219211ac1032df55cc06ba9e5cc3e1d20ef0242d628de699ff498d76228
```

To calculate a SHA512 hash for the plan text value `mthuttSkijacket2018`:

```shell
echo -n "mthuttSkijacket2018" | shasum -a 512 | awk '{ print $1 }'
```

Output:

```shell
fbd789ec2a8e0a4a144181b281a34381455c5d415a1fc2d20bc49c06bf76fae13659b7555213d9a1032f53bb771aa8fde6fff96d82461b26cde627c3ff680293
```

Enclosing the text to be converted in quotes will alllow a string containing spaces to be hashed from plain text.
