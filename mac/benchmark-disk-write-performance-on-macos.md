# Benchmark Disk Write Performance On MacOS

__Category: Mac__

You can benchmark disk write performance on macOS using the `dd` command. 

Create a temp directory:

```shell
mkdir benchmark && cd benchmark/
```

Write to a temporary file called `test.file`:

```shell
dd if=/dev/zero of=test.file bs=1M count=5000
```

Output:

```shell
5000+0 records in
5000+0 records out
5242880000 bytes transferred in 3.346387 secs (1566728534 bytes/sec)
```

Converting the above result in bytes/sec results in throughput of 1566.7 megabytes/sec.

Delete the temporary file:

```shell
rm test.file
```
