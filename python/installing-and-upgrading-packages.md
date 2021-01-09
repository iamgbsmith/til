# Installing And Upgrading Packages

__Category: Python__

Python packages can be installed using `pip`.

For example, to install the `requests` package:

```shell
pip install requests
```

To install a specific version:

```shell
pip install requests==2.24.0
```

To upgrade a package use the `--upgrade` flag:

```shell
pip install requests --upgrade
```

To list installed packages (showing outdated ones):

```shell
pip list --outdated
```

To show details about a specific packages:

```shell
pip show requests
```

Uninstall a specific package:

```shell
pip uninstall requests
```

See [pip - The Python Package Installer](https://pip.pypa.io/en/stable/) for more details.
