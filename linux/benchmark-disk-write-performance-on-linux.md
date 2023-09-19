# Benchmark Disk Write Performance On Linux

__Category: Linux__

You can benchmark disk write performance on Linux using the `dd` command. 

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
5242880000 bytes (5.2 GB, 4.9 GiB) copied, 5.49167 s, 955 MB/s
```

Delete the temporary file:

```shell
rm test.file
```
