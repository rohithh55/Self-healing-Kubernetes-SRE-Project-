# Monitoring Setup

## Objective

Implement observability for Kubernetes workloads and cluster infrastructure.

## Monitoring Stack

### Prometheus

Responsibilities:

* Metrics Collection
* Service Discovery
* Alert Evaluation
* Time Series Storage

Collected Metrics:

* CPU Usage
* Memory Usage
* Network Traffic
* Pod Status
* API Server Metrics
* Node Metrics

### Grafana

Responsibilities:

* Dashboard Visualization
* Performance Analysis
* Historical Trend Analysis

Dashboards Used

1. Kubernetes Compute Resources
2. Kubernetes API Server
3. Kubernetes Kubelet
4. Alertmanager Overview
5. Node Exporter Dashboard

### Alertmanager

Responsibilities:

* Alert Routing
* Incident Notification
* Alert Grouping

Alert Examples

* High CPU Usage
* Pod Failure
* Node Down
* Memory Pressure
* API Server Latency

### Node Exporter

Responsibilities:

* Node Metrics Collection
* CPU Monitoring
* Memory Monitoring
* Disk Monitoring
* Network Monitoring
