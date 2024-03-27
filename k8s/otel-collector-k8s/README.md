# OTEL Collector K8s

The OpenTelemetry Collector offers a vendor-agnostic implementation of how to receive, process and export telemetry data. The OTEL Collector Helm chart provided by the OpenTelemetry project includes configuration presets for easily setting up OTEL Collectors that can collect telemetry from a Kubernetes cluster.

This manifest packages the OTEL Collector Helm chart and installs two HelmReleases:

1) `otel-collector-node` which runs an instance on every Kubernetes node. This collector collects pod logs and Kubelet metrics
2) `otel-collector-cluster` which only has one instance. This collector collects cluster-level metrics and events.

- [Getting Started](https://opentelemetry.io/docs/kubernetes/getting-started/)
- [Documentation](https://opentelemetry.io/docs/kubernetes/helm/collector/)
- [Helm Chart](https://github.com/open-telemetry/opentelemetry-helm-charts/tree/main/charts/opentelemetry-collector)
