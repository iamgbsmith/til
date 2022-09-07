# Services That Run On A Kubernetes Node

__Category: Kubernetes__

Nodes in Kubernetes run the following services:

* Kubelet - an agent that runs on each node in the cluster and monitors work requests from the API server. The kubelet monitors a node and makes sure that the containers scheduled on each node run as expected.
* Kube-proxy - responsible for local cluster networking, ensuring the node has a unique IP address. It implements rules to handle routing and load balancing of traffic by using iptables and IPVS.
* Container runtime - the underlying software that runs containers on a Kubernetes cluster.
