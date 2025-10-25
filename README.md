
# S3 Bucket Access Setup for EC2

This repository provides instructions and policies to configure **AWS S3 bucket access** for an EC2 instance using IAM roles. It includes both a **custom policy** for backend access and a **bucket policy** for full access.

---

## 1️⃣ Custom Policy for Backend Access

Create a policy in IAM with the following JSON. Replace placeholders with your actual AWS account details:

```json
 {
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowBackendAccess",
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::<YOUR-AWS-ACCOUNT-ID>:role/<EC2-ROLE-NAME>"
      },
      "Action": [
        "s3:PutObject",
        "s3:GetObject"
      ],
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}


------

## 2️⃣
+
+ Custom Policy for Backend Access

Create a policy in IAM with the following JSON. Replace placeholders with your actual AWS account details:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowBackendAccess",
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::<YOUR-AWS-ACCOUNT-ID>:role/<EC2-ROLE-NAME>"
      },
      "Action": [
        "s3:PutObject",
        "s3:GetObject"
      ],
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}

---
