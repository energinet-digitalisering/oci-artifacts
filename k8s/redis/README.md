# Redis

Redis is a key-value store that can be used as a database, cache, or message broker.

- [Documentation](https://redis.io/documentation)
- [Helm Chart](https://artifacthub.io/packages/helm/bitnami/redis)

## Post-build variables

| Variable                  | Description                         | Default | Required |
| ------------------------- | ----------------------------------- | :-----: | :------: |
| redis_password            | The password for the Redis instance |         |    ✓     |
| redis_persistence_enabled | Whether to enable persistence       |  false  |    ✕     |
| redis_replica_count       | The number of replicas              |    1    |    ✕     |
