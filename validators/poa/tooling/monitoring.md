# Monitoring

The nodes are by default sending telemetry data \(can be disabled while deploying node\) to polkadot telemetry.

Dock will be adding itself to [Polkascan](https://polkascan.io/) for the mainnet. For the testnet, Dock will host a custom [Polkascan explorer](https://github.com/polkascan) just for itself.

To monitor other data like the network usage, CPU usage, disk usage, block production, number of connected peers, etc, [Prometheus](https://prometheus.io/) is used. Nodes by default make this data available at 127.0.0.1:9615 \(but can be overwritten with `allowPrometheusExt`\) and thus Prometheus interface can be configured to listen to that. In case, you have do not have Prometheus installed, it can be found [here](https://prometheus.io/download/). Once you have Prometheus running, configure it

```text
scrape_configs:
  # The job name is added as a label `job=dock-node` to any timeseries scraped from this config.
  - job_name: 'dock-node'

    # Override the global default and scrape targets from this job every 5 seconds.
    scrape_interval: 5s

    static_configs:
      - targets: ['<hostname:port of Substrate's Prometheus server.>']
```

Now the Prometheus UI will show various metrics prefixed with `substrate_`.

To visualize the above metrics on [Grafana](https://grafana.com/), import [this grafana dashboard](https://grafana.com/grafana/dashboards/11784). If you don't know how to import a dashboard, check [here](https://grafana.com/docs/grafana/latest/reference/export_import/#importing-a-dashboard).

