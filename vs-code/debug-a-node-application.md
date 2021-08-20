# Debug A Node Application

__Category: VS Code__

Visual Studio Code provides the ability to debug a Node application. To do this, open a terminal in VSCode and launch the application as follows (substituting `server.js` for the name of your application entrypoint):

```
node --inspect server.js
```

Add a breakpoint to the code by right-clicking on the line you want to stop the debugger on and select "Add Inline Breakpoint" from the popup menu.