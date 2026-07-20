---
name: Browse BankSA public banking products
description: >-
  List and inspect BankSA's publicly available banking products through the
  Consumer Data Right Product Reference Data API — no authentication required.
api: openapi/banksa-cds-banking-products-openapi.yml
operations: [listBankingProducts, getBankingProductDetail]
auth: none (public CDR Product Reference Data)
base_url: https://digital-api.banksa.com.au/cds-au/v1
---

# Browse BankSA public banking products

BankSA's Product Reference Data (PRD) endpoints are public and unauthenticated —
they are mandated by the Australian Consumer Data Right for every active ADI. Use
them to enumerate and compare BankSA products.

## Rules
- **No auth**: send no `Authorization` header and no client certificate.
- **Version header is mandatory**: every request needs an `x-v` header.
  Use `x-v: 5` for the product list and `x-v: 7` for product detail (the highest
  versions BankSA confirmed live). A missing/unsupported version returns HTTP 406.
- **Pagination**: `listBankingProducts` supports `page` (default 1) and
  `page-size` (default 25, max 1000). Read `meta.totalRecords` / `meta.totalPages`
  and follow `links.next` until it is absent.
- **Errors** come back as `{ "errors": [ { code, title, detail } ] }` with
  `urn:au-cds:error:cds:*` codes — see `errors/banksa-problem-types.yml`.

## Steps
1. **List products** — call `listBankingProducts`
   (`GET /banking/products`) with header `x-v: 5`. Optionally filter with the
   `product-category` query param. Page through using `page`/`page-size`.
   BankSA returns ~40 products across transaction/savings accounts, home loans,
   and credit cards.
2. **Pick a product** — take a `productId` from `data.products[]`.
3. **Get detail** — call `getBankingProductDetail`
   (`GET /banking/products/{productId}`) with header `x-v: 7` to retrieve full
   features, rates, fees, eligibility and terms for that product.

## Notes
- These endpoints expose no consumer data — only published product terms.
- To read a consumer's own accounts/transactions you must become a CDR accredited
  data recipient; see `skills/banksa-consumer-account-data.md`.
