# Project Plan

## Vision

Create an elegant bilingual literary home for Maria Dulce Reis that functions both as an author portfolio and as a self-managed publishing platform.

## Confirmed product decisions

- Public languages: Portuguese and English.
- Author identity: Maria Dulce Reis.
- Existing catalogue: 19 literary entries registered in the working archive.
- Two administrator accounts: Maria and the site administrator.
- Both administrators can create, edit, draft and publish literary entries.
- Only Maria can approve or reject reader comments.
- Readers can submit comments without receiving publishing access.
- Email subscriptions are opt-in and require confirmation.
- Original manuscripts are preserved unchanged; edited copies are separate.
- The initial visual direction is editorial and literary: warm ivory, forest green, muted terracotta, serif display typography and generous whitespace.

## User roles and permissions

| Capability | Maria | Site administrator | Reader |
|---|---:|---:|---:|
| Read published works | Yes | Yes | Yes |
| Create and edit works | Yes | Yes | No |
| Save drafts | Yes | Yes | No |
| Publish and unpublish | Yes | Yes | No |
| Upload images | Yes | Yes | No |
| Submit comments | Optional | Optional | Yes |
| Approve/reject comments | Yes | No | No |
| Manage subscribers | Yes | Yes | No |
| Manage application settings | Yes | Yes | No |

The role design must distinguish general administration from comment moderation. Maria belongs to both the `Administrators` and `CommentModerators` permission groups. The site administrator belongs to `Administrators` only. The backend must enforce this on every moderation request.

## Delivery phases

### Phase 1 — Foundation
- Establish repository and documentation.
- Create content catalogue and JSON schemas.
- Resolve content metadata queries.
- Agree on domain, account ownership and operational responsibilities.

### Phase 2 — Public website
- Responsive homepage and navigation.
- Biography and books.
- Bilingual literary archive and individual reading pages.
- Search and filters.
- Recognition, publications, peace initiatives and contact information.

### Phase 3 — AWS foundation
- Choose and configure AWS account and region.
- S3 and CloudFront hosting.
- Domain, DNS and HTTPS.
- API Gateway, Lambda and DynamoDB.
- Logging, budget alerts and security baseline.

### Phase 4 — Author dashboard
- Cognito sign-in and role-based permissions.
- Create, edit, save draft, preview, publish and unpublish.
- Upload and manage photographs.
- Link Portuguese and English versions of the same work.
- Revision history and safe deletion/archive behaviour.

### Phase 5 — Reader comments
- Public comment submission.
- Pending moderation queue.
- Maria-only approval and rejection.
- Replies, reporting, spam controls and rate limits.

### Phase 6 — Email subscriptions
- Subscriber sign-up and double opt-in.
- Confirmation and unsubscribe workflows.
- Publication notification preferences.
- SES domain authentication and sending configuration.

### Phase 7 — Quality, automation and launch
- Accessibility, responsive and browser testing.
- Security and privacy review.
- Backups and recovery test.
- GitHub Actions CI/CD.
- Monitoring, documentation and launch checklist.

## Learning and delivery approach

Build and test locally first. For AWS, follow this learning sequence:

1. AWS Management Console.
2. Simple AWS CLI operations.
3. Terraform for repeatable infrastructure.
4. GitHub Actions for automated testing and deployment.

Do not create production AWS resources until the design, budget controls and account access have been reviewed.

## Initial non-functional requirements

- Mobile-friendly and accessible.
- Secure by default; least privilege.
- HTTPS throughout.
- Public visitors cannot access drafts or private dashboard operations.
- Original text and publication metadata must be preserved.
- Subscription consent and unsubscribe must be recorded.
- Reader email addresses must never be shown publicly.
- All moderation actions must be attributable to the authenticated moderator.
- Maintain backups and a documented recovery process.
