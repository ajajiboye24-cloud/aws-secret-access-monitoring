# aws-secret-access-monitoring
Cloud Security Monitoring &amp; Alerting System (AWS)
Overview

This project implements a cloud-native security monitoring system that detects and alerts on unauthorized access to secrets stored in AWS Secrets Manager.

The system logs API activity using AWS CloudTrail, processes logs in CloudWatch, and triggers real-time alerts via SNS when a secret is accessed.

Architecture

Services Used:

AWS Secrets Manager

AWS CloudTrail

Amazon S3

Amazon CloudWatch Logs

CloudWatch Metric Filters

CloudWatch Alarms

Amazon SNS

IAM Roles

Architecture Flow:

Secret stored in AWS Secrets Manager

Secret retrieval triggers GetSecretValue API call

CloudTrail logs management event

Logs delivered to CloudWatch Logs

Metric filter detects GetSecretValue pattern

Alarm triggered when metric ≥ 1

SNS sends email notification

(You should include a simple architecture diagram here.)

Security Design Decisions

Used least-privilege IAM role for CloudTrail → CloudWatch integration

Excluded AWS KMS and RDS Data API events to reduce noise

Used static threshold alarm for sensitive resource access

Switched alarm statistic from Average to Sum to ensure proper detection

Testing & Troubleshooting

Tested detection by:

Accessing secret via AWS Console

Accessing secret via AWS CLI

Troubleshooting Steps:

Verified CloudTrail event history

Confirmed log delivery timestamps

Tested metric filter using sample CloudTrail JSON logs

Manually triggered alarm via CLI

Validated SNS subscription confirmation

Key Learnings

Difference between management vs data events

How CloudWatch metric filters parse JSON logs

Importance of alarm statistic selection (Sum vs Average)

Real-world troubleshooting across multiple AWS services
