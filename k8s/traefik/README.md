# Traefik

Traefik is a reverse proxy and load balancer that routes incoming requests to the correct backend service. It is used as an ingress controller in Kubernetes clusters.

- [Documentation](https://doc.traefik.io/traefik/)
- [Helm Chart](https://github.com/traefik/traefik-helm-chart)

## Dependencies

- [Cert Manager](../cert-manager/README.md)
  - Cluster Issuer
  - Cluster Issuer Certificate
    - Its secret must be named `cluster-issuer-certificate-tls`

## Post-build variables

| Variable                         | Description                            | Default |
| -------------------------------- | -------------------------------------- | :-----: |
| traefik_ingress_load_balancer_ip | The IP address of the load balancer    |   ""    |
| cluster_domain                   | The domain of the cluster              |   ""    |
| traefik_cpu_request              | The CPU request for the Traefik pod    |  100m   |
| traefik_memory_request           | The memory request for the Traefik pod |  50Mi   |
| traefik_cpu_limit                | The CPU limit for the Traefik pod      |  200m   |
| traefik_memory_limit             | The memory limit for the Traefik pod   |  100Mi  |
