# Load Testing Report

## Tool

Apache Benchmark (AB)

## Test Target

DevOps Jobs Portal

Endpoint:

/jobs

## Test Configuration

Total Requests:

50,000

Concurrency:

100

Command Used

ab -n 50000 -c 100 http://<LOAD-BALANCER>/jobs

## Test Goals

* Evaluate application performance
* Observe Kubernetes behavior under load
* Validate monitoring dashboards
* Trigger alerts
* Verify recovery mechanisms

## Observations

Before Traffic

* CPU Usage approximately 4%
* Memory Usage approximately 36%
* Stable Network Throughput

During Traffic

* Increased CPU utilization
* Increased network throughput
* Increased API Server activity
* Alertmanager generated alerts

Application Failure

Observed errors:

* TypeError: Failed to Fetch
* Request Aborted

Recovery

Kubernetes automatically restarted unhealthy pods.

Pods returned to Running state.

Metrics returned to normal levels.

## Conclusion

The platform successfully handled high traffic and demonstrated Kubernetes self-healing capabilities.
