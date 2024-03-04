# Vertical Pod Autoscaler

A service that automatically adjusts the CPU and memory reservations for your pods to help them run more efficiently.

## Dependencies

- [Metrics Server](../infrastructure/metrics-server/README.md)

## CRDs

### VerticalPodAutoscaler

- `k8s/vertical-pod-autoscaler/configs/vpa.yaml`

This `VerticalPodAutoscaler` resource is used to enable Vertical Pod Autoscaling for a specific resource (e.g. `Deployment`, `StatefulSet`, `DaemonSet`).

| Variable        | Description                                                          |  Default   | Required |
| --------------- | -------------------------------------------------------------------- | :--------: | :------: |
| vpa-target-name | The name of the target resource                                      |            |    ✓     |
| vpa-api-version | The API version of the target resource                               |  apps/v1   |    ✕     |
| vpa-kind        | The kind of the target resource (Deployment, StatefulSet, DaemonSet) | Deployment |    ✕     |
