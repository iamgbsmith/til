# Convert Markdown To PDF

__Category: Nodejs__

You can convert Markdown to PDF in Node.js using the `md-to-pdf` package. The steps here will install the package globally for use at the command line.

Install `md-to-pdf` globally:

```shell
yarn global add md-to-pdf
```


Convert from Markdown to PDF at the command line:

```shell
md-to-pdf /path/to/input.md
```

Alternatively, pass from stdin and pipe to stdout into a target file:

```shell
cat input.md | md-to-pdf > /path/to/output.pdf
```

See [md-to-pdf on Github](https://github.com/simonhaenisch/md-to-pdf) for more details.
