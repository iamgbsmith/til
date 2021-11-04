# Setup An IPFS Node

__Category: Blockchain__

The steps outlined here will install and configure an IPFS node on Ubuntu Linux (Raspbian for ARMv7). The process is similar for other Linux distros.

### Install IPFS

Identify the IPFS version to install from https://dist.ipfs.io/#go-ipfs

Switch to the `/tmp` directory and download the Linux binary:

```shell
wget https://dist.ipfs.io/go-ipfs/v0.10.0/go-ipfs_v0.10.0_linux-arm.tar.gz
```

Extract the file:

```shell
tar -xvzf go-ipfs_v0.10.0_linux-arm.tar.gz
```

Change to the `go-ipfs` directory and run the install script:

```shell
cd go-ipfs
sudo bash install.sh
```

Validate that IPFS has installed correctly:

```shell
ipfs --version
```

Output:

```shell
ipfs version 0.10.0
```

### Initialise nodes

Create the IPFS repository:

```shell
ipfs init
```

The output from this command will be the peer identity (which is also known as the node ID).

```shell
generating ED25519 keypair...done
peer identity: 12D3KooWCvpAR8hKpAnBMiTBDVyKhXLtkRckJ9kxDKe3PkjZQNGj
initializing IPFS node at /home/pi/.ipfs
to get started, enter:

	ipfs cat /ipfs/QmQPeNsJPyVWPFDVHb77w8G42Fvo15z4bG2X8D2GhfbSXc/readme
```

### Start the node

__Do not follow these steps if you want to configure a private IPFS network.__

The following steps will start an IPFS node and make it publicly accessible. 

Open another terminal and start the IPFS daemon:

```shell
ipfs daemon
```

Sample output:

```shell
Initializing daemon...
go-ipfs version: 0.10.0
Repo version: 11
System version: arm/linux
Golang version: go1.16.8
Swarm listening on /ip4/127.0.0.1/tcp/4001
Swarm listening on /ip4/127.0.0.1/udp/4001/quic
Swarm listening on /ip4/192.168.68.80/tcp/4001
Swarm listening on /ip4/192.168.68.80/udp/4001/quic
Swarm listening on /ip6/::1/tcp/4001
Swarm listening on /ip6/::1/udp/4001/quic
Swarm listening on /p2p-circuit
Swarm announcing /ip4/127.0.0.1/tcp/4001
Swarm announcing /ip4/127.0.0.1/udp/4001/quic
Swarm announcing /ip4/192.168.68.80/tcp/4001
Swarm announcing /ip4/192.168.68.80/udp/4001/quic
Swarm announcing /ip6/::1/tcp/4001
Swarm announcing /ip6/::1/udp/4001/quic
API server listening on /ip4/127.0.0.1/tcp/5001
WebUI: http://127.0.0.1:5001/webui
Gateway (readonly) server listening on /ip4/127.0.0.1/tcp/8080
Daemon is ready
```

From another terminal, show the status of the network:

```shell
ipfs swarm peers
```

Sample output:

```shell
/ip4/101.231.135.211/udp/4662/quic/p2p/12D3KooWA6AUMZrJ2FkRaXG1cCFAkTyKAdbeN4Jxk2g1EVcHSRPQ
/ip4/101.231.135.211/udp/4663/quic/p2p/12D3KooWAgR8XZpubTiLHbs5e2HczvpyahgGCTjyReqvaYNm6neu
/ip4/101.231.135.211/udp/4664/quic/p2p/12D3KooWHeNKKH8WLEa5tSxKa426ZjdTa792K2QJwQ7Dzvn9Loe4
```

If you have installed the IPFS WebUI, browse to http://hostname:5001/webui and view the status of your node such as connected peers and files being stored.
