# Benchmark Disk Write Performance

__Category: Mac__

You can benchmark disk write performance. 

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
8000+0 records in
8000+0 records out
8388608000 bytes transferred in 5.477342 secs (1606850002 bytes/sec)
```

Converting the above result in bytes/sec results in throughput of 1606.85 megabytes/sec.

Delete the temporary file:

```shell
rm test.file
```
