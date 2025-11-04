# CariData Helm Chart

## Overview
This Helm chart deploys the CariData backend and frontend applications along with ingress and services.

## Installation
```bash
helm install caridata charts/caridata
```

## Configuration

### Resource management

Both the backend and frontend deployments expose dedicated `resources` sections so you can
define CPU and memory requests and limits according to Kubernetes best practices. Each
component ships with sensible defaults that request a portion of the available resources
while still defining upper limits to protect the cluster.

Example override file:

```yaml
backend:
  resources:
    requests:
      cpu: 500m
      memory: 512Mi
    limits:
      cpu: 1
      memory: 1Gi

frontend:
  resources:
    requests:
      cpu: 200m
      memory: 256Mi
    limits:
      cpu: 400m
      memory: 512Mi
```
