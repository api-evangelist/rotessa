---
name: Onboard a customer and start a recurring debit
description: Create a Rotessa customer from their bank details, then start a recurring PAD/ACH transaction schedule against that customer.
api: openapi/rotessa-openapi.yml
operations: [createCustomer, createTransactionSchedule]
---

# Onboard a customer and start a recurring debit

Use this skill to take a new payer from raw bank details to an active recurring
pre-authorized debit (Canada) or ACH (US) schedule.

## Authentication
All requests go to `https://api.rotessa.com/v1` (or `https://sandbox-api.rotessa.com/v1`
for testing) with the header:

```
Authorization: Token token="<your_api_key>"
Content-Type: application/json
```

## Steps

1. **Create the customer** — `POST /customers` (`createCustomer`).
   - Provide `name`, `account_number`, and either Canadian coordinates
     (`institution_number`, `transit_number`) or US coordinates
     (`routing_number`, `bank_account_type` = `Savings`|`Checking`).
   - Set a unique `custom_identifier` if you want to reference the customer by your
     own key later.
   - Capture the returned `id` (the Rotessa customer id).

2. **Create the recurring schedule** — `POST /transaction_schedules`
   (`createTransactionSchedule`).
   - `customer_id`: the `id` from step 1.
   - `amount`: the debit amount.
   - `process_date`: the first withdrawal date. **Must be at least 2 business days in
     the future** (else you get error_code `process_date_timing`).
   - `frequency`: one of `Once`, `Weekly`, `Every Other Week`, `Monthly`,
     `Every Other Month`, `Quarterly`, `Semi-Annually`, `Yearly`.
   - `installments`: number of debits; **omit for an indefinite schedule**. If sent it
     must be >= 1 (else error_code `installments_required`).

   > If you only hold your own identifier and not the Rotessa `id`, use
   > `POST /transaction_schedules/create_with_custom_identifier`
   > (`createTransactionScheduleWithCustomIdentifier`) with `custom_identifier` instead
   > of `customer_id`.

## Conventions and error handling
- No idempotency key exists — do not blindly retry a create on a network error; first
  re-query (`getCustomer` / `getTransactionSchedule`) to confirm whether it succeeded.
- Errors come back as `{ "errors": [ { "error_code", "error_message" } ] }`.
  `401` = bad/missing key, `422` = invalid data, `400` = bad parameters.
- See `conventions/rotessa-conventions.yml` and `errors/rotessa-problem-types.yml`.
