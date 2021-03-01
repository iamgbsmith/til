# Using Node Version Manager

__Category: Nodejs__

`nvm` is a version manager for Node.js, designed to be installed per-user, and invoked per-shell. It allows easier use of different versions of Node.js on a single local enviroment and supports switching between them with minimal effort.

The steps outlined here are for NVM on a Mac however they should also work on Linux and Windows (and Windows using [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10)).

### Install NVM

Specify the version of NVM based on the release versions at https://github.com/nvm-sh/nvm/tags. This TIL will be installing v0.37.2 of NVM.

```shell
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.2/install.sh | bash
```

__Close and reopen your terminal to start using nvm.__

### Verify installation

Verify NVM has installed using the command:

```shell
command -v nvm
```

This should output `nvm` to the console if the installation was successful.

### List node versions

List installed Node versions with the following command:

```shell
nvm ls
```

To see what versions are available to install (due to the number of verisons, you may want to pipe the output to `less`):

```shell
nvm ls-remote
```

### Install specific versions of Node

#### Install Node LTS

Install the latest LTS (Long Term Support) version with the following command:

```shell
nvm install --lts
```

Output:

```shell
Installing latest LTS version.
Downloading and installing node v14.15.5...
Downloading https://nodejs.org/dist/v14.15.5/node-v14.15.5-darwin-x64.tar.xz...
################################################################################################################################# 100.0%
Computing checksum with shasum -a 256
Checksums matched!
Now using node v14.15.5 (npm v6.14.11)
Creating default alias: default -> lts/* (-> v14.15.5)
```

Verify the installation:

```shell
node --version
```

Output:

```shell
v14.15.5
```

#### Install Node v12

Install the latest release of Node 12.

```
nvm install 12
```

Verify the installation:

```shell
node --version
```

Output:

```shell
v12.20.2
```

#### Install the latest version

```shell
nvm install node
```

### Switch between Node versions

You can switch between Node versions as follows:

```shell
nvm use 12.1.2
```

Or for a specific version of 12:

```shell
nvm use 12.4.0
```

Or the latest LTS version:

```shell
nvm use --lts
```

If a Node version is not available locally when switching, you will be prompted to install it.

__Note:__ NVM is not recommended for production environments. It should only be used during the development phase.

See [Node Version Manager on GitHub](https://github.com/nvm-sh/nvm) for more details.
