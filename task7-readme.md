# AIOps Monitoring & Event Processing
## Scenario

This project simulates a basic AIOps monitoring workflow for a
payment service. Operational telemetry is analyzed to identify
abnormal service behavior and generate anomaly events.

## Operational Data

The operational data contains timestamped service telemetry,
including:

- Response time
- CPU utilization
- Memory utilization
- Log level
- Log message

## Observations

Most observations represent normal service behavior.

Two observations contain abnormal behavior:

- 10:05 – elevated response time and ERROR log
- 10:06 – elevated response time, CPU, memory, and ERROR log

## Anomaly Detection

The anomaly detector uses the following thresholds:

- Response time > 500 ms
- CPU > 80%
- Memory > 80%
- ERROR log

The pipeline detected 2 anomalies from 10 records.

## Event Flow

The anomaly event flows through:

Anomaly Detector
→ Event Producer
→ Event Topic
→ Event Consumer
→ AIOps Output

## End-to-End Execution

The pipeline processed 10 records and detected 2 anomalies.

After correcting the event topic wiring, the anomaly events were
published and consumed successfully.

## Issue and Correction

The initial pipeline detected anomalies but consumed zero events.

The issue was caused by the producer and consumer not sharing the
same topic instance.

The pipeline was corrected so that the producer and consumer use
the same EventTopic instance.

## Limitation and Improvement

The anomaly detector uses fixed thresholds.

A possible improvement is to use historical telemetry to establish
dynamic baselines and detect deviations from normal behavior.

## Reproduction Steps

Install dependencies:

    pip install -r requirements.txt

Run the pipeline:

    python src/aiops_pipeline.py

Run the tests:

    pytest -v