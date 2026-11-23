# DNA Health Analyzer

**A web application that turns raw consumer DNA data into an accessible, health-focused genetic variant report.**

🔗 **Live application:** [DNA Health Analyzer — North Genetics](https://north-genetics.com)

---

## Project Overview

Millions of people have raw DNA files from consumer genotyping services, but these files are difficult to interpret without specialist knowledge.

DNA Health Analyzer lets a user upload such a file and receive a structured report highlighting
genetic variants that public clinical sources associate with inherited conditions, drug
response, protective effects and other health-related traits. Each finding is placed in context
using the user's genotype, scientific classifications and population-frequency data, with
plain-language explanations aimed at non-specialists.

The service is designed as an educational and informational tool. Its reports encourage
further reading and discussion with healthcare professionals and are not a medical diagnosis.

DNA Health Analyzer is the first service of **North Genetics**, a life-science technology brand
focused on tools for genetic data analysis and interpretation.

## What It Does

### Input

A raw DNA data file downloaded by the user from a consumer genotyping service. Such a file is a
plain-text list of genetic markers, each with an identifier, a genomic position and the user's
genotype at that position.

### Output

- **Report summary** – an on-screen overview of the completed analysis.
- **PDF report** – a readable table of findings, each with its genotype, gene, population
  frequency, clinical significance, associated condition or trait, interpretation, importance
  rating and a plain-language summary, followed by explanatory notes and a disclaimer.
- **Extended data export** – a tab-separated file with the full finding details for users who
  want to explore the data further.

### Key Terms

| Term | Meaning |
| --- | --- |
| SNP | Single-nucleotide polymorphism – a position in the DNA where people commonly differ by a single letter (A, C, G or T). |
| rsID | A standard identifier for a known genetic variant, for example `rs1234`. |
| Genotype | The two letters a person carries at a position, one inherited from each parent. |
| Heterozygous / homozygous | Two different letters at a position / the same letter twice. |
| ClinVar | A public database of reported relationships between genetic variants and health conditions. |
| Clinical significance | The classification submitted to ClinVar, such as pathogenic, benign, risk factor or drug response. It is not a diagnosis. |
| Population frequency | How common a variant is in reference populations. Rare does not mean harmful, and common does not mean harmless. |
| Carrier status | The service's interpretation of a finding, e.g. *Functional variant*, *Recessive carrier*, *Neutral* or *Uncertain*. |
| Recessive carrier | One copy of a variant associated with a recessive condition; carriers are usually unaffected but may pass it on. |
| Importance | An AI-assisted rating (*High*, *Moderate*, *Low*, *Minimal*) of how informative a finding is – not a measure of disease risk. |
| AI interpretation summary | A short plain-language explanation of what the finding may mean. |

### Example Use Case

A person who has tested with a consumer genotyping service wants to know whether their raw data
contains anything health-related. They sign in, confirm consent and upload the file. When the
analysis is complete, the report lists, among other findings, a variant
labeled *Recessive carrier* for an inherited condition, with its population frequency, ClinVar
classification and a plain-language summary. The person downloads the PDF and brings it to a
genetic counselor or physician, who can decide whether confirmatory clinical testing is
appropriate.

*This is an illustrative scenario. Results are informational and require clinical confirmation
before any medical use.*

## Key Features

- **Raw DNA data upload** – accepts raw DNA data files exported by common consumer
  genotyping services.
- **Automated analysis** – uploaded files are processed in the background, and the user can follow
  the job status from upload to completed report.
- **Clinical variant annotation** – findings are matched against public clinical reference data,
  including ClinVar, and enriched with population-frequency context.
- **AI-assisted interpretation** – selected findings receive an AI-generated, plain-language
  summary and an importance rating, presented alongside the underlying evidence.
- **Reports** – an on-screen summary, a downloadable PDF report, and an extended tab-separated
  data export for users who want the full detail.
- **Public demo** – visitors can explore a complete read-only example report without creating an
  account.
- **Accounts and sign-in** – Google sign-in and email/password registration with email
  verification.
- **User support messaging** – an in-app mailbox for communication between users and the
  service administrator.
- **Privacy controls** – explicit consent before upload, user-requested deletion of analysis data,
  and automatic time-limited data retention.
- **Administration** – an administrator dashboard for service oversight and failed-job alerts.

## Technologies Used

- **Backend:** Java 21, Spring Boot, Spring Security, Spring Data JPA, REST APIs
- **Frontend:** React, TypeScript, Vite
- **Database:** MySQL
- **Data processing:** Bash, AWK, Python
- **AI integration:** OpenAI API
- **Genomic data sources:** ClinVar and public population-frequency data

## Engineering Highlights

### Software Engineering

- Built an end-to-end product independently: requirements, user interface, backend services,
  persistent storage, report generation and deployment.
- Developed a Java 21 / Spring Boot backend and a React / TypeScript frontend, including sign-in
  flows adapted for both desktop and mobile browsers.
- Implemented complete user journeys: sign-in, consent, file upload, progress tracking, report
  viewing and downloads, support messaging and data deletion.
- Generated professional PDF reports and structured data exports directly from application data.
- Maintained an automated backend test suite (160+ tests) covering file handling, analysis
  processing, AI integration, reporting, security and data retention.

### Data Engineering and Automation

- Built an automated, background analysis workflow that takes a raw upload through to a completed
  report without manual intervention.
- Handled the inconsistency of real-world data: accepted raw data from different
  consumer genotyping services and produced uniform results from them.
- Integrated large public genomic reference datasets into the analysis.
- Managed schema evolution with versioned database migrations.
- Automated recurring operational tasks such as data retention and scheduled deletion.

### AI Integration

- Integrated a large language model API into a production workflow to produce plain-language
  explanations of genetic findings.
- Applied AI in a sensitive, accuracy-critical domain, combining AI output with established
  reference data rather than relying on the model alone.
- Designed the integration to be robust: the analysis still completes when the AI service is slow
  or unavailable, and AI usage is kept strictly on the server side.
- Communicated the role and limitations of AI-generated content clearly to end users.

### Cloud Infrastructure

- Deployed and operated the application on a public HTTPS domain using AWS and a self-managed
  Ubuntu Linux server.
- Configured native service management, HTTPS and a reverse proxy without relying on container
  tooling.
- Created repeatable deployment and operational scripts, including automated availability checks.

### Security and Reliability

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

### Bioinformatics and Domain Expertise

- Applied knowledge of human genetics: genotypes, zygosity, reference genome builds, clinical
  significance classifications and population allele frequencies.
- Worked with ClinVar and public population-frequency resources.
- Used the publicly available Genome in a Bottle HG002 reference sample to provide a realistic
  public demo without exposing personal data.
- Presented complex genetic evidence in a cautious, understandable way for non-specialist users,
  with clear statements of what the results can and cannot show.

## Live Application

The application is publicly available at **[DNA Health Analyzer — North Genetics](https://north-genetics.com)**.
Select **View demo results** to explore a sample report without signing in. The demo uses the
publicly available HG002 reference genome sample from the Genome in a Bottle consortium rather
than data from any real user.

The service is currently offered free of charge during an introductory period.

## Development

DNA Health Analyzer was designed, developed and deployed as an independent project. The work
covers product definition, user experience, backend and frontend development, genetic data
processing, AI integration, reporting, security, cloud deployment and ongoing operation.

AI coding agents were used as development tools where appropriate, while requirements, design
decisions, review, testing and deployment remained under the author's responsibility.

## Source Availability

The source code is maintained in a private repository because the application contains
proprietary analysis and interpretation methods. This repository serves as a public overview of
the project. The technical work can be discussed in more depth on request.
