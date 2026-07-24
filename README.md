# Rotessa (rotessa)

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
