
## AIOps Scenario

This project simulates monitoring of a payment service using synthetic
operational telemetry.

The operational data contains service metrics and log information.
The purpose of the AIOps workflow is to identify abnormal service
behaviour and process detected anomalies as events.

The workflow consists of:

Operational Data
→ Anomaly Detection
→ Event Generation
→ Producer
→ Topic
→ Consumer
→ AIOps Output  