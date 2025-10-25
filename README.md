# S3 Bucket Access Setup for EC2

This repository provides instructions and a combined policy to configure **AWS S3 bucket access** for an EC2 instance using IAM roles. The policy includes both **backend access** (read/write objects) and **full bucket permissions**.

---

## Combined IAM and Bucket Policy

Use this single JSON policy for your S3 bucket. Replace placeholders with your actual AWS account ID, IAM role name, and bucket name.

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
        "s3:GetObject",
        "s3:PutObject"
      ],
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    },
    {
      "Sid": "AllowFullBucketAccess",
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::<YOUR-AWS-ACCOUNT-ID>:role/<EC2-ROLE-NAME>"
      },
      "Action": "s3:*",
      "Resource": [
        "arn:aws:s3:::your-bucket-name",
        "arn:aws:s3:::your-bucket-name/*"
      ]
    }
  ]
}
