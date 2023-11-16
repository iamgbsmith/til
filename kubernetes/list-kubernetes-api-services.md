# List Kubernetes API Services

__Category: Kubernetes__

You can list API services provided by your Kubernetes host with `kubectl` as follows:

```shell
kubectl get apiservices
```

Sample output

```shell
NAME                                   SERVICE   AVAILABLE   AGE
v1.                                    Local     True        60m
v1.admissionregistration.k8s.io        Local     True        60m
v1.apiextensions.k8s.io                Local     True        60m
v1.apps                                Local     True        60m
v1.authentication.k8s.io               Local     True        60m
v1.authorization.k8s.io                Local     True        60m
v1.autoscaling                         Local     True        60m
v1.batch                               Local     True        60m
v1.certificates.k8s.io                 Local     True        60m
v1.coordination.k8s.io                 Local     True        60m
v1.discovery.k8s.io                    Local     True        60m
v1.events.k8s.io                       Local     True        60m
v1.networking.k8s.io                   Local     True        60m
v1.node.k8s.io                         Local     True        60m
v1.policy                              Local     True        60m
v1.rbac.authorization.k8s.io           Local     True        60m
v1.scheduling.k8s.io                   Local     True        60m
v1.storage.k8s.io                      Local     True        60m
v1beta2.flowcontrol.apiserver.k8s.io   Local     True        60m
v1beta3.flowcontrol.apiserver.k8s.io   Local     True        60m
v2.autoscaling                         Local     True        60m
```

Services which start with `v1.`, `v2.` are considered stable. 

__Do not use any beta services for production workloads.__
