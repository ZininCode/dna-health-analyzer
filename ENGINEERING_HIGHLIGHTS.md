# Engineering Highlights – DNA Health Analyzer

A concise overview of the engineering experience demonstrated by DNA Health Analyzer, a
publicly deployed web application for analyzing consumer DNA data. For a product overview, see
[README.md](README.md).

## Software Engineering

- Built an end-to-end product independently: requirements, user interface, backend services,
  persistent storage, report generation and deployment.
- Developed a Java 21 / Spring Boot backend and a React / TypeScript frontend, including sign-in
  flows adapted for both desktop and mobile browsers.
- Implemented complete user journeys: sign-in, consent, file upload, progress tracking, report
  viewing and downloads, support messaging and data deletion.
- Generated professional PDF reports and structured data exports directly from application data.
- Maintained an automated backend test suite (160+ tests) covering file handling, analysis
  processing, AI integration, reporting, security and data retention.

## Data Engineering and Automation

- Built an automated, background analysis workflow that takes a raw upload through to a completed
  report without manual intervention.
- Handled the inconsistency of real-world data: accepted raw data from different
  consumer genotyping services and produced uniform results from them.
- Integrated large public genomic reference datasets into the analysis.
- Managed schema evolution with versioned database migrations.
- Automated recurring operational tasks such as data retention and scheduled deletion.

## AI Integration

- Integrated a large language model API into a production workflow to produce plain-language
  explanations of genetic findings.
- Applied AI in a sensitive, accuracy-critical domain, combining AI output with established
  reference data rather than relying on the model alone.
- Designed the integration to be robust: the analysis still completes when the AI service is slow
  or unavailable, and AI usage is kept strictly on the server side.
- Communicated the role and limitations of AI-generated content clearly to end users.

## Cloud Infrastructure

- Deployed the application to a public HTTPS domain, combining AWS content delivery (S3 and
  CloudFront) with a self-managed Ubuntu Linux server.
- Configured native service management, HTTPS and a reverse proxy without relying on container
  tooling.
- Created repeatable deployment and operational scripts, including automated availability checks.

## Security and Reliability

- Implemented Google OAuth 2.0 and email/password authentication with email verification and
  password reset.
- Applied session-based authentication, role-based authorization, CSRF protection, per-user data
  isolation and rate limiting.
- Treated genetic data as highly sensitive: private storage, strict upload validation, explicit
  consent, user-requested deletion and time-limited retention.
- Kept secrets out of source control and frontend code.
- Built resilience into background processing, including clear user-facing error messages and
  safe recovery of interrupted jobs after a restart.
- Addressed privacy and regulatory considerations (GDPR) alongside the technical work.

## Bioinformatics and Domain Expertise

- Applied knowledge of human genetics: genotypes, zygosity, reference genome builds, clinical
  significance classifications and population allele frequencies.
- Worked with ClinVar and public population-frequency resources.
- Used the publicly available Genome in a Bottle HG002 reference sample to provide a realistic public demo without
  exposing personal data.
- Presented complex genetic evidence in a cautious, understandable way for non-specialist users,
  with clear statements of what the results can and cannot show.
