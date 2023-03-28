# memos

<img src="https://raw.githubusercontent.com/usememos/memos/2e14561bfce0092851ab612b6d849b9c9815228c/web/public/logo.png" align="right" width="92" alt="memos logo">

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat)
![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat)
![AppVersion: 0.11.2](https://img.shields.io/badge/AppVersion-0.11.2-informational?style=flat)

A lightweight, self-hosted memo hub. Open Source and Free forever.

**Homepage:** <https://charts.gabe565.com/charts/memos>

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/gabe565/charts/issues/new)**

## Source Code

* <https://github.com/gabe565/charts/tree/main/charts/memos>
* <https://usememos.com>
* <https://github.com/usememos/memos>

## Requirements

Kubernetes: `>=1.22.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| <https://bjw-s.github.io/helm-charts> | common | 1.3.2 |

## TL;DR

```console
helm repo add gabe565 https://charts.gabe565.com
helm repo update
helm install memos gabe565/memos
```

## Installing the Chart

To install the chart with the release name `memos`

```console
helm install memos gabe565/memos
```

## Uninstalling the Chart

To uninstall the `memos` deployment

```console
helm uninstall memos
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/bjw-s/helm-charts/tree/main/charts/library/common/values.yaml) from the [bjw-s common library](https://github.com/bjw-s/helm-charts/tree/main/charts/library/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install memos \
  --set env.TZ="America/New York" \
    gabe565/memos
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install memos gabe565/memos -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from the bjw-s common library chart [here](https://github.com/bjw-s/helm-charts/tree/main/charts/library/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"neosmemo/memos"` | image repository |
| image.tag | string | `"0.11.2"` | image tag |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See [values.yaml](./values.yaml) | Configure persistence settings for the chart under this key. |
| podSecurityContext.fsGroup | int | `65534` | Volume binds will be granted to `nobody` group |
| podSecurityContext.runAsGroup | int | `65534` | Run as `nobody` group |
| podSecurityContext.runAsUser | int | `65534` | Run as `nobody` user |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

---
Autogenerated from chart metadata using [helm-docs](https://github.com/norwoodj/helm-docs)