# Check For Outdated Dependencies

__Category: Nodejs__

You can check for outdated dependencies in a Node project `package.json` file by running the following command:

```shell
yarn outdated
```

The output from this command will contain a list of the packages using semver showing:

* The current installed version
* The recommended (wanted) version 
* The latest version.

Sample output from this command:

```shell
yarn outdated v1.22.4
info Color legend : 
 "<red>"    : Major Update backward-incompatible updates 
 "<yellow>" : Minor Update backward-compatible features 
 "<green>"  : Patch Update backward-compatible bug fixes
Package    Current Wanted Latest Package Type    URL                                                 
deep-equal 2.0.3   2.0.5  2.0.5  dependencies    https://github.com/inspect-js/node-deep-equal#readme
rollup     2.18.1  2.42.3 2.42.3 devDependencies https://rollupjs.org/                               
socket.io  2.3.0   2.4.1  4.0.0  dependencies    https://github.com/socketio/socket.io#readme        
✨  Done in 0.96s.
```

Always aim to upgrade to at least the wanted version for a package. Proceed with caution when upgrading to the latest version of a package as this may contain breaking changes.
