# Traefik

Traefik is a reverse proxy and load balancer that routes incoming requests to the correct backend service. It is used as an ingress controller in Kubernetes clusters.

## Dependencies

- [Cert Manager](../cert-manager/README.md)
  - Cluster Issuer
  - Cluster Issuer Certificate
    - Its secret must be named `cluster-issuer-certificate-tls`

## Post-build variables

| Variable                         | Description                         | Default |
| -------------------------------- | ----------------------------------- | :-----: |
| traefik_ingress_load_balancer_ip | The IP address of the load balancer |   ""    |
| cluster_domain                   | The domain of the cluster           |   ""    |
