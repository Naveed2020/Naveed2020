<picture>
  <source media="(prefers-color-scheme: dark) and (max-width: 600px)" srcset="assets/profile-header-mobile-dark.svg">
  <source media="(max-width: 600px)" srcset="assets/profile-header-mobile.svg">
  <source media="(prefers-color-scheme: dark)" srcset="assets/profile-header-dark.svg">
  <img src="assets/profile-header.svg" alt="Naveed Amiri — Software Engineer. Applied AI, business applications, and systems integration." width="100%">
</picture>

**Based in Texas, United States.**

I’m Naveed Amiri, a software engineer building business applications, AI agents, and integrations that connect customer workflows with the systems behind them. My experience spans web and mobile development, Salesforce, government systems integration, and infrastructure operations.

Python and Django, React and TypeScript, and Flutter and Dart are central to my current work. My broader experience also includes **C#, .NET, and SQL Server**.

[Systems I Build](#systems-i-build) · [Technical Range](#technical-range) · [Winfolk](#winfolk--product-case-file) · [Fixophile](#fixophile--service-platform) · [Experience](#systems--integration-experience) · [Credentials](#credentials--platform-practice) · [Let’s Connect](#lets-connect)

---

## Systems I Build

| Focus | What I work on |
| --- | --- |
| **Application experiences** | Customer and admin workspaces, operational dashboards, maps, and reporting. |
| **Business workflows** | Lead follow-up, service booking, technician matching and onboarding, customer communication, and financial records. |
| **Backend services** | Domain models, tenant context, permissions, asynchronous processing, caching, and shared agent workflows. |
| **Connected platforms** | Business-system integrations, provider APIs, verified webhooks, messaging, website chat, and tenant-specific AI knowledge. |

## Technical Range

<picture>
  <source media="(prefers-color-scheme: dark) and (max-width: 600px)" srcset="assets/technology-stack-mobile-dark.svg">
  <source media="(max-width: 600px)" srcset="assets/technology-stack-mobile.svg">
  <source media="(prefers-color-scheme: dark)" srcset="assets/technology-stack-dark.svg">
  <img src="assets/technology-stack.svg" alt="Python, Django, React, TypeScript, Flutter, Dart, PostgreSQL, Redis, C sharp, .NET, SQL Server, and Docker" width="100%">
</picture>

| Discipline | Languages, tools, and practices |
| --- | --- |
| **Languages** | Python · TypeScript · JavaScript · Dart · C# · PHP · SQL |
| **Backend & APIs** | Django · Django REST Framework · .NET · REST APIs · Django ORM · authentication and permissions |
| **Web & mobile** | React · Flutter · Tailwind CSS · React Router · Riverpod · GoRouter · responsive interfaces |
| **Data & background work** | PostgreSQL · SQL Server · Redis · Celery · scheduled tasks · imports and exports |
| **Integrations & applied AI** | Messaging and email providers · webhook processing · knowledge retrieval · agent workflows · evaluation and human review |
| **Salesforce** | Platform administration · Apex · Flow · reports and dashboards · user authentication · MFA/SSO — through certifications and hands-on platform practice |
| **Cloud & infrastructure** | Microsoft Azure · hosting and deployment · DNS · servers and networking · data-center operations · Veeam · backup and recovery |
| **Delivery & diagnostics** | Git · Docker · Docker Compose · Vite · npm · pip · Flutter Pub · automated tests · structured logging |

Additional familiarity includes **Laravel** and **OAuth concepts**.

## Winfolk · Product Case File

### A connected workspace for home-service businesses

**Private project · Web and mobile · Small-group real-world testing**

I founded Winfolk to connect lead intake, customer conversations, scheduling, field work, and financial operations for contractors and trade businesses. I am developing it as a shared backend with a web dashboard and a mobile companion.

**My role:** Product requirements, architecture, implementation, integration testing, and ongoing troubleshooting across the backend, web, and mobile applications.

#### The problem

Contractors can lose inquiries when replies are slow or conversations are spread across channels. A single inquiry can then lead to an appointment, a job, and a financial record. Winfolk is designed to support timely follow-up and keep that history connected throughout the workflow.

<picture>
  <source media="(prefers-color-scheme: dark) and (max-width: 600px)" srcset="assets/winfolk-workflow-mobile-dark.svg">
  <source media="(max-width: 600px)" srcset="assets/winfolk-workflow-mobile.svg">
  <source media="(prefers-color-scheme: dark)" srcset="assets/winfolk-workflow-dark.svg">
  <img src="assets/winfolk-workflow.svg" alt="Winfolk connects lead intake, customer conversations, scheduling and jobs, field work, and financial operations, with supporting AI and platform services." width="100%">
</picture>

#### Product scope

| Product area | Capabilities |
| --- | --- |
| **Lead intake & CRM** | Website forms and widgets, external lead channels, customer records, and follow-up. |
| **Customer communication** | Shared inbox, SMS/MMS, email, call forwarding, templates, campaigns, and human takeover. |
| **Service delivery** | Services, jobs, technicians, service areas, interactive maps, and scheduling. |
| **Financial operations** | Invoices, transactions, budgets, receipt OCR, job costing, imports and exports, and lead-cost attribution. |
| **AI & automation** | Provider configuration, knowledge retrieval, website agents, chat workflows, evaluation, and human review. |
| **Platform administration** | Tenant lifecycle, billing, support, consent and retention workflows, audit history, and analytics. |

#### Engineering decisions

- **A shared service layer.** Django REST Framework serves the React dashboard and Flutter companion, with PostgreSQL for relational data and Redis for caching and background processing.
- **A shared Agent Engine.** Tenant-specific business knowledge, services, availability, and pricing context inform agent behavior. Channel adapters let messaging and website chat share business rules.
- **Durable notification delivery.** An outbox persists notifications before dispatch. Idempotency keys, bounded retries, and recovery of pending work help handle interruptions. Critical authentication email has a separate worker queue from routine and bulk traffic.
- **Explicit integration boundaries.** Provider adapters and webhook verification handle outside events; tenant middleware derives company context from authenticated membership.
- **Website integration.** A JavaScript widget and a WordPress integration path let businesses connect their existing websites. Telnyx SMS/MMS, inbound webhooks, and tenant phone-number routing support customer conversations.
- **Operational context.** Structured logs, correlation IDs, delivery history, and an HMAC-linked audit ledger support investigation. The repository also includes an optional monitoring stack.

**Planned channel:** Real-time voice support, building on the shared Agent Engine and channel-adapter design.

<details>
<summary><strong>Technology and integration inventory</strong></summary>

The inventory below reflects the repository manifests and configuration. Observability services are available through an optional Docker Compose profile.

#### Backend, data & documents

- **Languages & runtime:** Python 3.11 · TypeScript · JavaScript · Dart · PHP for the WordPress integration
- **Backend:** Django 4.2 · Django REST Framework · Django ORM · Simple JWT · django-cors-headers · Gunicorn · psycopg2-binary · python-dotenv
- **Data, cache & jobs:** PostgreSQL 15 · Redis 7 · Celery with Redis · Celery Beat · django-redis
- **Documents & spreadsheets:** openpyxl · pypdf · python-docx · CSV and Excel workflows · receipt OCR workflows

#### Web & mobile

- **Web application:** React 19 · React DOM · TypeScript 6 · Vite 8 · Tailwind CSS 4 · React Router 7 · Axios
- **Web UI & data tools:** MapLibre GL · Recharts · PapaParse · Lucide React
- **Frontend build & lint:** PostCSS · Autoprefixer · Oxlint · Vite React plugin · Tailwind PostCSS plugin · TypeScript type packages
- **Mobile application:** Flutter · Dart · flutter_riverpod · go_router · Dio · flutter_secure_storage · fl_chart · lucide_icons · google_fonts · intl · cupertino_icons

#### Integrations & AI

- **Messaging & email:** Telnyx · Twilio · Stalwart mail · SMTP
- **Lead channels & website:** Thumbtack · Angi · Google Local Services Ads · WordPress/PHP · website forms and widgets
- **AI capabilities:** Configurable AI-provider registry · knowledge retrieval · agent automation · website chat · evaluation and governance controls

#### Build, quality & operations

- **Build & packaging:** Docker · Docker Compose · pip · npm lockfile and `npm ci` · Flutter Pub · `tsc -b` · Vite build and preview
- **Tests & analysis:** Django test framework · Node `node:test` · Flutter `flutter_test` · Flutter lints · Oxlint
- **Optional observability stack:** OpenTelemetry Collector · Prometheus · Alertmanager · Grafana · Loki · Tempo

</details>

<details>
<summary><strong>Authentication, reliability, and data safeguards</strong></summary>

- **Authentication:** JWT and session authentication, OTP workflows, session revocation, and administrator TOTP enrollment through PyOTP. Mandatory administrator MFA enrollment is configurable.
- **Access & credentials:** tenant-aware request context, permission checks, scoped authentication throttles, and Fernet-encrypted credential fields through `cryptography`.
- **External events:** provider-specific webhook verification, delivery-state tracking, and unmatched-event records for manual review.
- **Background work:** notification outbox, idempotency keys, priority queues, retry backoff with jitter, circuit-breaker support, scheduling, and recovery of pending work.
- **Data lifecycle:** consent records, retention workflows, data-subject request handling, legal holds, and an HMAC-linked audit ledger with chain verification. Retention enforcement and audit behavior depend on configuration.
- **Diagnostics & tests:** structured JSON logs and correlation context; repository tests include login throttling, credential redaction, and correlation propagation.

</details>

## Fixophile · Service Platform

### On-demand support, at home and online

I develop Fixophile, a platform for booking technicians for in-home and online support. My full-stack work covers the customer booking experience and technician-partner onboarding.

| Workflow | What I build |
| --- | --- |
| **Customer booking** | Service-area selection, service categories, scheduling, and technician matching. |
| **Partner onboarding** | Personal information, location and skills, experience, and verification steps. |

I own the requirements, workflow design, implementation, testing, and iterative improvement of these experiences.

## Systems & Integration Experience

My experience also includes connecting organizational systems and supporting the infrastructure behind them.

- **Technical coordination.** Led an approximately six-person network and software team on an integration connecting the Ministry of Industry and Commerce’s ACBR licensing environment with the Ministry of Finance’s SIGTAS revenue system in Afghanistan.
- **Infrastructure operations.** Managed a government data-center function and supported hosted applications, networking, and organizational technology across government and education settings.
- **Backup and recovery.** Took on server-backup administration with Veeam alongside infrastructure responsibilities, helping protect critical organizational data.

## Credentials & Platform Practice

| Certification | Issued |
| --- | --- |
| **Salesforce Certified Platform Administrator** | January 2025 |
| **Salesforce Certified Platform Developer** | March 2025 |

**Salesforce Trailhead · Triple Star Ranger**

Five completed Superbadges cover reports and dashboards, user authentication, MFA and single sign-on settings, Flow administration, and Apex. This hands-on practice supports my work with platform administration, declarative automation, access management, reporting, and development.

## How I Engineer

- **Start with the workflow.** Translate business problems into requirements, break complex systems into manageable components, and give product areas clear responsibilities.
- **Keep access explicit.** Carry tenant context and permissions through requests, data access, and administrative actions.
- **Plan for provider failures.** Verify callbacks and give background work clear retry, failure, and recovery paths.
- **Make behavior traceable.** Keep logs, correlation context, delivery history, and audit records useful when investigating a problem.
- **Account for the data lifecycle.** Include consent, retention, and deletion workflows alongside core product features.
- **Check behavior at its boundaries.** Use focused tests for backend logic, frontend utilities, and mobile components.
- **Work across system boundaries.** Coordinate technical dependencies and troubleshoot across application, network, and infrastructure layers.

## Education

**Bachelor’s degree in Software Engineering**  
Ghalib University · Graduated 2016

## Let’s Connect

<picture>
  <source media="(prefers-color-scheme: dark) and (max-width: 600px)" srcset="assets/contact-intro-mobile-dark.svg">
  <source media="(max-width: 600px)" srcset="assets/contact-intro-mobile.svg">
  <source media="(prefers-color-scheme: dark)" srcset="assets/contact-intro-dark.svg">
  <img src="assets/contact-intro.svg" alt="Good software starts with a conversation. Get in touch for project discussions, engineering ideas, and professional connections." width="100%">
</picture>

<p align="center">
  <a href="mailto:naveed_amiri@yahoo.com"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/contact-email-dark.svg"><img src="assets/contact-email.svg" width="260" alt="Email Naveed Amiri: naveed_amiri@yahoo.com"></picture></a>
  <a href="https://www.linkedin.com/in/naveedamiri"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/contact-linkedin-dark.svg"><img src="assets/contact-linkedin.svg" width="260" alt="Connect with Naveed Amiri on LinkedIn: linkedin.com/in/naveedamiri"></picture></a>
  <a href="https://github.com/Naveed2020"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/contact-github-dark.svg"><img src="assets/contact-github.svg" width="260" alt="Visit Naveed Amiri on GitHub: @Naveed2020"></picture></a>
</p>
