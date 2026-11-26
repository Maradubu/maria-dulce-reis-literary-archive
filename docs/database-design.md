# Data Model and Database Design

This document defines the initial logical model. Physical DynamoDB table and key design will be finalised after listing the API access patterns.

## Literary work

A work is the parent record shared by its language versions.

| Field | Type | Description |
|---|---|---|
| workId | string | Stable unique identifier |
| status | string | `draft`, `published`, `archived` |
| category | string | Poetry, prose, reflection, story, etc. |
| themes | string[] | Search/filter themes |
| publicationDate | string | ISO date `YYYY-MM-DD` |
| commentsEnabled | boolean | Whether readers may comment |
| notifySubscribers | boolean | Whether this publication triggers email |
| createdAt | string | ISO timestamp |
| updatedAt | string | ISO timestamp |
| publishedAt | string/null | Publication timestamp |
| createdBy | string | Cognito subject |
| updatedBy | string | Cognito subject |

Each language version contains:
- `language`: `pt` or `en`
- `title`
- `body`
- optional `excerpt`
- optional `slug`
- optional translation/editorial notes

Do not assume every work has both language versions. A work may be published in one language while the translation is pending.

## Comments

| Field | Type | Description |
|---|---|---|
| commentId | string | Unique identifier |
| workId | string | Related work |
| displayName | string | Public display name |
| email | string | Private contact address; never returned publicly |
| body | string | Submitted comment |
| status | string | `pending`, `approved`, `rejected`, `spam` |
| createdAt | string | Submission timestamp |
| moderatedAt | string/null | Moderation timestamp |
| moderatedBy | string/null | Moderator Cognito subject |
| reply | object/null | Optional author reply |

Public APIs return only approved comments and omit private fields.

## Subscribers

| Field | Type | Description |
|---|---|---|
| subscriberId | string | Unique identifier |
| email | string | Subscriber address |
| status | string | `pending`, `active`, `unsubscribed`, `bounced` |
| consentAt | string/null | Consent timestamp |
| confirmedAt | string/null | Confirmation timestamp |
| unsubscribedAt | string/null | Unsubscribe timestamp |
| preferredLanguage | string | `pt`, `en` or `both` |
| confirmationTokenHash | string/null | Hash only; never store raw token |
| createdAt | string | Record creation timestamp |

Avoid storing unnecessary personal information. Restrict access to subscriber records.

## Media

Media files are stored in S3. DynamoDB stores:
- `mediaId`
- `workId`
- S3 object key
- alt text
- caption
- content type
- file size
- upload timestamp
- uploader Cognito subject

## Audit and delivery records

Maintain records for:
- Publishing/unpublishing.
- Work edits and revision references.
- Comment moderation.
- Subscription consent and unsubscribe.
- Email notification attempts and delivery state.

Do not log passwords, raw confirmation tokens, full subscriber lists or unnecessary personal data.

## Data design principles

- Use stable IDs, not titles, as identifiers.
- Keep original manuscripts unchanged.
- Use ISO 8601 timestamps and ISO date strings.
- Validate all data at the API boundary.
- Define access patterns before selecting DynamoDB partition and sort keys.
- Add pagination to list endpoints.
