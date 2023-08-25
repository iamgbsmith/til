# Create A Dev Containers Project

__Category: VS Code__

Dev Containers (also known as remote containers) allow you to run a development project inside a container with minimal setup and configuration.

Pre-requisites:

* Ensure you have installed Docker Desktop and it is running.
* Install the Remote Containers extension for VS Code.

### Create dev container files

From the command palette select: `Remote-Containers: Add Development container Configuration Files`. This will create the following:

* A directory in the root of your project called `.devcontainer`
* The file `devcontainer.json` and a `Dockerfile` in the `/.devcontainer` directory.

These files should be added to version control.

Populate the Dockerfile with the required configuration to build and run the container.

### Run your project

From the command palette, select `Remote-containers: Rebuild and Reopen in Container` to build and connect to the Dev container. You will see the Terminal running your container. From there you can run the setup commands to install the required dependencies into your locally running container.

For example, for a running python Dev container:

`pip3 install --user -r requirements.txt`

Followed by:

`python app-py`

See [Developing inside a Container](https:///code.visualstudio.com/docs/remote/containers) for more details.
