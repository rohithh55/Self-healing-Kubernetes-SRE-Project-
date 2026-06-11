# Architecture Overview

## Project Summary

This project demonstrates the implementation of Site Reliability Engineering (SRE) practices for a Kubernetes-based DevOps Jobs Portal deployed on AWS EKS.

The platform was monitored using Prometheus, Grafana, Alertmanager, and Node Exporter. Reliability testing was performed using Apache Benchmark (AB) by generating approximately 50,000 HTTP requests against the application.

## Architecture Components

### Infrastructure Layer

* AWS EKS Cluster
* Worker Nodes
* Application Load Balancer (ALB)
* Route 53 (Optional)
* VPC with Public and Private Subnets

### Application Layer

* Frontend Application
* Backend API
* Kubernetes Deployments
* Kubernetes Services
* Kubernetes Ingress

### Monitoring Layer

* Prometheus
* Grafana
* Alertmanager
* Node Exporter
* kube-state-metrics

### CI/CD Layer

* Jenkins
* Docker
* Kubernetes Deployments

## Request Flow

User → Load Balancer → Kubernetes Ingress → Service → Application Pods

Metrics Flow:

Application / Nodes → Prometheus → Grafana Dashboards

Alert Flow:

Prometheus → Alertmanager → Notifications

## Reliability Objectives

* High Availability
* Automatic Recovery
* Resource Monitoring
* Failure Detection
* Incident Response
* Performance Validation
