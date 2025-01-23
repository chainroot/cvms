# CVMS Helm Chart

This Helm chart is used to deploy the CVMS (Custom Video Management System) application.

## Prerequisites

- Kubernetes 1.12+
- Helm 3.0+

## Installation

To install the chart with the release name `my-release`:

```bash
helm install my-release /path/to/cvms
```

## Uninstallation

To uninstall/delete the `my-release` deployment:

```bash
helm uninstall my-release
```

## Configuration

The following table lists the configurable parameters of the CVMS chart and their default values.

| Parameter                | Description                           | Default                        |
|--------------------------|---------------------------------------|--------------------------------|
| `image.repository`       | Image repository                      | `cvms/cvms`                    |
| `image.tag`              | Image tag                             | `latest`                       |
| `image.pullPolicy`       | Image pull policy                     | `IfNotPresent`                 |
| `service.type`           | Kubernetes service type               | `ClusterIP`                    |
| `service.port`           | Service port                          | `80`                           |
| `ingress.enabled`        | Enable ingress controller resource    | `false`                        |
| `ingress.annotations`    | Ingress annotations                   | `{}`                           |
| `ingress.hosts`          | Ingress hostnames                     | `[]`                           |
| `ingress.tls`            | Ingress TLS configuration             | `[]`                           |
| `resources`              | CPU/Memory resource requests/limits   | `{}`                           |
| `nodeSelector`           | Node labels for pod assignment        | `{}`                           |
| `tolerations`            | Tolerations for pod assignment        | `[]`                           |
| `affinity`               | Node affinity for pod assignment      | `{}`                           |

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example:

```bash
helm install my-release /path/to/cvms --set image.tag=1.0.0
```

Alternatively, a YAML file that specifies the values for the parameters can be provided while installing the chart. For example:

```bash
helm install my-release /path/to/cvms -f values.yaml
```

### Detailed Configuration

Below is a more detailed explanation of the values that can be set in the `values.yaml` file:

- `image.repository`: The Docker image repository for the CVMS application.
- `image.tag`: The tag of the Docker image to use.
- `image.pullPolicy`: The Kubernetes image pull policy.
- `service.type`: The type of Kubernetes service to create (e.g., `ClusterIP`, `NodePort`, `LoadBalancer`).
- `service.port`: The port on which the service will be exposed.
- `ingress.enabled`: Whether to enable the ingress controller.
- `ingress.annotations`: Annotations to add to the ingress resource.
- `ingress.hosts`: A list of hostnames to configure in the ingress resource.
- `ingress.tls`: TLS configuration for the ingress resource.
- `resources`: Resource requests and limits for the CVMS pods.
- `nodeSelector`: Node labels for pod assignment.
- `tolerations`: Tolerations for pod assignment.
- `affinity`: Affinity rules for pod assignment.

## Contributing

We welcome contributions! Please read our [Contributing Guide](CONTRIBUTING.md) to learn how you can help.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Maintainers

- Mohammad (mohammad@example.com)

For any questions or issues, please open an issue on the [GitHub repository](https://github.com/your-repo/cvms).
