# Placement Constraints With Swarm

Docker Swarm will attempt to run containers across nodes to provide maximum resiliency and availability. For example, if you specify two replicas of a container then it will try and run them on two different nodes within a swarm using placement constraints. Only when resources are unavailable will two containers be placed on the same node in the swarm.

Sometimes it may be necessary to specify which node a container is run on. For example, a container that monitors and reports on the Swarm state should be run on a manager node in order to get the data it needs or use a Docker volume. 

Databases that cannot be horizontally partitioned typically use a single data store and should be deployed to a specific node in the swarm.

### Specifying placement constraints

An container image can be run on specific nodes using constraints. For example on a specific host:

```yaml
placement:
  constraints: [node.hostname == foo.bar.com]
```

Or on a manager node:

```yaml
placement:
  constraints: [node.role == manager]
```

To use a label for placement constraints:

```yaml
placement:
  constraints: [node.labels.web == true]
```

Labels can be added to a node. List nodes using the following command:

```bash
docker node ls
```

```bash
ID                            HOSTNAME            STATUS              AVAILABILITY        MANAGER STATUS      ENGINE VERSION
x2v4tvhqadyovjjnn5hwku5iw     ip-172-26-1-98      Ready               Active                                  18.09.0
1ovulgnezf0tgw0th05y2qv97 *   ip-172-26-6-144     Ready               Active              Leader              18.09.0
```

To add a label to a node, issue the following command from the swarm manager node:

```bash
docker node update --label-add web=true ip-172-26-1-98
```

List labels applied to a node as follows:

```bash
docker node inspect --format '{{ .Spec.Labels }}' ip-172-26-1-98
```

Results in the following output:

```bash
map[web:true]
```

To remove a label:

```bash
docker node update --label-rm web ip-172-26-1-98
```

### Using placement constraints

In your Docker compose file, use the `placement` value with `constraints` based on any labels which have been manually created:

```yaml
web:
  image: orbiks/web-container:0.4.7
  deploy:
    replicas: 2
    placement:
      constraints: [node.labels.web == true ]
```