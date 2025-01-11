# Assignment-2.15 Shakeela

# EC2 Access to AWS Secrets Manager

## **Step 1: Authorizing EC2 to Retrieve Secrets**

To allow an EC2 instance to retrieve secrets from AWS Secrets Manager:
1. Attach an **IAM Role** to the EC2 instance.
2. Create an **IAM Policy** with permissions for `secretsmanager:GetSecretValue` and `secretsmanager:DescribeSecret`.
3. Assign the policy to the IAM Role.

---

## **Step 2: IAM Policy**

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "secretsmanager:GetSecretValue",
        "secretsmanager:DescribeSecret"
      ],
      "Resource": "arn:aws:secretsmanager:ap-southeast-1:255945442255:secret:prod/cart-service/credentials"
    }
  ]
}
