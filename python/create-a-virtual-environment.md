# Create A Virtual Environment

__Category: Python__

Tools like `virtualenv` and `virtualenvwrapper` provide isolated Python environments which are cleaner than installing packages system-wide. Virtual environments prevent dependency conflicts and also let you install packages without root privileges.

Create a new virtual environment by choosing a Python interpreter and making a `./venv` directory for it:

```shell
python3 -m venv ./venv
```

Activate the virtual environment:
```
source ./venv/bin/activate
```

Ensure `pip` is up to date:
```shell
pip3 install -U pip
```

You can then start installing packages using `pip3 install <package-name>`.
