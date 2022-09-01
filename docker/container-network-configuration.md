# Container Network Configuration

__Category: Docker__

Docker provides three network configurations to choose from depending on your requirements. Bridge, Host, and none.

### Bridge 

* The default network configuration which is an internal, private network used by the container. The container network is isolated from Docker host network.
* Each container in the bridge network is assigned an IP address and subnet mask with the hostname defaulting to the container name.
* Containers connected to the default bridge network can ccess other bridge connected containers by IP address but not by hostname.
* Port mapping between the container and the host is achieved using the `--publish` flag. For example `--publish 8080:80` which allows clients to access the container at the host IP and port of 8080.

### Host

* Allows running of a container using the host network directly. 
* Applications running within a container can be accessed directly via their ports as opposed to a mapped port.
* Containers can only allocate ports which are unused by the host.

### None

* Disables networking for a container. No services or applications within the container are accessible via ports.
