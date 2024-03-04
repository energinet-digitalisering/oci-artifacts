# Vertical Pod Autoscaler

A service that automatically adjusts the CPU and memory reservations for your pods to help them run more efficiently.

## Dependencies

- [Metrics Server](../infrastructure/metrics-server/README.md)

## CRDs

### VerticalPodAutoscaler

To enable the Vertical Pod Autoscaler, you need to create a `VerticalPodAutoscaler` resource for the target resource (e.g. `Deployment`, `StatefulSet`, `DaemonSet`).

```yaml
apiVersion: autoscaling.k8s.io/v1beta2
kind: VerticalPodAutoscaler
metadata:
  name: <vpa-name>
spec:
  targetRef:
    apiVersion: "apps/v1"
    kind: <Deployment | StatefulSet | DaemonSet>
    name: <target-name>
```

It is recommended that you include this resource as part of a component. For example if you have a component `k8s/redis` that deploys a Helm Chart with Kustomize, you can include the `VerticalPodAutoscaler` resource in the `k8s/redis` folder, and reference it in the  `k8s/redis/kustomization.yaml` file.
