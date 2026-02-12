# Task-Scheduler
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
