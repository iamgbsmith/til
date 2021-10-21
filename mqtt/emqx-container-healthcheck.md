# EMQX Container Healthcheck

__Category: MQTT__

[EMQ X](https://www.emqx.io) is an Erlang MQTT broker designed for low-latency message routing between IoT physical network device deployments at scale.

Out-of-the-box, the `beam.smp` process in EMQ X can cause CPU spikes up to 100% for short bursts in a container deployment if using the default healthcheck process.

A more performant way of checking the container health for the EMQ X broker is to call the `/status` endpoint using curl.

When building the EMQ X container ensure the curl dependency is included:

```shell
# add run deps, never remove - ADD curl for healthcheck
&& apk add --no-cache --virtual .run-deps \
    ncurses-terminfo-base \
    ncurses-terminfo \
    ncurses-libs \
    readline \
    curl \
```

If you are incorporating the healtcheck into the container, include the following in the Dockerfile:

```shell
HEALTHCHECK --interval=1m --timeout=10s --retries=3 CMD curl -f http://localhost:8080/status
```

Alternatively, call the `/status` endpoint when performing a healthcheck from your container orchestration engine.
