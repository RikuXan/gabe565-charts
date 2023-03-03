# qbittorrent

<img src="https://raw.githubusercontent.com/qbittorrent/qBittorrent/master/src/icons/qbittorrent-tray.svg" align="right" width="92" alt="qbittorrent logo" style="padding-left: 20px">

![Version: 0.0.1](https://img.shields.io/badge/Version-0.0.1-informational?style=flat)
![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat)
![AppVersion: version-4.5.2-r0](https://img.shields.io/badge/AppVersion-version--4.5.2--r0-informational?style=flat)

The qBittorrent project aims to provide an open-source software alternative to µTorrent.

**Homepage:** <https://charts.gabe565.com/charts/qbittorrent>

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/gabe565/charts/issues/new)**

## Source Code

* <https://github.com/gabe565/charts/tree/main/charts/qbittorrent>
* <https://github.com/qbittorrent/qBittorrent>
* <https://github.com/linuxserver/docker-qbittorrent>

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
helm install qbittorrent gabe565/qbittorrent
```

## Installing the Chart

To install the chart with the release name `qbittorrent`

```console
helm install qbittorrent gabe565/qbittorrent
```

## Uninstalling the Chart

To uninstall the `qbittorrent` deployment

```console
helm uninstall qbittorrent
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/bjw-s/helm-charts/tree/main/charts/library/common/values.yaml) from the [bjw-s common library](https://github.com/bjw-s/helm-charts/tree/main/charts/library/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install qbittorrent \
  --set env.TZ="America/New York" \
    gabe565/qbittorrent
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install qbittorrent gabe565/qbittorrent -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from the bjw-s common library chart [here](https://github.com/bjw-s/helm-charts/tree/main/charts/library/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | See [values.yaml](./values.yaml) | environment variables. [[ref]](https://github.com/linuxserver/docker-qbittorrent#parameters) |
| env.TZ | string | `"UTC"` | Set the container timezone |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"ghcr.io/linuxserver/qbittorrent"` | image repository |
| image.tag | string | `"version-4.5.2-r0"` | image tag |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| service | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

---
Autogenerated from chart metadata using [helm-docs](https://github.com/norwoodj/helm-docs)