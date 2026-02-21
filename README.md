AWS Secret Access Monitoring & Alerting System

This project demonstrates a cloud-native security monitoring system built with AWS Secrets Manager, CloudTrail, CloudWatch, and SNS to detect and alert on sensitive secret access in real time.

🚀 Features

Monitor GetSecretValue API calls via CloudTrail management events

Stream CloudTrail logs to CloudWatch Logs

Detect secret access using CloudWatch metric filters

Trigger real-time alerts with CloudWatch Alarms

Send email notifications via SNS

Apply IAM least-privilege roles for secure service integration

🧠 AWS Services Used

Secrets Manager (Secure secret storage)

CloudTrail (API activity logging)

S3 (CloudTrail log storage)

CloudWatch Logs

CloudWatch Metric Filters

CloudWatch Alarms

SNS (Email notifications)

IAM

🧪 How It Works

A secret is securely stored in AWS Secrets Manager.

When GetSecretValue is called, CloudTrail logs the management event.

CloudTrail delivers logs to CloudWatch Logs.

A metric filter scans logs for GetSecretValue.

If detected (≥1 event), a CloudWatch Alarm enters ALARM state.

SNS sends a real-time email notification.

🔍 Troubleshooting & Validation

Verified CloudTrail event history for GetSecretValue logs

Tested metric filter using sample CloudTrail JSON data

Manually triggered alarm via AWS CLI

Corrected alarm statistic from Average → Sum to ensure accurate detection

Confirmed SNS subscription and email delivery

🧰 Future Enhancements

Rebuild full infrastructure using Terraform (Infrastructure as Code)

Add automated remediation (Lambda to rotate or revoke access)

Integrate Slack or webhook notifications

Add anomaly detection for unusual secret access patterns
