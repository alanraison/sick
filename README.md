# sick
The System Initiative Controller for Kubernetes

## Installation

SICK can be deployed to Kubernetes using Helm.

### Using Helm

```bash
helm install sick ./charts/sick
```

For more configuration options, see the [Helm chart documentation](./charts/sick/README.md).

## Development

This repository includes a GitHub Actions workflow that automatically packages the Helm chart and uploads it as a GitHub artifact when changes are pushed.
