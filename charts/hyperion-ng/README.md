# hyperion-ng

![Version: 2.0.1](https://img.shields.io/badge/Version-2.0.1-informational?style=flat-square) ![AppVersion: 2.0.0-alpha9](https://img.shields.io/badge/AppVersion-2.0.0--alpha9-informational?style=flat-square)

Hyperion is an opensource Bias or Ambient Lighting implementation

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/k8s-at-home/charts/issues/new/choose)**

## Source Code

* <https://github.com/hyperion-project/hyperion.ng>
* <https://hub.docker.com/r/sirfragalot/hyperion.ng>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://k8s-at-home.com/charts/ | common | 3.0.1 |

## TL;DR

```console
helm repo add k8s-at-home https://k8s-at-home.com/charts/
helm repo update
helm install hyperion-ng k8s-at-home/hyperion-ng
```

## Installing the Chart

To install the chart with the release name `hyperion-ng`

```console
helm install hyperion-ng k8s-at-home/hyperion-ng
```

## Uninstalling the Chart

To uninstall the `hyperion-ng` deployment

```console
helm uninstall hyperion-ng
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](../common/values.yaml) from the [common library](../common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install hyperion-ng \
  --set env.TZ="America/New York" \
    k8s-at-home/hyperion-ng
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install hyperion-ng k8s-at-home/hyperion-ng -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | `{}` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"sirfragalot/hyperion.ng"` |  |
| image.tag | string | `"2.0.0-alpha.9-x86_64"` |  |
| ingress.enabled | bool | `false` |  |
| persistence.config.emptyDir | bool | `false` |  |
| persistence.config.enabled | bool | `false` |  |
| persistence.config.mountPath | string | `"/root/.hyperion"` |  |
| service.additionalPorts[0].name | string | `"jsonservice"` |  |
| service.additionalPorts[0].port | int | `19444` |  |
| service.additionalPorts[0].protocol | string | `"TCP"` |  |
| service.additionalPorts[0].targetPort | int | `19444` |  |
| service.additionalPorts[1].name | string | `"protobufservice"` |  |
| service.additionalPorts[1].port | int | `19445` |  |
| service.additionalPorts[1].protocol | string | `"TCP"` |  |
| service.additionalPorts[1].targetPort | int | `19445` |  |
| service.additionalPorts[2].name | string | `"boblightservice"` |  |
| service.additionalPorts[2].port | int | `19333` |  |
| service.additionalPorts[2].protocol | string | `"TCP"` |  |
| service.additionalPorts[2].targetPort | int | `19333` |  |
| service.port.port | int | `8090` |  |
| strategy.type | string | `"Recreate"` |  |

## Changelog

All notable changes to this application Helm chart will be documented in this file but does not include changes from our common library. To read those click [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common#changelog).

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

### [1.0.0]

#### Added

- N/A

#### Changed

- N/A

#### Removed

- N/A

[1.0.0]: #1.0.0

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/k8s-at-home/charts/issues/new/choose)
- Ask a [question](https://github.com/k8s-at-home/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)