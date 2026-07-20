---
name: Read a consumer's BankSA account data (CDR)
description: >-
  Retrieve a consenting consumer's BankSA accounts, balances and transactions
  through the Consumer Data Right, acting as an accredited data recipient under
  FAPI / OAuth2 with mTLS.
api: openapi/banksa-cds-banking-products-openapi.yml
operations: [listBankingAccounts, getBankingAccountDetail, listBankingBalancesBulk, getBankingBalance, listBankingTransactions, getBankingTransactionDetail]
auth: OAuth2 / OpenID Connect (FAPI 1.0 Advanced) + mTLS — CDR accredited data recipient
base_url: https://digital-api.banksa.com.au/cds-au/v1
---

# Read a consumer's BankSA account data (CDR)

These endpoints return a consumer's own banking data and are **only** reachable by
an accredited data recipient (ADR) that the consumer has consented to. This is not
a self-service developer flow — you must be accredited through the CDR Register.

## Prerequisites
- CDR accreditation and a client certificate from the CDR Register PKI.
- A consumer authorization obtained via the data holder's OpenID Provider using
  OAuth 2.0 authorization-code under **FAPI 1.0 Advanced** (PAR + PKCE + request
  objects). Tokens are **mTLS sender-constrained**. See
  `authentication/banksa-authentication.yml` and `scopes/banksa-scopes.yml`.
- The consent must grant the scopes each step needs.

## Rules
- Send `Authorization: Bearer <access_token>` over the mTLS channel, plus the
  FAPI headers (`x-fapi-auth-date`, `x-fapi-interaction-id`, and
  `x-fapi-customer-ip-address` for customer-present calls).
- Set `x-v` per endpoint version; handle HTTP 406 on unsupported versions.
- Paginate with `page` / `page-size`; follow `links.next`.
- Errors use the CDS envelope `{ "errors": [ ... ] }` — see
  `errors/banksa-problem-types.yml`.

## Steps
1. **List accounts** — `listBankingAccounts` (`GET /banking/accounts`), requires
   scope `bank:accounts.basic:read`. Filter with `product-category` /
   `open-status` if needed.
2. **Account detail** — `getBankingAccountDetail`
   (`GET /banking/accounts/{accountId}`), requires `bank:accounts.detail:read`.
3. **Balances** — `listBankingBalancesBulk`
   (`GET /banking/accounts/balances`) for all accounts, or `getBankingBalance`
   (`GET /banking/accounts/{accountId}/balance`) for one; scope
   `bank:accounts.basic:read`.
4. **Transactions** — `listBankingTransactions`
   (`GET /banking/accounts/{accountId}/transactions`) then
   `getBankingTransactionDetail`
   (`GET /banking/accounts/{accountId}/transactions/{transactionId}`); scope
   `bank:transactions:read`.

## Notes
- Regular payments (`listDirectDebits`, `listScheduledPayments`,
  `listInstalmentPlans`) need `bank:regular_payments:read`; payees
  (`listBankingPayees`) need `bank:payees:read`.
- All operations are read-only; there is no idempotency key.
