# Testkube

TestKube is a service that allows you to run tests on your Kubernetes cluster.

- [Documentation](https://docs.testkube.io)
- [Helm Chart](https://github.com/kubeshop/helm-charts/tree/develop/charts/testkube)

## Post-build variables

| Variable                               | Description                   | Default | Required |
| -------------------------------------- | ----------------------------- | :-----: | :------: |
| **Configuration**                      |                               |         |          |
| **Resource Resquests and Limits**      |                               |         |          |
| testkube_minio_cpu_request             | Minio CPU request             |  `50m`  |    ✕     |
| testkube_minio_memory_request          | Minio memory request          | `50Mi`  |    ✕     |
| testkube_minio_cpu_limit               | Minio CPU limit               | `100m`  |    ✕     |
| testkube_minio_memory_limit            | Minio memory limit            | `150Mi` |    ✕     |
| testkube_mongodb_cpu_request           | MongoDB CPU request           | `150m`  |    ✕     |
| testkube_mongodb_memory_request        | MongoDB memory request        | `100Mi` |    ✕     |
| testkube_mongodb_cpu_limit             | MongoDB CPU limit             | `300m`  |    ✕     |
| testkube_api_cpu_request               | API CPU request               | `200m`  |    ✕     |
| testkube_api_memory_request            | API memory request            | `200Mi` |    ✕     |
| testkube_api_cpu_limit                 | API CPU limit                 | `200m`  |    ✕     |
| testkube_api_memory_limit              | API memory limit              | `200Mi` |    ✕     |
| testkube_dashboard_cpu_request         | Dashboard CPU request         |  `25m`  |    ✕     |
| testkube_dashboard_memory_request      | Dashboard memory request      | `25Mi`  |    ✕     |
| testkube_dashboard_cpu_limit           | Dashboard CPU limit           |  `50m`  |    ✕     |
| testkube_dashboard_memory_limit        | Dashboard memory limit        | `50Mi`  |    ✕     |
| testkube_operator_cpu_request          | Operator CPU request          |  `25m`  |    ✕     |
| testkube_operator_memory_request       | Operator memory request       | `25Mi`  |    ✕     |
| testkube_operator_cpu_limit            | Operator CPU limit            |  `50m`  |    ✕     |
| testkube_operator_memory_limit         | Operator memory limit         | `50Mi`  |    ✕     |
| testkube_operator_proxy_cpu_request    | Operator Proxy CPU request    |  `25m`  |    ✕     |
| testkube_operator_proxy_memory_request | Operator Proxy memory request | `25Mi`  |    ✕     |
| testkube_operator_proxy_cpu_limit      | Operator Proxy CPU limit      |  `50m`  |    ✕     |
