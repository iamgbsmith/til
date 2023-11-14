# Install Ruby Using RVM

`rvm` is a version manager for Ruby. 

Run the following command to install rvm on macOS:

```shell
\curl -sSL https://get.rvm.io | bash -s -- --version latest
```

Restart your shell. Confirm rvm is working:

```shell
rvm -v
```

To list installable Ruby versions:

```shell
rvm list known
```

Install a specific version of Ruby:

```shell
rvm install 3.0.4
```

Use a specific version of Ruby:

```shell
rvm use 3.0.4
```

Uninstall a specific version of Ruby:

```shell
rvm uninstall 3.0.4
```

## Problems with Ruby and OpenSSL

If you have problems installing a Ruby version due to missing OpenSSL packages, run the following to resolve to OpenSSL in /usr/local/opt:

```shell
rvm install 3.2.0 --with-openssl --with-openssl-lib=/usr/local/opt/openssl@1.1/lib --with-openssl-include=/usr/local/opt/openssl@1.1/include
```

## Uninstalling RVM

You can uninstall rvm with the following command:

```shell
rvm implode
```
