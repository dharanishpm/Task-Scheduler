# Task-Scheduler
We built a distributed task scheduler using Spring Boot as the control plane, AWS Step Functions for orchestration, Lambda for execution, and DynamoDB for state management. We maintained two DynamoDB repositories — one for task lifecycle state and another for distributed locking to prevent duplicate execution. Step Functions handled retries and error transitions, and final failures were pushed to SQS DLQ. IAM roles were configured with least privilege for each component.

Fault-tolerant serverless task scheduler built with AWS Step Functions, Lambda, DynamoDB, and SQS (DLQ) featuring distributed locking, retries, and failure handling.

🏗 System Overview — Distributed Task Scheduler

Built a distributed, idempotent task scheduler using:

Spring Boot (Control Plane)

AWS Step Functions (Orchestration)

AWS Lambda (Execution Workers)

DynamoDB (Task + Lock storage)

SQS DLQ (Failure handling)

IAM with least privilege

CloudWatch for logging

The important design decision:
You used two DynamoDB repositories:

Task Repository

Task Lock Repository

This ensured safe distributed execution and prevented duplicate processing.
