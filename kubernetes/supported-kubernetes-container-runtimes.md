# Supported Kubernetes Container Runtimes

__Category: Kubernetes__

Supported container runtimes in Kubernetes include:

* [Docker](https://docker.comz)
* [containerd](https://containerd.io/)
* [rkt](redhat.com/en/topics/containers/what-is-rkt)
* [CRI-O](https://cri-o.io) (Container Runtime Interface using OCI)

In Azure AKS, the default container runtime is `containerd` and is supported on both Linux and Windows worker nodes.

In Amazon EKS, the default container runtime is `containerd` and is supported on both Linux and Windows worker nodes.

__Note:__ Containerd has a smaller scope compared to the Docker runtime which helps improve security and pod startup latency. It also frees up additional CPU and memory for use by applications.
