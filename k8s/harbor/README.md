# Harbor

Harbor is an open-source cloud native registry that stores, signs, and scans container images for vulnerabilities.

- [Documentation](https://goharbor.io/docs/)
- [Helm Chart](https://github.com/goharbor/harbor-helm)

## Dependencies

- [Cert Manager](../cert-manager/README.md)
- An ingress controller
  - [Traefik](../traefik/README.md)

## Post-build variables

| Variable             | Description                     | Default | Required |
| -------------------- | ------------------------------- | :-----: | :------: |
| cluster_domain       | The domain of the cluster       |         |    ✓     |
| cluster_ingress_port | The port of the cluster ingress |   ""    |    ✕     |
