# SNS Setup

## Steps
1. Go to AWS Console > SNS.
2. Create a new topic (e.g., `security-alerts`).
3. Add email or SMS subscriptions for notifications.
4. Link the SNS topic to CloudWatch alarm actions.
5. Test by triggering an alarm to verify notification delivery.

SNS will send alerts to your chosen endpoints when a security event occurs.