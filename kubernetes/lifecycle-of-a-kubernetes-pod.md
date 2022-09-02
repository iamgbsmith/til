# Lifecycle Of A Kubernetes Pod

__Category: Kubernetes__

A Kubernetes pod can be in one of five lifecycle phases and is controlled by submitting a pod YAML manifest to the cluster. 

Manifest files define the target state of the pod which is updated by the scheduler. Pods are started on  healthy nodes that have enough resources.

The five phases are as follows:

* Pending - the pod has been accepted by the cluster but is not ready to run (for example, a required container image needs to be downloaded before it will start).
* Running - the pod has been bound to a node are ready and containers have created. At least one container has transitioned to a running state.
* Succeeded - all containers in a pod have completed their intended task and terminated successfully.
* Failed - one or all containers in the pod have terminated in failure or were terminated by the system.
* Unknown - the state of the pod could not be determined.

A Pod's `status` field is a PodStatus object, which has a `phase` field.
