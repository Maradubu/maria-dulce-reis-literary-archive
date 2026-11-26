# Backend

Serverless API functions will be organised by domain:
- `works/` — create, update, list, publish and archive literary works.
- `comments/` — submit comments and Maria-only moderation.
- `subscriptions/` — opt-in, confirmation, unsubscribe and notification preferences.
- `shared/` — validation, authorisation and shared utilities.

Keep each Lambda function narrowly scoped and grant only the IAM permissions it needs.
