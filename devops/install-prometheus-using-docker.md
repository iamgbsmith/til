# Install Prometheus Using Docker

__Category: DevOps__

Prometheus is an open-source systems monitoring and alerting toolkit which is used to provide insights into application and operating system performance.

Prometheus collects and stores its metrics as time series data. Metrics information is stored with the timestamp at which it was recorded, alongside optional key-value pairs called labels. Data can be exported using "Exporters" for ingestion into other systems such as Grafana for observability.

### Run Prometheus in a Docker container

Pull the latest Prometheus container from Docker Hub:

```shell
docker pull prom/prometheus
```

Create a config file called `prometheus.yml` for bootstrapping Prometheus:

```yaml
global:
  scrape_interval:     15s
  evaluation_interval: 15s

alerting:
  alertmanagers:
    - static_configs:
        - targets:
          # - alertmanager:9093

rule_files:
  # - "first.rules"
  # - "second.rules"

scrape_configs:
  - job_name: prometheus
    static_configs:
      - targets: ['localhost:9090']

      
- job_name: "wmi-exporter"
    # metrics_path defaults to '/metrics'
    # scheme defaults to 'http'.

    static_configs:
      # target is the IP address of the source system which is exporting metrics
      - targets: ['192.168.68.69:9182'] 
```

The above is a sample. Customise based on your requirements.

Start the Prometheus container using the config file:

```shell
docker run -d --name=prometheus -p 9090:9090 -v /path/to/prometheus.yml:/etc/prometheus/prometheus.yml prom/prometheus --config.file=/etc/prometheus/prometheus.yml
```

Confirm Prometheus is running by browsing to http://localhost:9090/targets/

See [Prometheus Overview](https://prometheus.io/docs/introduction/overview) for more details.
