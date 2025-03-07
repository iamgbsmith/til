# Install Homebrew

__Category: Mac__

Homebrew is a package manager for macOS. 

Install as follows (you may be prompted for `sudo` access):

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Add brew to your path:

```shell
echo >> /Users/gregsmith/.zprofile
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/gregsmith/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

Confirm the installed version:

```shell
brew --version
```
