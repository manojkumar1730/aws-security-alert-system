# CloudTrail Setup

## Steps

1. Go to AWS Console → CloudTrail → Trails.
2. Click **Create trail** and give it a name (e.g., `secret-manage-trail`).
3. Enable for **all regions**.
4. Choose or create an **S3 bucket** for storing logs.
5. Turn on **log file validation** (for security).
6. Enable **CloudWatch Logs** and create a log group (e.g., `networks-secretmanager-loggroup`).
7. Let CloudTrail create an **IAM role** for permissions.
8. (Optional) Enable **SNS notifications**.
9. Save the trail → status should show **Logging ✅**.


---

## Verify
1. Go to **CloudTrail → Event history**.
2. Perform a test action in **Secrets Manager** (e.g., `GetSecretValue`).
3. You should see the event recorded in **Event history**.

CloudTrail will now record all account activity for security monitoring.