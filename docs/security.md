# Security, Privacy and Permissions

## Roles

### Administrators
Initial members: Maria and the site administrator.

Can:
- Create and edit literary works.
- Save drafts.
- Publish and unpublish works.
- Upload and manage media.
- View subscriber administration information where required.
- Manage ordinary site content.

Cannot:
- Approve or reject comments unless also assigned the moderator permission.

### Comment moderators
Initial member: Maria only.

Can:
- View pending comments.
- Approve or reject comments.
- Hide or remove approved comments.
- Reply to comments, if the reply feature is enabled.

Maria belongs to both `Administrators` and `CommentModerators`. The site administrator belongs only to `Administrators`.

### Public readers
Can:
- Read published content.
- View approved comments.
- Submit comments.
- Subscribe and unsubscribe.

Cannot:
- Read drafts.
- Access the admin dashboard's protected API operations.
- View private email addresses or subscriber records.
- Moderate comments.

## Enforcement

- Enforce permissions in backend Lambda functions.
- Verify Cognito JWTs and group claims.
- Use least-privilege IAM roles for each Lambda function.
- Do not trust role names, user IDs or permission flags supplied by the browser.
- For moderation, require membership in `CommentModerators`; Maria is the only initial member.
- Log moderation decisions with the authenticated subject and timestamp.

## Authentication

- No public administrator registration.
- Create two administrator accounts manually.
- Require strong unique passwords and MFA.
- Do not share accounts.
- Provide a documented account recovery process.
- Never commit credentials or tokens to Git.

## Application security

- HTTPS only.
- S3 origin access through CloudFront OAC.
- Validate and size-limit uploads.
- Restrict allowed image formats and inspect file metadata.
- Use pre-signed S3 uploads with short expiry and constrained object keys.
- Validate and sanitise user input.
- Encode comment output to prevent cross-site scripting.
- Rate-limit public endpoints and add spam protection.
- Use secure, short-lived authentication sessions.
- Apply appropriate CORS restrictions.
- Keep dependencies updated.

## Privacy

- Collect only information needed to provide comments and subscriptions.
- Do not display commenter or subscriber email addresses.
- Obtain clear opt-in consent for email subscriptions.
- Use double opt-in and a working unsubscribe process.
- Document retention and deletion processes.
- Publish a privacy notice and cookie notice where required.
- Review UK GDPR and PECR obligations before launch.

## Operations

- Enable CloudTrail where appropriate.
- Use CloudWatch logs and alarms.
- Set log retention.
- Configure AWS Budgets alerts.
- Back up DynamoDB and important S3 content.
- Test restore procedures.
- Review IAM permissions before launch.
