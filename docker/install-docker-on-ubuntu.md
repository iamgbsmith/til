# Install Docker On Ubuntu

The process outlined here will install Docker on Ubuntu and configure a non-root user account with permissions required to run Docker containers.

### Install Docker

First, update the packages list: 

```shell
sudo apt update
```

Upgrade your system:

```shell
sudo apt upgrade
```

Reboot the server.

Next, install the dependencies necessary to enable a new repository over HTTPS. When prompted, keep the local version of files.

```shell
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

Import the repository’s GPG key using `curl`:

```shell
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

Add the Docker APT repository to your system’s software repository list:

```shell
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

Update the apt package list and install the latest version of Docker CE (Community Edition):

```shell
sudo apt update
sudo apt install docker-ce
```

Check the Docker version:

```shell
docker -v
Docker version 18.09.0, build 4d60db4
```

Log out and log back into the server (type the exit command).

### Configure user account to run Docker

By default, managing Docker requires administrator privileges. To run Docker commands as a non-root user without prepending sudo, you need to add your user to the docker group which is created during the installation of the Docker CE package. Do this as follows:

```shell
sudo usermod -aG docker $USER
```

`$USER` is an environment variable that holds the username of the logged in user.

Log out and back in to refresh the group membership.