# OpenTelemetry Operator

The OTEL Operator offers a vendor-agnostic implementation of a ControlPlane to create and manage OTEL related resources.

- [Documentation](https://opentelemetry.io/docs/kubernetes/helm/operator/)
- [Helm Chart](https://github.com/open-telemetry/opentelemetry-helm-charts/tree/main/charts/opentelemetry-operator)

## Preset Collectors

This OCI Artifact includes a set preconfigured collectors to make it easier to get started with telemetry collection.

These are configured to match the default preset configuration described in the [OTEL Collector's Getting Started guide for Kubernetes](https://opentelemetry.io/docs/kubernetes/getting-started/).

By default these presets do not include exporters, and will only export telemetry to standard out. For more advanced use cases, these OCI artifacts can be used as templates, or be patched with Kustomize.

> [!NOTE]
> In the future these collectors might be expanded to support exporting to popular backends.

### Kubernetes Cluster Telemetry

This collector is configured to receive cluster-wide metrics and events from a Kubernetes cluster. It runs a single replica in the cluster to avoid creating duplicates.

It has the following receivers configured:

- [Kubernetes Cluster Receiver](https://opentelemetry.io/docs/kubernetes/collector/components/#kubernetes-cluster-receiver)
- [Kubernetes Objects Receiver](https://opentelemetry.io/docs/kubernetes/collector/components/#kubernetes-objects-receiver)
- Prometheus - to scrape metrics from the OTEL Collector itself.

### Kubernetes Node Telemetry

This collector is configured to receive telemetry from all nodes. It runs as a DaemonSet, defaulting to one agent per node. It receives/scrapes on the following:

- Kubelet Stats (port 10250) - node, pod, container, and volume metrics from the KAPI server
- OTLP (port 4317/grpc and 4318/http) - Application telemetry and instrumentation
- Prometheus (port 8888) - the OTEL Collectors own metrics (its a list that can be expanded to scrape more targets)

To learn more about the different recievers visit the following links:

- [Kubelet Stats Receiver](https://opentelemetry.io/docs/kubernetes/collector/components/##kubeletstats-receiver)
- [OTLP Receiver](https://github.com/open-telemetry/opentelemetry-collector/blob/main/receiver/otlpreceiver/README.md)
- [Prometheus Receiver](https://github.com/open-telemetry/opentelemetry-collector-contrib/blob/main/receiver/prometheusreceiver/README.md)
