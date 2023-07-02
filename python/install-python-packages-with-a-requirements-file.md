# Install Python Packages With A Requirements File

__Category: Python__

Multiple packages for a Python project can be installed using a `requirements.txt` file as an alternative to using the `pip install` command. This approach should be used to effectively manage dependencies for a project.

For example, add package dependencies to `requirements.txt` as follows:

```text
flask-restful >= 0.3.8
torch >=2.0.0
transformers >= 4.27.4
```

Run the following command to install the packages using requirements.txt:

```shell
pip install -r requirements.txt
```

__Note:__ If you encounter the following error on macOS:

```shell
-bash: [...] bad interpreter: No such file or directory
```

Install the packages using requirements.txt as follows:

```shell
python3 -m pip install -r requirements.txt
```
