# SICK Helm Chart

This Helm chart deploys the System Initiative Controller for Kubernetes (SICK).

## Prerequisites

- Kubernetes 1.19+
- Helm 3.0+

## Installing the Chart

To install the chart with the release name `my-release`:

```bash
helm install my-release ./charts/sick
```

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```bash
helm uninstall my-release
```

## Configuration

The following table lists the configurable parameters of the SICK chart and their default values.

| Parameter | Description | Default |
|-----------|-------------|---------|
| `replicaCount` | Number of replicas | `1` |
| `image.repository` | Image repository | `sick` |
| `image.pullPolicy` | Image pull policy | `IfNotPresent` |
| `image.tag` | Image tag (defaults to chart appVersion) | `""` |
| `serviceAccount.create` | Specifies whether a service account should be created | `true` |
| `serviceAccount.name` | The name of the service account to use | `""` |
| `service.type` | Kubernetes service type | `ClusterIP` |
| `service.port` | Service port | `8080` |
| `resources` | CPU/Memory resource requests/limits | `{}` |
| `nodeSelector` | Node labels for pod assignment | `{}` |
| `tolerations` | Tolerations for pod assignment | `[]` |
| `affinity` | Affinity settings for pod assignment | `{}` |

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example:

```bash
helm install my-release ./charts/sick \
  --set replicaCount=2 \
  --set image.tag=0.2.0
```

Alternatively, a YAML file that specifies the values for the parameters can be provided while installing the chart:

```bash
helm install my-release ./charts/sick -f my-values.yaml
```

## GitHub Actions Artifact

This Helm chart is automatically packaged and uploaded as a GitHub artifact when changes are pushed to the repository. The workflow is triggered on:

- Push to `main` or `master` branch (when charts are modified)
- Pull requests to `main` or `master` branch (when charts are modified)
- Manual workflow dispatch

The packaged chart artifact can be downloaded from the GitHub Actions workflow runs.
