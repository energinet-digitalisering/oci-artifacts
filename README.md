# OCI Artifacts

> [! WARNING ]
> This repo is temporarily public, as Kustomize does not support pulling from OCI yet.


This repository contains Kubernetes (K8s) manifests distributed as OCI Artifacts.

- [Cert Manager](k8s/cert-manager/README.md)
- [Harbor](k8s/harbor/README.md)
- [Pulumi Operator](k8s/pulumi-operator/README.md)
- [Redis](k8s/redis/README.md)
- [Reloader](k8s/reloader/README.md)
- [Testkube](k8s/testkube/README.md)
- [Traefik](k8s/traefik/README.md)

OCI Artifacts are a great way to distribute ready-to-use K8s manifests. It requires almost no lines of code to get services deployed, so it can in some cases be a great alternative to Helm charts. However it does not have the same innate flexibility as Helm charts, so it is not a replacement for Helm charts. So the main reason to use OCI Artifacts is to get a service deployed with as little effort as possible. It might not work for advanced use-cases, but for simple (most) use-cases it will make your life easier.

<!-- readme-tree start -->
 ```
 ```
 <!-- readme-tree end -->

## Requirements

- [KSail](https://github.com/devantler/ksail)
- [Docker](https://www.docker.com/)
- Linux or MacOS

## Usage

This repository serves as the source-of-truth for the OCI Artifacts.

### Reference an OCI Artifact with Kustomize

> [! NOTE ]
> Pulling K8s manifest over OCI is not supported by Kustomize yet. There is [an active Pull Request](https://github.com/kubernetes-sigs/kustomize/pull/5147) that will add support for this. Until then, we can use Git over HTTP to reference the OCI Artifact.

To reference an OCI Artifact with Kustomize, you need to add the following to your `kustomization.yaml` files that you want to reference the OCI Artifact and its configurations from:

```yaml
# Service deployments
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization
resources:
  # To reference a service you use the following syntax:
  - https://github.com/energinet-digitalisering/oci-artifacts//k8s/[serviceName]?ref=[refName]

---
# Config deployments
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization
resources:
  # To reference a config you use the following syntax:
  - https://raw.githubusercontent.com/energinet-digitalisering/oci-artifacts/[refName]/k8s/[serviceName]/[pathToConfigYamlFile]
```

Where `[serviceName]` is the name of the OCI Artifact you want to reference, and `[refName]` is the name of the branch or tag you want to pull the OCI Artifact from. If you want to reference a config file, you also need to specify the [pathToConfigYamlFile] which is the path to the yaml file relative to the OCI Artifact folder. For example `cert-manager/certificates/cluster-issuer-certificate.yaml`, if you want to pull the cluster issuer certificate provided by the cert-manager OCI Artifact

### Setting variables for OCI Artifacts

Some of the OCI Artifacts require you to provide some variables to configure the service. You can do this by adding the variables to your variables files in the `k8s/clusters/[clusterName]/variables` folder in your own clusters repo. As the references are http, you can fairly easily decode where to look for the possible variables. For example, if you want to reference the `traefik` service, you can find the variables in the `k8s/traefik/*.yaml` files in this repository.

### Patching OCI Artifacts

Some OCI Artifacts might not meet your expectations out-of-the-box. In this case, you can patch the OCI Artifact by adding patches to your `kustomization.yaml` file that references the OCI Artifact. For example, if you want to patch the `traefik` service, you would add the following to your `kustomization.yaml` file:

```yaml
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization
resources:
  # To reference a service you use the following syntax:
  - https://github.com/energinet-digitalisering/oci-artifacts//k8s/traefik?ref=v0.0.3

patches:
  # To patch a service with a patch file you use the following syntax:
  - path: traefik-patch.yaml
    target:
      kind: HelmRelease
      name: traefik
      namespace: traefik
  # To inline patch a service you use the following syntax:
  - patch: |-
      - op: replace
        path: /some/existing/path
        value: new value
    target:
      kind: HelmRelease
      name: traefik
      namespace: traefik
```

This allows you full control over the OCI Artifacts, but if you require a lot of patches, you might want to consider contributing to the OCI Artifact to make it more flexible, or copying the OCI Artifact into your own clusters repo and configure it there.

## Contributing

The OCI Artifacts repo is owned by the Digital Incubator, and as such it is the teams in the Digital Incubator that are responsible for maintaining the OCI Artifacts. However, we welcome contributions from anyone. If you want to contribute, please create issues or pull requests in this repository and we will take a look at it.
