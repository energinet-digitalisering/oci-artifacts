# Loki

Loki is a horizontally scalable, highly available, multi-tenant log aggregation system inspired by Prometheus.

These manifests wrap the Loki Helm chart, which is recommended by Grafana for loads up to a few TBs of logs per day. However, the default configuration provided runs Loki in single-binary mode, which is not recommended for loads of more than 20 GBs per day. For production setups, you will also want to configure storage yourself.

- [Documentation](https://grafana.com/docs/loki/latest/setup/install/helm/)
- [Helm Chart](https://github.com/grafana/loki/blob/main/production/helm/loki/values.yaml)
