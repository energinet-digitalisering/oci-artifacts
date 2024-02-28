# Redis

Redis is a key-value store that can be used as a database, cache, or message broker.

- [Documentation](https://redis.io/documentation)
- [Helm Chart](https://artifacthub.io/packages/helm/bitnami/redis)

## Post-build variables

| Variable                         | Description                                 | Default | Required |
| -------------------------------- | ------------------------------------------- | :-----: | :------: |
| **Configuration**                |                                             |         |          |
| redis_password                   | The password for the Redis instance         |         |    ✓     |
| redis_persistence_enabled        | Whether to enable persistence               |  false  |    ✕     |
| redis_replica_count              | The number of replicas                      |    1    |    ✕     |
| **Resource Requests and Limits** |                                             |         |          |
| redis_master_cpu_request         | The CPU request for the redis master pdo    |   50m   |    ✕     |
| redis_master_memory_request      | The memory request for the redis master pod |  128Mi  |    ✕     |
| redis_master_cpu_limit           | The CPU limit for the redis master pod      |  100m   |    ✕     |
| redis_master_memory_limit        | The memory limit for the redis master pod   |  256Mi  |    ✕     |
