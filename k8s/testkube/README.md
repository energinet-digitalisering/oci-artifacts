# Testkube

TestKube is a service that allows you to run tests on your Kubernetes cluster.

- [Documentation](https://docs.testkube.io)
- [Helm Chart](https://github.com/kubeshop/helm-charts/tree/develop/charts/testkube)

## Post-build variables

| Variable             | Description               | Default | Required |
| -------------------- | ------------------------- | :-----: | :------: |
| cluster_domain       | The domain of the cluster |   ""    |    ✓     |
| cluster_ingress_port | The port of the ingress   |   ""    |    ✕     |
