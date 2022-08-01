# Install Grafana Using Docker

__Category: DevOps__

Grafana is a multi-platform open source analytics and interactive visualization web application. It provides charts, graphs, and alerts for the web when connected to supported data sources.

Grafana can ingest data and visualise metrics, logs, and traces from multiple sources such as Prometheus, Loki, Elasticsearch, InfluxDB, and Postgres.

### Create a Docker volume for storing data

Create a volume for persistent data storage:

```shell
docker volume create grafana-data
```

### Run Grafana in a Docker container

Grafana open source version is based on Alpine Linux. 

Pull the latest Grafana container from Docker Hub:

```shell
grafana/grafana-oss
```

Start the Grafana container, specifying the Docker volume:

```shell
docker run -d -p 3000:3000 --name grafana --volume grafana-data grafana/grafana-oss
```

Browse to http://localhost:3000 and login with the admin user (default admin/admin). You will be prompted to change your password the first time you login.

See [Grafana](https://grafana.com) for more details.
