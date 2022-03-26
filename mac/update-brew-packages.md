# Update Brew Packages

__Category: Mac__

Packages installed with Brew should be periodically updated. To show which packages are out-of-date run the following command:

```shell
brew outdated
```

Example output:

```
adns (1.5.1) < 1.6.0
aom (3.2.0_2) < 3.3.0
cmake (3.15.4) < 3.22.3
python@3.9 (3.9.9) < 3.9.10
[etc...]
webp (1.2.1_1) < 1.2.2
yarn (1.22.17_2) < 1.22.18
zstd (1.5.0) < 1.5.2
asset-catalog-tinkerer (2.5.1) != 2.7
```

Update a specific package:

```shell
brew upgrade [package_name]
```

Update all packages as follows:

```shell
brew upgrade
```
