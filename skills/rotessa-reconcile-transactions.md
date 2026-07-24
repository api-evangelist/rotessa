---
name: Reconcile transactions and handle declines
description: Pull the Rotessa transaction report for a date range, classify each financial transaction by status, and act on declines/chargebacks using the PAD/ACH return reasons.
api: openapi/rotessa-openapi.yml
operations: [showTransactionReport, getTransactionSchedule]
---

# Reconcile transactions and handle declines

Use this skill to reconcile settled payments and triage failures.

## Authentication
Requests go to `https://api.rotessa.com/v1` with:

```
Authorization: Token token="<your_api_key>"
```

## Steps

1. **Pull the report** — `GET /transaction_report` (`showTransactionReport`).
   - `start_date` (required, `YYYY-MM-DD`) and optional `end_date`.
   - `status`: `All` (default), `Pending`, `Approved`, `Declined`, or `Chargeback`.
   - `page`: results are paginated at **1000 transactions per page**; increment `page`
     until a page returns fewer than 1000 rows.

2. **Classify each `FinancialTransaction` by `status`.**
   - `Approved` → settled successfully.
   - `Pending` → still processing; re-check on a later run.
   - `Declined` / `Chargeback` → read `status_reason` and act (see below).

3. **Act on declines/chargebacks** using `status_reason`
   (see `errors/rotessa-decline-codes.yml`):
   - `NSF`, `Funds Not Cleared` → transient; safe to let the schedule retry.
   - `Account Closed`, `Invalid/Incorrect Account No.`, `Account Not Found` → get
     corrected bank details from the customer, then update the customer.
   - `Agreement Revoked`, `Payment Stopped/Recalled`, `No Debit Allowed`,
     `Account Frozen` → do NOT retry; a new authorization or account is required.

4. **Inspect a schedule** if you need the source of a transaction —
   `GET /transaction_schedules/{id}` (`getTransactionSchedule`), where `id` is the
   `transaction_schedule_id` on the financial transaction.

## Conventions
- Filter server-side with `status` rather than pulling `All` and filtering locally.
- Errors: `{ "errors": [ { "error_code", "error_message" } ] }`;
  `406` means you requested a non-JSON format.
- See `conventions/rotessa-conventions.yml`.
