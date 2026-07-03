# Dentrix (dentrix)

Dentrix is a dental practice management platform from **Henry Schein One**, used by dental offices to manage patients, scheduling, clinical charting, treatment planning, insurance, and billing. Dentrix exposes third-party integration APIs through two distinct, partner-gated channels.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/dentrix/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/dentrix/refs/heads/main/apis.yml)

## Access Model (read this first)

Dentrix has **no public, self-serve API**. Both developer channels require an application, a use-case review, and a signed Dentrix API Agreement before an API key is issued, and both carry fees. There is no published OpenAPI specification, so the APIs listed here are **modeled** (`endpointsModeled: true`) from Henry Schein One's public developer materials rather than an official machine-readable contract.

### Two API surfaces — local vs. cloud

- **Dentrix Developer Program (DDP) — on-premise desktop.** Launched in 2012. Integrations run **locally** against the office's Dentrix database over password-protected **ODBC** connections, table views, stored procedures, and **DLL functions** (authenticated via a `RegisterUser` call). Per Henry Schein One: *"Dentrix is an on-premise application, and the Dentrix API is designed for on-premise integrations."* This is **not** a REST or cloud API — cloud integrations require a locally installed desktop agent acting as an intermediary. Over 100 stored procedures, table views, and DLL functions are documented across four categories: **Read API**, **Write API**, **Scheduling API** (commercial), and **Claims Summary API** (commercial). Supported languages include C#, C++, and Java (JDBC).

- **Dentrix Ascend API Exchange — cloud REST.** Launched July 2023. A **cloud REST/JSON API over HTTPS** on the SOC 2 Type II Dentrix Ascend platform, secured with **OAuth 2.0**. Exposes REST resources for patient information, scheduling, claim submission, and inventory, onboarded through a self-service vendor application.

- **Dentrix Enterprise API.** A separate on-premise API exists for larger group/DSO deployments.

## Tags

- Dental
- Practice Management
- Healthcare
- Dentistry
- Patient Data
- EHR
- Partner API
- Henry Schein One

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## APIs (modeled)

The following logical APIs are modeled from public developer materials. The concrete surface (endpoints, schemas, base URLs) is partner-gated.

### Dentrix Patients API

Retrieve and (with Write/Ascend scopes) manage patient demographics, contact details, household and responsible-party relationships, and status.

### Dentrix Appointments & Scheduling API

Read the schedule and book, reschedule, or cancel appointments (the commercial Scheduling API on the desktop; a REST scheduling resource on Ascend).

### Dentrix Providers API

Look up providers, operatories, and practice/location metadata used to associate appointments, procedures, and production.

### Dentrix Procedures & Treatment API

Access procedure codes (CDT), completed and planned procedures, treatment plans, and clinical notes.

### Dentrix Insurance & Claims API

Read insurance coverage and claim status, submit claims (Ascend), and pull practice-level claims reporting (the DDP Claims Summary API).

### Dentrix Ledger & Billing API

Access account ledgers, charges, payments, adjustments, and balances for patient and insurance reconciliation.

### Dentrix Prescriptions API

Read prescription and medication history from the patient clinical record (subject to program category and agreement).

## Pricing (see [plans](plans/dentrix-plans-pricing.yml))

- **DDP Read API:** $5,000 one-time registration + monthly royalty.
- **DDP Write API:** $5,000 one-time registration + monthly royalty (Scheduling and Claims Summary are additional commercial categories).
- **Dentrix Ascend API Exchange:** $47 per Ascend location per month, including 30,000 API calls and 3 GB data; overages at $0.0018/call and $1.00/GB.

Figures are drawn from public materials and are not reconciled against a signed agreement — verify current terms with Henry Schein One.

## Common Properties

- [Website](https://www.dentrix.com/)
- [LinkedIn](https://www.linkedin.com/company/henry-schein-one)
- [Documentation — Dentrix Developer Portal](https://ddp.dentrix.com/)
- [Documentation — Henry Schein One API Exchange](https://www.henryscheinone.com/dental-solutions/api-exchange)
- [Sign Up / Apply](https://ddp.dentrix.com/pages/faq)
- [Plans](plans/dentrix-plans-pricing.yml)
- [Rate Limits](rate-limits/dentrix-rate-limits.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
