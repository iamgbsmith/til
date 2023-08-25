# Python Imports Cannot Be Resolved In VS Code

__Category: VS Code__

You may see the following error related to imports when running or debugging a Python application in VS Code with the Pylance plugin:

```shell
Import "flask_restful" could not be resolved Pylance(reportMissingImports)
```

To fix this problem, open the Command Palette using `Ctrl + Shift + P` and choose: "Python: Select Intepreter" to use the correct interpreter for the project. This will be the one with (recommended) next to it in the selection list.
