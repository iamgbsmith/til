# Show Installed Version Of Kubernetes

__Category: Kubernetes__

You can show the installed version of Kubernetes using `kubectl`.

To show the client version:

```shell
kubectl version --client
```

To show the server version:

```shell
kubectl version --server
```

For more verbose output use the `--output=yaml` or `--output=json` flag. For example:

```shell
kubectl version --output=yaml
```

Sample output:

```
clientVersion:
  buildDate: "2023-11-15T16:58:22Z"
  compiler: gc
  gitCommit: bae2c62678db2b5053817bc97181fcc2e8388103
  gitTreeState: clean
  gitVersion: v1.28.4
  goVersion: go1.20.11
  major: "1"
  minor: "28"
  platform: darwin/amd64
kustomizeVersion: v5.0.4-0.20230601165947-6ce0bf390ce3
serverVersion:
  buildDate: "2023-10-18T11:33:18Z"
  compiler: gc
  gitCommit: a8a1abc25cad87333840cd7d54be2efaf31a3177
  gitTreeState: clean
  gitVersion: v1.28.3
  goVersion: go1.20.10
  major: "1"
  minor: "28"
  platform: linux/amd64
```

