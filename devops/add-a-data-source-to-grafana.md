# Add A Data Source To Grafana

__Category: DevOps__

Grafana can be configured to ingest data from various data sources. This TIL will add a Prometheus data source for `windows_exporter` being exposed on localhost.

### Configure a data source

Log into the Grafana console. 

From the left-hand menu select: Configuration -> Data sources.

Click "Add data source" and select Prometheus.

Enter the URL: https://localhost:9090 (or, if Prometheus is running in a Docker container, use the URL http://host.docker.internal:9090)

Enter a descriptive name.

Scroll down and press "Save & test".

### Create a dashboard 

This example is displaying data from the [windows_exporter](https://github.com/prometheus-community/windows_exporter) being processed by Prometheus.

From the left-hand menu select: Dashboards -> + Import.

Enter a dashboard ID of `14451` then press "Load". 

Select "Prometheus" as the Data Source then press "Import".

View the dashboard.
