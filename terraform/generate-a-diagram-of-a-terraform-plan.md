# Generate A Diagram Of A Terraform Plan

__Category: Terraform__

Terraform provides the ability to generate a visual representation of a plan in DOT (Graphviz) format. 

### Install Graphviz (Optional)

If required [install Graphviz](https://www.graphviz.org/download/) for your operating system.

On macOS:

```shell
brew install graphviz
```

On Linux (Ubuntu):

```shell
sudo apt install graphviz
```

On Windows using `winget`:

```shell
winget install graphviz
```

### Generate a DOT graph of the Terraform plan

Create a DOT graph file:

```shell
terraform graph -type=plan > infra-overview.dot
```

To convert the DOT graph to png:

```shell
dot -Tpng infra-overview.dot > infra-overview.png
```

### Generate an image of the Terraform plan

Alternatively, generate an image directly from DOT graph output:

```shell
terraform graph -type=plan | dot -Tpng -o infra-overview.png
```
