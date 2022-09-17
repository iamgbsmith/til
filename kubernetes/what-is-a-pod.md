# What Is A Pod

__Category: Kubernetes__

Containers are packaged into an object called a pod. A pod is the smallest deployable unit of computing that is created and managed in Kubernetes

Pods have the following characteristics:

* A pod represents a single instance of an app running in Kubernetes.
* Pod templates are written in YAML format and define the information about pods that run in a cluster including details on shared storage and network configuration.
* Containers in a pod share the same assigned IP address and are identified and grouped using string labels that are specified when defining a pod.
* A pod can hold a group of one or more containers however it should not contain multiple instances of the same app.
