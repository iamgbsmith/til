# Create A Swarm

The steps outlined here will create a Docker Swarm Manager and Swarm Network ready to deploy services to.

Initialise the Swarm Manager:

```
docker swarm init
```

Output 

```
Swarm initialized: current node (2nhrsjo9kmfku49chbvpjrx3l) is now a manager.

To add a worker to this swarm, run the following command:

    docker swarm join --token SWMTKN-1-06h53q2zo0guv90z8i22qa2bo4bq4ua01nlt6b16hhzn4mznpg-61safdie7gzli42p0161isf4f 192.168.65.3:2377

To add a manager to this swarm, run 'docker swarm join-token manager' and follow the instructions.
```

Nodes in a network are connected using an overlay network driver which creates a distributed network among multiple Docker daemon hosts.

Create the Swarm Overlay Network using:

```
docker network create -d overlay my-swarm-network
```

```
pu7428wt7ks1d8lhuqd2bs0b6
```

If you need to list networks, run the following command:

```
docker network ls
```

Output

```
NETWORK ID          NAME                DRIVER              SCOPE
ab2fff7ddd84        bridge              bridge              local
pu7428wt7ks1        my-swarm-network    overlay             swarm
09e5a9d66c8f        docker_gwbridge     bridge              local
6b415caa2017        host                host                local
vley4zfnoxnr        ingress             overlay             swarm
c0d3fc16a155        none                null                local
```

If this is a standalone single-node topology, the above will be suffient enough for you to start creating images and deploying containers.