# Final SRE Report

## Executive Summary

A Kubernetes-based DevOps Jobs Portal was deployed and monitored using Prometheus, Grafana, Alertmanager, and Node Exporter.

A load test of 50,000 requests was executed using Apache Benchmark.

The monitoring platform successfully detected traffic spikes, generated alerts, and recorded application failures.

Kubernetes automatically recovered unhealthy pods without manual intervention.

## Test Results

### Before Traffic

CPU Utilization:

~4%

Memory Utilization:

~36%

System Status:

Healthy

### During Traffic

CPU Usage Increased

Network Throughput Increased

Alerts Triggered

### Application Failure

Observed:

* Failed Fetch Requests
* Aborted Requests

### Recovery

Pods Automatically Restarted

Application Returned To Healthy State

Metrics Normalized

## Conclusion

The project demonstrates practical implementation of:

* Site Reliability Engineering
* Kubernetes Observability
* Incident Detection
* Incident Response
* Self-Healing Infrastructure
* Load Testing

The system successfully recovered from load-induced failures while maintaining cluster stability.
