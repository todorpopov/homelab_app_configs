# GitHub Copilot Instructions

# Overview

This repository contains Kubernetes manifests for various applications and services
deployed to a "homelab" cluster.

# Directory structure

Applications are deployed with a single manifest and are separated in directories based on their respective applications.

For example:

- ./dashboard
  - kubernetes-dashboard.yaml: Kubernetes manifest for the Kubernetes Dashboard application.
- ./dependencies
  - mongo.yaml: Kubernetes manifest for MongoDB.
  - postgresql.yaml: Kubernetes manifest for PostgreSQL.
  - rabbitmq.yaml: Kubernetes manifest for RabbitMQ.
  - redis.yaml: Kubernetes manifest for Redis.
- ./elastic-stack
  - elasticsearch.yaml: Kubernetes manifest for Elasticsearch.
  - filebeat.yaml: Kubernetes manifest for Filebeat.
  - kibana.yaml: Kubernetes manifest for Kibana.
- ./homepage
  - homepage.yaml: Kubernetes manifest for the Homepage application. All other services/applications are exposed through a link in the homepage dashboard.
- ./metrics-server
  - metrics-server.yaml: Kubernetes manifest for Metrics Server. These metrics are exposed through Grafana.
- ./ministack
  - ministack.yaml: Kubernetes manifest for the Ministack AWS emulator.
  - stackport.yaml: Kubernetes manifest for the Stackport AWS client. Set up to point at the ministack pods.
- ./mongo-express:
  - mongo-express.yaml: Kubernetes manifest for the Mongo Express application. Used to provide a web-based interface for managing MongoDB.
- ./node-exporter
  - node-exporter.yaml: Kubernetes manifest for the Node Exporter application. Used to collect hardware and OS metrics from the nodes.
- ./paperless
  - paperless.yaml: Kubernetes manifest for Paperless-ngx (document management). Uses SQLite and the shared Redis from the dependencies namespace.
- ./prometheus-stack:
  - grafana.yaml: Kubernetes manifest for the Grafana application.
  - kube-state-metrics.yaml: Kubernetes manifest for the Kube State Metrics service.
  - prometheus.yaml: Kubernetes manifest for Prometheus.
- ./registry
  - registry.yaml: Kubernetes manifest for the Docker Registry application. Used to store and manage local Docker images.


# Instructions

1. Ensure that all Kubernetes manifests are placed in their respective application directories.
2. Follow the naming convention `<application>.yaml` for all manifest files.
3. Ensure all deployments have configured resource requests and limits for CPU and memory.
4. Update the root README file to reflect any changes in the directory structure or newly added applications.
5. Update this instructions file whenever new applications or services are added to the repository.
