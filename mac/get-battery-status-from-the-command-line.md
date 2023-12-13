# Get Battery Status From The Command Line

__Category: Mac__

You can show the status of your MacBook battery from the command line using the following command:

```shell
pmset -g batt
```

Sample output when running on AC power:

```shell
Now drawing from 'AC Power'
 -InternalBattery-0 (id=6946915)	63%; charging; 1:28 remaining present: true
```

Sample output when running on battery power:

```shell
Now drawing from 'Battery Power'
 -InternalBattery-0 (id=6946915)	65%; charging; 0:00 remaining present: true
```
