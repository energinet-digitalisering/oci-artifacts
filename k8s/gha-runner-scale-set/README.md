# GitHub Runner Scale Set

GitHub Runner Scale Set enables running self-hosted GitHub Actions runners in Kubernetes.

## Dependencies

- [GitHub Runner Scale Set Controller](../gha-runner-scale-set-controller/README.md)

## Post-build variables

| Variable              | Description                                                                        | Default | Required |
| --------------------- | ---------------------------------------------------------------------------------- | :-----: | :------: |
| actions_runner_image  | The image to use for the GitHub Actions Runner Scale set.                          |   ""    |    ✕     |
| github_config_url     | The URL to the GitHub org or repo to scope the GitHub Actions Runner Scale set to. |   ""    |    ✓     |
| github_token          | The GitHub Token required to authenticate with your GitHub org or repo.            |   ""    |    ✓     |
| runner_scale_set_name | The name of the GitHub Actions Runner Scale set.                                   |   ""    |    ✓     |
