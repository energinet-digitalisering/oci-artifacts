# OTEL Collector

The OpenTelemetry Collector offers a vendor-agnostic implementation of how to receive, process and export telemetry data. This manifest packages the OTEL Collector chart provided by the OpenTelemetry project.

- [Documentation](https://opentelemetry.io/docs/kubernetes/helm/collector/)
- [Helm Chart](https://github.com/open-telemetry/opentelemetry-helm-charts/tree/main/charts/opentelemetry-collector)

## Post-build variables

| Variable            | Description                                                                                                    |   Default   | Required |
| ------------------- | -------------------------------------------------------------------------------------------------------------- | :---------: | :------: |
| otel_collector_mode | Workload management strategy used for the OTEL Collector. Can be either daemonset, deployment, or statefulset. | "daemonset" |    ✕     |
