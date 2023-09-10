# Get CPU Temperature And Thermal Information

__Category: Mac__

You can obtain CPU temperature and thermal information for your Mac from the command line as follows:

```shell
sysctl machdep.xcpm.cpu_thermal_level
```

Sample output:

```shell
machdep.xcpm.cpu_thermal_level: 60
```

To show more detailed information including fan speed (RPM) and CPU die temperature:

```shell
sudo powermetrics --samplers smc
```

Sample output:

```shell
**** SMC sensors ****

CPU Thermal level: 36
IO Thermal level: 0
Fan: 1228.98 rpm
CPU die temperature: 64.88 C
CPU Plimit: 0.00
GPU Plimit (Int): 0.00 
Number of prochots: 0
```
