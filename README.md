# AWS Security Alert System

## Project Description
The AWS Security Alert System is designed to monitor and alert on suspicious activities in your AWS account using native AWS services. It automates detection and notification of security events, helping you respond quickly to potential threats.

---

## Tools Used

- **AWS Secrets Manager**: Securely stores and manages sensitive credentials and secrets.
- **AWS CloudTrail**: Tracks API calls and user activity across your AWS account.
- **AWS CloudWatch**: Monitors logs and metrics, triggers alarms for suspicious events.
- **Amazon SNS (Simple Notification Service)**: Sends notifications (email/SMS) when alarms are triggered.
- **AWS IAM (Identity and Access Management)**: Manages user permissions and access policies.

---

## How It Works


The system architecture is as follows:

1. **Secrets Manager** manages sensitive credentials and secrets.
2. **CloudTrail** records all API activity in your AWS account.
3. **CloudTrail** stores logs in an S3 bucket.
4. **CloudWatch** monitors CloudTrail logs via Log Groups and applies Metric Filters.
5. When a suspicious pattern is detected, CloudWatch triggers an Alarm.
6. The Alarm sends a notification via SNS to your chosen endpoint (email).

---

## Step-by-Step Setup Guide

1. **Configure Secrets Manager**
	- Go to AWS Console > Secrets Manager
	- Store and manage sensitive information such as personal info, database credentials, API keys, and account IDs
	- Use Secrets Manager to protect access to these sources and rotate secrets regularly
2. **Enable CloudTrail**
	- Go to AWS Console > CloudTrail
	- Create a new trail and enable management/data events
	- Set up an S3 bucket for log storage
3. **Create CloudWatch Metric Filter & Alarm**
	- Go to CloudWatch > Logs > Metric Filters
	- Create a filter for suspicious activity (e.g., unauthorized API calls)
	- Create an alarm based on the metric filter
4. **Set Up SNS Topic**
	- Go to SNS > Create Topic (e.g., `security-alerts`)
	- Add email/SMS subscriptions
	- Link the SNS topic to the CloudWatch alarm action
5. **Test the System**
	- Trigger a test event to verify notifications are received

---

## Benefits & Real-World Use Case
- **Proactive Security**: Detects and alerts on suspicious AWS activity in real time.
- **Automated Response**: Reduces manual monitoring and speeds up incident response.
- **Compliance**: Helps meet security and audit requirements for cloud environments.
- **Scalable**: Easily adapts to multiple AWS accounts and regions.

**Example Use Case:**
An organization uses this system to monitor for unauthorized changes or activities, root account usage, or API calls from unusual locations. When such events occur, security teams are instantly notified and can take action to secure the environment.
