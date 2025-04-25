# Get GPU Information And Metrics

__Category: Mac__

You can get GPU information and metrics on macOS using the `powermetrics` command line utility. `sudo` is required to launch it.

To print details on GPU usage every 2 seconds:

```shell
sudo powermetrics --samplers gpu_power -i2000
```

To print details on GPU usage every 500 milliseconds, 20 times in total:

```shell
sudo powermetrics --samplers gpu_power -i500 -n20
```
