# [cluster-name]

This repository contains the Kubernetes (K8s) manifests for the [cluster-name] cluster.

<!-- readme-tree start -->
 ```
 ```
 <!-- readme-tree end -->

## Requirements

- [KSail](https://github.com/devantler/ksail)
- [Docker](https://www.docker.com/)
- Linux or MacOS

## Usage

This repository serves as the source-of-truth for the [cluster-name] cluster. Any changes you make to the manifests in this repository will be pulled into your running clusters that are connected to this repository.

### Create your cluster environments

```bash
ksail init [name]-docker
ksail init [name]-sandbox
ksail init [name]-staging
ksail init [name]-production
```

### Provision the cluster in Docker

```bash
ksail up [name]-docker
```

### Share SOPS Keys

Now that you have created the first cluster, KSail has created a SOPS key on your system, that allows you to encrypt and decrypt secrets. You can find the key in:

- Linux: `$HOME/sops/age/keys.txt`
- macOS: `$HOME/Library/Application Support/sops/age/keys.txt`

In this file you will find a section that looks like this:

```txt
# KSAIL_SOPS_KEY start
# created: 2024-01-15T11:45:58+01:00
# public key: <public-key>
<private-key>
# KSAIL_SOPS_KEY end
```

You need to copy and share this section with your team members, who then need to add it to their `keys.txt` file.

> [!WARNING]
> The export and import features are not working yet, so you need to copy the keys manually for now.

Luckily, KSail has a command that helps you with this:

```bash
ksail sops --export <file-name>
ksail sops --import <file-name>
```

### Provision the cluster to a cloud provider

Azure:

- Create an Infrastructure as Code (IaC) repository from the [pulumi-aks-gitops-template](https://github.com/energinet-digitalisering/pulumi-aks-gitops-template) repository template, and follow the instructions in the README.md file to provision the infrastructure.
