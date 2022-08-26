# Get The Time It Takes To Run A Command

__Category: Linux__

You can get how long it takes to run a command with `time`.

For example, to show how long it takes to clone a GitHub repo:

```shell
time git clone https://github.com/iamgbsmith/react-wordle.git boardle
```

Output

```shell
Cloning into 'boardle'...
remote: Enumerating objects: 127, done.
remote: Counting objects: 100% (127/127), done.
remote: Compressing objects: 100% (115/115), done.
remote: Total 127 (delta 11), reused 124 (delta 8), pack-reused 0
Receiving objects: 100% (127/127), 4.36 MiB | 5.42 MiB/s, done.
Resolving deltas: 100% (11/11), done.

real	0m2.169s
user	0m0.164s
sys     0m0.168s
```

* `real` refers to actual elapsed time
* `user` is the amount of CPU time spent in user-mode code (outside the kernel) 
* `sys` is the amount of CPU time spent in the kernel within the process

The `time` command also works similarly on macOS.
