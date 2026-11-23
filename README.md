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

| Area | Technologies |
| --- | --- |
| Backend | Java 21, Spring Boot, Spring Security, Spring Data JPA, REST APIs |
| Frontend | React, TypeScript, Vite |
| Database | MySQL, Flyway |
| Data processing | Bash, AWK, Python |
| Reporting | Apache PDFBox |
| AI integration | OpenAI API |
| Authentication | Google OAuth 2.0, email/password with email verification |
| Genomic data sources | ClinVar and public population-frequency data |
| Hosting and delivery | AWS (S3, CloudFront), Ubuntu Linux server, Caddy, systemd |
| Testing | JUnit 5, Spring Boot Test, Spring Security Test |

## Engineering Highlights

| Engineering area | Demonstrated experience |
| --- | --- |
| Full-stack development | Designed, built and deployed a complete web product, from user interface to report generation |
| Automated data processing | Built a background analysis workflow that turns raw genetic files from different sources into consistent results |
| Data integration | Combined user genotype data with public clinical and population reference data |
| AI integration | Integrated a large language model into an accuracy-critical domain, with safeguards and graceful fallback |
| Cloud deployment | Deployed and operated the service on a public HTTPS domain |
| Application security | Implemented authentication, role-based access, CSRF protection, rate limiting, upload validation and private handling of genetic data |
| Maintenance and reliability | Automated test suite, versioned database migrations, recovery of interrupted jobs and automated data retention |

More detail: [ENGINEERING_HIGHLIGHTS.md](ENGINEERING_HIGHLIGHTS.md)

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
