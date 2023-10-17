# What Are Library Container Directories

__Category: Mac__

Library container directories on macOS manage data and resources for applications. Container directories can be either system wide, or user-specific in multi-user environments.

Features of container directories:

* User-specific application data isolation using `~/Library/Containers/` where directories are organised by the app bundle identifier.
* Application specific container directories to prevent other apps from accessing or modifying data.
* Providing a place to store application-specific preference plist files.
* Providing a place to store application logs and diagnostic information.

Applications should store data in container directories to enhance security and privacy on macOS.
