# Self-healing-Kubernetes-SRE-Project-
This project demonstrates the implementation of Site Reliability Engineering (SRE) practices for a Kubernetes-based DevOps Jobs Portal deployed on AWS EKS.
# Site Reliability Engineering for DevOps Jobs Portal

## Project Overview

This project demonstrates the implementation of Site Reliability Engineering (SRE) practices for a Kubernetes-based DevOps Jobs Portal deployed on AWS.

The project focuses on:

- Kubernetes Observability
- Prometheus Monitoring
- Grafana Dashboards
- AlertManager Integration
- Apache Benchmark Load Testing
- Kubernetes Self-Healing
- Incident Analysis
- SLI/SLO Design

---

## Architecture

Users access the application through an AWS Application Load Balancer.

```text
Users
  |
  v
AWS ALB
  |
  v
Kubernetes Cluster
  |
  +-- Frontend
  +-- Backend
  +-- PocketBase
  |
  +-- Prometheus
  +-- Grafana
  +-- AlertManager
  +-- Node Exporter
```

---

## Technology Stack

| Component | Technology |
|------------|------------|
| Cloud | AWS |
| Orchestration | Kubernetes |
| Monitoring | Prometheus |
| Visualization | Grafana |
| Alerting | AlertManager |
| Metrics | Node Exporter |
| Load Testing | Apache Benchmark |
| Database | PocketBase |

---

## Reliability Goals

### Service Level Objectives (SLO)

- Availability > 99.9%
- Error Rate < 1%
- API Success Rate > 99%
- Recovery Time < 5 minutes

---

## Load Testing

Apache Benchmark was used to generate approximately 50,000 requests.

```bash
ab -n 50000 -c 100 http://ALB/jobs
```

---

# Before Traffic

System operating normally.

## Metrics

| Metric | Value |
|----------|---------|
| CPU Usage | 4% |
| Memory Usage | 36% |
| Availability | 100% |
| Error Rate | 0% |

### Screenshots

![Compute](screenshots/before-traffic/compute-resources.png)

![API Server](screenshots/before-traffic/api-server.png)

![AlertManager](screenshots/before-traffic/alertmanager.png)

![Node Exporter](screenshots/before-traffic/node-exporter.png)

---

# During Traffic

Traffic generated using Apache Benchmark.

### Observations

- CPU spikes detected
- Network traffic increased
- Request throughput increased
- AlertManager triggered alerts
- Backend instability observed

### Screenshots

![CPU](screenshots/during-traffic/cpu-spike.png)

![Network](screenshots/during-traffic/network-spike.png)

![API](screenshots/during-traffic/api-server-load.png)

---

# Incident Analysis

During the load test, the application experienced temporary failures.

### Errors

```text
TypeError: Failed to fetch
```

```text
Request aborted
```

### Screenshots

![Failed Fetch](screenshots/application-failure/failed-fetch-error.png)

![Aborted](screenshots/application-failure/request-aborted.png)

### Root Cause

Potential causes:

- Backend saturation
- Database bottleneck
- Resource exhaustion
- Lack of horizontal scaling

---

# Kubernetes Self-Healing

During load testing, pods became unhealthy and were automatically restarted by Kubernetes.

Recovery occurred without manual intervention.

### Recovery Process

1. Kubernetes detected unhealthy pods.
2. Failed containers were terminated.
3. New pods were created.
4. Services were reattached.
5. Application availability was restored.

---

# Recovery Metrics

| Metric | Result |
|----------|---------|
| Availability | Maintained |
| Recovery | Automatic |
| Pod Health | Restored |
| Monitoring | Operational |

### Screenshots

![Recovery](screenshots/recovery/pod-recovery.png)

![Cluster](screenshots/recovery/cluster-healthy.png)

---

# Monitoring Stack

## Prometheus

Metrics collection.

## Grafana

Visualization dashboards.

## AlertManager

Alert routing and notifications.

## Node Exporter

Infrastructure metrics.

---

# Key Achievements

- Implemented complete observability stack
- Performed 50,000 request load test
- Monitored Kubernetes cluster health
- Detected application bottlenecks
- Demonstrated Kubernetes self-healing
- Maintained high availability

---

# Resume Summary

Implemented Site Reliability Engineering practices for a Kubernetes-based DevOps Jobs Portal using Prometheus, Grafana, AlertManager, and Apache Benchmark. Conducted 50,000-request load testing, analyzed application reliability, identified bottlenecks, and validated Kubernetes self-healing capabilities through automatic pod recovery.
