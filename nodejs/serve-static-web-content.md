# Serve Static Web Content

__Category: Nodejs__

Nodejs provides the ability to serve static web content using the `serve` package.

Install `serve` globally:

```shell
yarn global add serve
```

Assuming your web site content resides in a directory called `build`, serve on the default port of 3000 as follows:

```shell
serve -s build
```

Access the web site at http://localhost:3000

If necessary, you can specify a different port using the `-l` flag. To serve on port 4000:

```shell
serve -s build -l 4000
```

Access the web site at http://localhost:4000
