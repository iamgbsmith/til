# Container States In Kubernetes

__Category: Kubernetes__

Containers in Kubernetes can be in one of three states:

* Waiting - a container is performing the operations needed to start up (for example, pulling the container image from a container registry or applying secret data).
* Running - a container is executing without issues.
* Terminated - a container either ran to completion or failed for some reason.
