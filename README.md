# Web Application Kubernetes Deployment

This repository contains Kubernetes manifests for deploying a web application in a multi-zone cluster. The deployment is optimized for fault tolerance, resource efficiency, and scalability.

## Files and Structure

- `manifests/`
  - `deployment.yaml`: Defines the deployment configuration for the web application.
  - `service.yaml`: Exposes the application within the Kubernetes cluster.
  - `hpa.yaml`: Horizontal Pod Autoscaler for scaling the application based on CPU utilization.
  - `pdb.yaml`: Pod Disruption Budget to ensure minimum availability during updates or failures.
  - `priorityclass.yaml`: Priority class for ensuring resource allocation.

## Features

- **Fault Tolerance:** Pods are distributed across nodes and zones using `podAntiAffinity`.
- **Scalability:** Automatic scaling with Horizontal Pod Autoscaler.
- **Resource Optimization:** Requests and limits are defined for efficient resource usage.
- **Health Monitoring:** Readiness and liveness probes to ensure application health.
- **High Availability:** Pod Disruption Budget ensures minimum 3 pods are always available.

## Prerequisites

- Kubernetes cluster (multi-zone setup preferred).
- kubectl installed and configured.
- Docker image of the web application (`myregistry/web-app:latest`).

## Deployment Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/canavarro86/web-app-k8s-deployment.git
   cd web-app-k8s-deployment
