# Compile To An Executable

__Category: Nodejs__

You can cross-compile a Nodejs application on Linux, Windows, and macOS to an executable using `pkg`. 

Applications compiled using `pkg` do not require Node to be installed on a target system in order to run.

Install globally using yarn:

```shell
yarn global add pkg
```

Compile an application with an entrypoint of `src/server.js` to a binary file called `my-node-app` using the Node 16 runtime on macOS x64 architecture:

```shell
pkg src/server.js --targets node16-macos-x64 --output my-node-app
```

Compile an application with an entrypoint of `src/app.js` to a binary file called `my-node-app` using the Node 14 runtime on Linux arm v7 architecture (for example, to run on a Raspberry Pi):

```shell
pkg src/app.js --targets node14-linux-armv7 --output my-node-app
```

__Note:__ Some applications may require advanced configuration for loading assets or writing to log files. See [Pkg from Vercel](https://github.com/vercel/pkg) for more details on configuration options.
