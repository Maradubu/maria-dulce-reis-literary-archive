# Maria Dulce Reis — Literary Archive

A bilingual Portuguese/English author portfolio, literary archive and publishing platform for Maria Dulce Reis.

## Project goals

- Present Maria Dulce Reis's biography, books, publications, recognition and peace initiatives.
- Preserve original Portuguese and English manuscripts as separate, linked versions.
- Provide a private publishing dashboard for Maria and the site administrator.
- Allow readers to submit comments, with approval reserved for Maria.
- Offer opt-in email subscriptions for new publications.
- Deploy a secure, serverless application on AWS.

## Initial technical direction

- Frontend: HTML, CSS and JavaScript (start simple; introduce a framework only if justified).
- Hosting and media: Amazon S3 and CloudFront.
- Authentication: Amazon Cognito.
- API: Amazon API Gateway and AWS Lambda.
- Data: Amazon DynamoDB.
- Email: Amazon SES.
- Infrastructure as code: Terraform, introduced after the Console and AWS CLI learning stages.
- CI/CD: GitHub Actions, introduced after the application and infrastructure are understood.

## Repository map

- `website/` — public site and private admin interface.
- `backend/` — API functions and shared backend code.
- `content/` — catalogue metadata and original manuscript files.
- `schemas/` — JSON data contracts.
- `infrastructure/` — architecture notes and future Terraform.
- `docs/` — project, architecture, security and implementation decisions.
- `tests/` — future automated tests.

## Important content-preservation rule

Original manuscripts must never be silently corrected or overwritten. Portuguese and English manuscripts are stored separately. Editorial corrections, if requested, must be saved as separate edited versions.

The current `content/catalogue.json` is a metadata index, not a complete copy of the manuscripts. Add the full original texts to the relevant language folders as they are transferred into the repository.

## Getting started

1. Open this folder in Visual Studio Code.
2. Read `docs/project-plan.md`.
3. Read `docs/architecture.md` and `docs/security.md`.
4. Review `content/catalogue.json` and resolve the outstanding editorial queries.
5. Begin the public website locally before provisioning AWS resources.

No AWS resources are created by this starter project.
