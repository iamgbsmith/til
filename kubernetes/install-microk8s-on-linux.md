# Install MicroK8s on Linux

__Category: Kubernetes__

Install MicroK8s as follows:

```shell
sudo snap install microk8s --classic
```

Check the node is ready:

```shell
microk8s status --wait-ready
```

Access the Kubernetes dashboard:

```shell
microk8s dashboard-proxy
```

### Enable or disable services

You can enable a service or list of services

```shell
microk8s enable dashboard dns istio registry
```

To disable a service, specify the service name(s):

```shell
microk8s disable registry
```

### Start or stop MicroK8s

```shell
microk8s start
```

```shell
microk8s stop
```
