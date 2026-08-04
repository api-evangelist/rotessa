# Rotessa (rotessa)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Rotessa is a Winnipeg, Manitoba-based fintech that helps small and mid-sized North American businesses collect recurring payments directly from their customers' bank accounts — over pre-authorized debit (PAD) in Canada and ACH in the United States. It positions bank-account payments as a low-cost alternative to card processing for invoices, memberships, subscriptions, tuition, and rent, and ships a genuine public REST API plus a free sandbox for developers.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/rotessa/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/rotessa/refs/heads/main/apis.yml)

## Tags

- Payments
- Canada
- Pre-Authorized Debit
- ACH
- Account-to-Account
- Bank Payments
- Recurring Payments
- Subscriptions
- Direct Debit
- Money Movement
- Open Banking

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-07-24

## APIs

The Rotessa API is a single versioned REST surface (`https://api.rotessa.com/v1`) documented as a one-page Slate reference. Authentication is by API key passed as `Authorization: Token token=<api_key>`. A free sandbox is available at `https://sandbox-api.rotessa.com/v1` (sign up at sandbox.rotessa.com). No downloadable OpenAPI/Swagger spec, Postman collection, or webhooks are published as of the review date.

### Rotessa Customers API

Create, retrieve, and update the customers (bank-account holders) that Rotessa withdraws recurring payments from — by Rotessa customer ID or a merchant-supplied custom identifier.

- **Human URL:** [https://rotessa.com/docs/#customers](https://rotessa.com/docs/#customers)
- **Base URL:** `https://api.rotessa.com/v1`

#### Tags

- Customers
- Bank Accounts

#### Properties

- [Documentation](https://rotessa.com/docs/#customers)
- [API Reference](https://rotessa.com/docs/#customers)

### Rotessa Transaction Schedules API

Create and manage one-time and recurring pre-authorized debit / ACH transaction schedules against a customer's bank account, including frequency, custom-identifier creation, PATCH/POST updates, and deletion.

- **Human URL:** [https://rotessa.com/docs/#transaction-schedules](https://rotessa.com/docs/#transaction-schedules)
- **Base URL:** `https://api.rotessa.com/v1`

#### Tags

- Transaction Schedules
- Recurring Payments
- Pre-Authorized Debit

#### Properties

- [Documentation](https://rotessa.com/docs/#transaction-schedules)
- [API Reference](https://rotessa.com/docs/#transaction-schedules)

### Rotessa Transaction Report API

Retrieve financial transaction records and their status (and status reasons) for reconciliation and reporting.

- **Human URL:** [https://rotessa.com/docs/#transaction-report](https://rotessa.com/docs/#transaction-report)
- **Base URL:** `https://api.rotessa.com/v1`

#### Tags

- Transactions
- Reporting
- Reconciliation

#### Properties

- [Documentation](https://rotessa.com/docs/#financial-transactions)
- [API Reference](https://rotessa.com/docs/#transaction-report)

## Common Properties

- [Website](https://rotessa.com/)
- [Developer Portal](https://rotessa.com/our-customers/developers/)
- [Documentation](https://rotessa.com/docs/)
- [API Reference](https://rotessa.com/docs/)
- [Getting Started](https://support.rotessa.com/rotessas-sandbox-and-api)
- [GitHub Organization](https://github.com/Rotessa)
- [LinkedIn](https://www.linkedin.com/company/rotessa)
- [Pricing](https://rotessa.com/pricing/)
- [Blog](https://rotessa.com/blog/)
- [Support](https://support.rotessa.com/)
- [Sign Up](https://rotessa.com/sign-up/)
- [Login](https://app.rotessa.com/login)
- [Terms of Service](https://rotessa.com/legal/)
- [Privacy Policy](https://rotessa.com/legal/privacy/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
