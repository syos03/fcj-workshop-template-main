---
title: "Week 10 Worklog"
date: 2024-01-01
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}


### Week 10 Objectives:

* Deploy the IoT Telemetry ingestion flow using AWS IoT Core service.
* Integrate Amazon SQS queues for message buffering and data loss prevention.
* Program AWS Lambda (Telemetry Processor) to process and save data into Amazon DynamoDB.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | :---: | :---: | --- |
| 64 | Set up AWS IoT Core, initialize Thing representing the vehicle, and configure X.509 Certificate. | 19/06/2026 | 19/06/2026 |  |
| 65 | Build Vehicle Simulator program to transmit telemetry data periodically via MQTT protocol. | 20/06/2026 | 20/06/2026 |  |
| 66 | Configure AWS IoT Rule Engine to automatically capture incoming MQTT messages from devices. | 21/06/2026 | 21/06/2026 |  |
| 67 | Initialize Amazon SQS (Standard Queue) to receive and temporarily store telemetry messages. | 22/06/2026 | 22/06/2026 |  |
| 68 | Program AWS Lambda (Telemetry Processor) function to parse raw vehicle data from SQS queues. | 23/06/2026 | 23/06/2026 |  |
| 69 | Configure SQS as Event Source Trigger for the Lambda Processor to execute batch tasks. | 24/06/2026 | 24/06/2026 |  |
| 70 | Code Lambda logic to save sensor logs and update the latest vehicle status in Amazon DynamoDB. | 25/06/2026 | 25/06/2026 |  |


### Week 10 Achievements:

* Successfully deployed IoT Telemetry ingestion from Simulator to AWS IoT Core securely.
* Integrated SQS message broker and configured AWS Lambda for automatic processing.
* Confirmed successful sensor data storage in the Amazon DynamoDB database.
