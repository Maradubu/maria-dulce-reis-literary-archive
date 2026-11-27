# Maria Dulce Leitão Reis — Literary Archive

A bilingual literary archive and author portfolio dedicated to Portuguese poet and writer **Maria Dulce Leitão Reis**.

This project aims to create a digital home for Maria's literary work, bringing together her biography, books, poetry, prose, publications and creative contributions in a structured, accessible and thoughtfully designed online archive.

Beyond the public-facing website, the longer-term vision is to develop a publishing platform that allows content to be managed securely, preserves original manuscripts and supports ongoing literary publications.

## Project Overview

- **Public Literary Archive** — a bilingual Portuguese and English website presenting Maria's biography, literary catalogue, books, publications and written work.
- **Publishing Platform** — a secure administrative environment for managing publications, maintaining the literary catalogue and overseeing reader engagement.


## Current Development

The project is currently in its initial website development phase.

Work completed and underway includes:

- Git repository initialisation and project structure.
- Definition of the website's visual identity and design direction.
- Initial English homepage and biography page implementation.
- Shared CSS styling and responsive layout foundations.
- Initial literary catalogue structure using JSON metadata.
- Planning for bilingual content organisation and future publishing functionality.

Development is being approached incrementally, with the public website and content structure taking priority before backend services and cloud deployment are introduced.

## Technology Stack

The planned technology stack includes:

| Area | Technology |
|---|---|
| Frontend | HTML, CSS, JavaScript |
| Version control | Git and GitHub |
| Cloud hosting | AWS S3 and CloudFront |
| Authentication | Amazon Cognito |
| API | Amazon API Gateway |
| Serverless compute | AWS Lambda |
| Database | Amazon DynamoDB |
| Email notifications | Amazon SES |
| Infrastructure as Code | Terraform |
| CI/CD | GitHub Actions |

The AWS architecture will be developed progressively, beginning with practical implementation and testing through the AWS Management Console, followed by AWS CLI exercises and eventually infrastructure automation with Terraform.

## Planned Features

### Public Website

- Bilingual Portuguese and English interface.
- Author biography and interactive timeline.
- Literary archive with individual reading pages.
- Books and publications catalogue.
- Responsive design for desktop and mobile devices.

### Publishing and Administration

- Secure administrator authentication.
- Content and publication management.
- Separate publishing access for the author and site administrator.
- Structured storage of original Portuguese and English manuscripts.

### Reader Engagement

- Opt-in email subscriptions for new publications.
- Reader comments with moderation and approval reserved for the author.
- Notifications when new literary work is published.

### Cloud Infrastructure and DevOps

- AWS-hosted website and supporting services.
- Serverless backend architecture.
- Secure access management and application permissions.
- Infrastructure provisioning with Terraform.
- Automated testing and deployment through GitHub Actions.

## Repository Structure

```text
maria-dulce-reis-literary-archive/
│
├── website/
│   ├── en/                 # English website
│   ├── pt/                 # Portuguese website
│   ├── assets/
│   │   ├── css/            # Shared stylesheets
│   │   ├── js/             # Frontend JavaScript
│   │   └── images/         # Website imagery
│   └── admin/              # Future publishing interface
│
├── content/
│   ├── en/                 # English content
│   ├── pt/                 # Portuguese content
│   └── catalogue.json      # Literary catalogue metadata
│
├── backend/                # Planned serverless backend
├── infrastructure/         # AWS infrastructure and Terraform
├── schemas/                # Data structures and JSON schemas
├── docs/                   # Project and architecture documentation
└── tests/                  # Automated testing
```

## Development Approach

The project is being developed in stages:

1. Establish the website structure, visual identity and bilingual content organisation.
2. Implement the public literary archive and its core pages.
3. Introduce interactive functionality and structured content management.
4. Develop the AWS infrastructure and serverless backend.
5. Implement authentication, subscriptions and moderated comments.
6. Introduce Terraform, CI/CD and automated testing.

Each stage is intended to build on the previous one, with an emphasis on understanding the underlying technologies rather than simply deploying a finished solution.

## Project Status

**Active development — Initial website phase.**

The repository is evolving alongside the project. Features and architectural components described above represent the intended direction and are not necessarily implemented yet.

---

A personal literary archive developed with a focus on preserving original writing, thoughtful digital presentation and practical cloud engineering.