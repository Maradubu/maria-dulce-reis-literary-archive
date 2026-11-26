# Architecture Decision Log

## ADR-001 — Serverless AWS architecture
**Decision:** Use S3, CloudFront, Cognito, API Gateway, Lambda, DynamoDB and SES as the initial AWS direction.

**Reason:** Avoid managing a continuously running server and gain practical experience with AWS services relevant to the project.

## ADR-002 — Two administrators, Maria-only comment moderation
**Decision:** Maria and the site administrator both receive administrator access. Maria alone receives comment-moderator permission.

**Implementation:** Separate Cognito groups/claims for `Administrators` and `CommentModerators`; backend functions enforce each permission.

## ADR-003 — Preserve original manuscripts
**Decision:** Original Portuguese and English texts are immutable archive sources. Editorial changes are separate versions.

## ADR-004 — Bilingual work model
**Decision:** Portuguese and English versions are linked under one stable work ID, but either language may be incomplete.

## ADR-005 — Moderated reader comments
**Decision:** All new comments begin as `pending`; only Maria can approve or reject them.

## ADR-006 — Double opt-in subscriptions
**Decision:** Subscription addresses become active only after the recipient confirms. Every email provides an unsubscribe route.

## ADR-007 — Learn AWS progressively
**Decision:** Console first, then AWS CLI, then Terraform, followed by CI/CD automation.
