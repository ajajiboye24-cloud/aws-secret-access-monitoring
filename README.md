# AWS Secret Access Monitoring & Alerting System

This project demonstrates a cloud-native security monitoring system built with **AWS Secrets Manager, CloudTrail, CloudWatch, and SNS** to detect and alert on sensitive secret access in real time.

## 🚀 Features

- Detect `GetSecretValue` API calls via CloudTrail management events
- Stream CloudTrail logs to CloudWatch Logs for centralized visibility
- Create CloudWatch metric filters to track secret access events
- Trigger real-time alerts using CloudWatch Alarms
- Send email notifications via SNS
- Use IAM roles to enforce least-privilege access between services

## 🧠 AWS Services Used

- Secrets Manager (Secret storage)
- CloudTrail (API activity logging)
- S3 (CloudTrail log storage)
- CloudWatch Logs (Log aggregation)
- CloudWatch Metric Filters (Event detection)
- CloudWatch Alarms (Alert triggering)
- SNS (Email notifications)
- IAM (Access control)

## 🧪 How It Works

1. A secret is securely stored in AWS Secrets Manager.
2. When the secret is retrieved, AWS logs a `GetSecretValue` management event in CloudTrail.
3. CloudTrail delivers events to CloudWatch Logs.
4. A metric filter scans logs for `GetSecretValue`.
5. A CloudWatch Alarm triggers when the metric is **≥ 1** (Statistic: `Sum`).
6. SNS sends an email notification to subscribed recipients.

## 🧰 Future Enhancements

- Rebuild the full system using Terraform (Infrastructure as Code)
- Add automated remediation with Lambda (rotate secret / revoke access)
- Send alerts to Slack via webhook
- Add anomaly detection for unusual access patterns
- Add a DynamoDB table for tracking access events over time
