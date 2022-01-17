# Clean Yarn Cache

__Category: Nodejs__

Yarn stores every package in a global cache in your user directory on the file system. Over time, this directory will grow to gigabytes in size and may need to be purged to reclaim disk space.

To output a list of entries in the cache:

```shell
yarn cache list
```

To remove all entries in the cache:

```shell
yarn cache clean
```

__Note:__ Only clean the yarn cache if you are prepared to download required package dependencies again.

See [yarn cache](https://classic.yarnpkg.com/en/docs/cli/cache/) for more details.
