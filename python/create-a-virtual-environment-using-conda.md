# Create A Virtual Environment Using Conda

__Category: Python__

Conda (anaconda) provides isolated Python environments which are cleaner than installing packages system-wide. Virtual environments prevent dependency conflicts and also let you install packages without root privileges.

Install Anaconda using a package manager. For example on macOS:

```shell
brew install anaconda
```

__Launch a new shell for path settings to take effect.__

Create a new virtual environment by choosing a Python version:

```shell
conda create -n py311-myenvironment python=3.11 -y
```

Activate the virtual environment:

```shell
conda activate py311-myenvironment
```

When you have finished, deactivate the virtual environment:

```shell
conda deactivate
```

Python commands including `pip` will work from your newly created virtual environment.
