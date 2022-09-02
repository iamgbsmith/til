# Windows Workloads In Kubernetes

__Category: Kubernetes__

While you can only run a Kubernetes control plane on Linux, you can deploy worker nodes running either Windows or Linux.

Microsoft offer several images that can be used as a base layer for Windows containers:

* Windows - contains the full set of Windows APIs and system services excluding server roles.
* Windows Server - contains the full set of Windows APIs and system services.
* Windows Server Core - a smaller image that contains a subset of the Windows Server APIs and the full .NET framework. Also includes most server roles.
* Nano Server - the smallest Windows Server image which provides support for .NET Core APIs and some server roles.

Official images for .NET containers can be found at [Docker Hub](https://hub.docker.com/_/microsoft-dotnet)
