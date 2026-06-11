# Apache Benchmark Execution

## Command

ab -n 50000 -c 100 http://<LOAD-BALANCER>/jobs

## Parameters

* n = Total Requests
* c = Concurrent Users

## Results

Generated Traffic:

50,000 Requests

Concurrency:

100 Users

Observed:

* CPU Spike
* Network Spike
* Alert Generation
* Temporary Request Failures
* Pod Recovery

## Validation

The test successfully validated system reliability and observability.
