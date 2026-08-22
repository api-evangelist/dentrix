# Dentrix (dentrix)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
