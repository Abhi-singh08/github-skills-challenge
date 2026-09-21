# Operational Data Analysis

The operational dataset contains 10 timestamped observations for the
payment-service.
The metric fields are response_time_ms, cpu_percent, and memory_percent.
The log fields are log_level and message. The timestamp field identifies
when each observation occurred.
The observations from 10:00 through 10:04 show normal behaviour.
The 10:05 observation shows elevated response time and an ERROR log
indicating a payment service timeout.
The 10:06 observation shows elevated response time, high CPU utilization,
high memory utilization, and an ERROR log indicating a database
connection timeout.
The observations from 10:07 through 10:09 return to normal levels.