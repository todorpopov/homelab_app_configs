# Homelab App Configurations

Kubernetes configuration files for homelab applications and services.

## Overview

This repository contains Kubernetes manifests for deploying and managing various applications in a homelab environment. Each directory contains YAML configuration files for specific services or application stacks.

All manifests are configured to personal needs and do not represent a generic solution. DNS resolving is tuned to go through a Tailscale subnet, so host names must be changed for the services to be deployed to a different cluster.

## Services

### Monitoring & Metrics

- **prometheus-stack/** - Complete Prometheus monitoring stack
  - `prometheus.yaml` - Prometheus metrics collection
  - `grafana.yaml` - Grafana dashboards and visualization
  - `kube-state-metrics.yaml` - Kubernetes cluster metrics
- **node-exporter/** - System-level metrics collection
- **metrics-server/** - Kubernetes metrics API

### Logging & Analytics

- **elastic-stack/** - Complete ELK stack
  - `elasticsearch.yaml` - Log storage and search
  - `kibana.yaml` - Log visualization and analysis
  - `filebeat.yaml` - Log shipping and forwarding

### Infrastructure Services

These services are used for application development and testing.

- **dependencies/** - Core infrastructure dependencies
  - `postgres.yaml` - PostgreSQL database
  - `redis.yaml` - Redis cache/message broker
  - `rabbitmq.yaml` - RabbitMQ message queue
- **registry/** - Container registry
  - `registry.yaml` - Docker registry
  - `registry-ui.yaml` - Web UI for registry

### Management & UI

- **dashboard/** - Kubernetes Dashboard for cluster management
- **homepage/** - Custom homepage/dashboard

## Directory Structure

```
.
├── dashboard/
├── dependencies/
├── elastic-stack/
├── homepage/
├── metrics-server/
├── node-exporter/
├── prometheus-stack/
└── registry/
```

## Usage

Each directory contains the necessary Kubernetes manifests for deploying the respective service. To deploy a service:

```bash
kubectl apply -f <directory>/<manifest>.yaml
```

To deploy an entire stack:

```bash
kubectl apply -f <directory>/
```

## Notes

- Ensure cluster resources (CPU, memory, storage) are adequate before deployment
- Check for any ConfigMaps or Secrets that need to be configured separately
- Review namespace configurations and adjust as needed for your cluster
- Some services may have dependencies on others (e.g., Filebeat requires Elasticsearch)

## Maintenance

Last updated: April 8, 2026
