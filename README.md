# Turborepo Remote Cache Chart

- [Turborepo Remote Cache Chart](#turborepo-remote-cache-chart)
  - [Requirments](#requirments)
  - [Introduction](#introduction)
  - [Compatibility](#compatibility)
  - [Installing the chart](#installing-the-chart)
  - [Configuration](#configuration)
    - [Image](#image)
    - [Deployment](#deployment)
    - [Service](#service)
    - [Ingress](#ingress)

## Requirments

- Helm v3

## Introduction

This chart bootstraps an instance of Turborepo Remote Cache server. The image used for that is [here](https://github.com/fox1t/turborepo-remote-cache).

## Compatibility

| Turborepo Remote Cache Version | Kubernetes Version | Helm Chart Version |
| ------------------------------ | ------------------ | ------------------ |
| 1.5.1                          | 1.22               | 0.1.2              |

## Installing the chart

WIP - Helm repo in progress

## Configuration

### Image

| Parameter          | Description                               | Default        |
| ------------------ | ----------------------------------------- | -------------- |
| `image.tag`        | `fox1t/turborepo-remote-cache` image tag. | `1.5.1`        |
| `image.pullPolicy` | Image pull policy                         | `IfNotPresent` |

### Deployment

| Parameter                | Description                       | Default |
| ------------------------ | --------------------------------- | ------- |
| `deployment.labels`      | Kubernetes deployment labels      | `{}`    |
| `deployment.annotations` | Kubernetes deployment annotations | `{}`    |

### Service

| Parameter              | Description                    | Default     |
| ---------------------- | ------------------------------ | ----------- |
| `service.type`         | Kubernetes service type        | `ClusterIP` |
| `service.externalPort` | Kubernetes service port        | `3000`      |
| `service.nodePort`     | If service type is `NodePort`  | `None`      |
| `service.labels`       | Kubernetes service labels      | `{}`        |
| `service.annotations`  | Kubernetes service annotations | `{}`        |

### Ingress

| Parameter                      | Description                                                  | Default                     |
| ------------------------------ | ------------------------------------------------------------ | --------------------------- |
| `ingress.enabled`              | Flag to enable Ingress                                       | `false`                     |
| `ingress.labels`               | Ingress additional labels                                    | `{}`                        |
| `ingress.hosts[0].name`        | Hostname to your SonarQube installation                      | `remote-cache.your-org.com` |
| `ingress.hosts[0].path`        | Path within the URL structure                                | `/`                         |
| `ingress.hosts[0].serviceName` | Optional field to override the default serviceName of a path | `None`                      |
| `ingress.hosts[0].servicePort` | Optional field to override the default servicePort of a path | `None`                      |
| `ingress.tls`                  | Ingress secrets for TLS certificates                         | `[]`                        |
| `ingress.className`            | Optional field to configure ingress class name               | `None`                      |
| `ingress.annotations`          | Optional field to add extra annotations to the ingress       | `None`                      |
