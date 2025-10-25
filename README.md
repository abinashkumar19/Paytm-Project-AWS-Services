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


-----------------------------------------------------------------------------------------------------


2️⃣ Bucket Policy

The bucket policy should be applied to your S3 bucket. Replace placeholders with your actual account number, role name, and bucket name:

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::accountnumber:role/rolename"
            },
            "Action": "s3:*",
            "Resource": [
                "arn:aws:s3:::bucketname",
                "arn:aws:s3:::bucketname/*"
            ]
        }
    ]
}
