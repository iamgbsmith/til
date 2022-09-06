# Control Plane Services

__Category: Kubernetes__

Kubernetes relies on several administrative services running on the control plane which manage communication, workload scheduling, and cluster persistence. 

The following services are used in a Kubernetes control plane:

* API Server - acts as a front-end to the control plane providing a way to communicate between components in a cluster. The `kubectl` command runs against the `kube-apiserver` API.
* Backing Store - a strongly consistent distributed key-value store based on [`etcd`](https://etcd.io) used to save the configuration and state of a Kubernetes cluster.
* Scheduler - the component which assigns workloads across all nodes and monitors the cluster for newly created containers to assign them to nodes.
* Controller Manager - launches and monitors the controllers configured for a cluster through the API server. Controllers track the state of objects in the cluster.
* Cloud Controller Manager - integrates with underlying cloud technologies in a cluster when the cluster is running in a cloud environment. This includes load balancers, queues, and storage.

__Note:__  Backup for `etcd` data in the backing store is the responsiblity of the Kubernetes cluster administrator.
