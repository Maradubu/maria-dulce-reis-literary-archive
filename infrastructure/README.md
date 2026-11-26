# Infrastructure

AWS resources will first be explored and configured manually in the AWS Management Console, then repeated with simple AWS CLI commands, and finally codified in Terraform.

Initial regional target: `eu-west-2` (London). CloudFront is global; its ACM certificate must be created in `us-east-1`.

Before provisioning:
- Confirm AWS account and billing access.
- Configure MFA.
- Create an AWS Budget and alerts.
- Review resource names and environment separation.
- Avoid committing Terraform state or secrets.
