# BankSA (banksa)

BankSA is a South Australian retail and business banking brand operating as a division of Westpac Banking Corporation (ABN 33 007 457 141, AFSL and Australian credit licence 233714). It shares the Westpac Group core banking platform alongside sibling brands St.George and Bank of Melbourne. Under Australia's Consumer Data Right (CDR / Open Banking) regime, BankSA exposes a live, public, unauthenticated Product Reference Data (PRD) API conforming to the DSB Consumer Data Standards, hosted at `digital-api.banksa.com.au`.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/banksa/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/banksa/refs/heads/main/apis.yml)

## Tags

- Financial
- Banks
- Open Banking
- CDR
- Consumer Data Right
- Consumer Banking
- Australia
- Product Reference Data

## Timestamps

- **Created:** 2026-07-20
- **Modified:** 2026-07-20

## APIs

### BankSA CDR Product Reference Data API

Public, unauthenticated Consumer Data Right Product Reference Data (PRD) endpoint listing BankSA banking products (`GET /banking/products`). Confirmed live returning HTTP 200 with an `x-v` response header (versions 4 and 5 supported) and a `data.products` array of 40 products across categories such as transaction and savings accounts, home loans, and credit cards. Conforms to the DSB Consumer Data Standards CDR Banking API contract.

- **Human URL:** [https://consumerdatastandardsaustralia.github.io/standards/#cdr-banking-api_get-products](https://consumerdatastandardsaustralia.github.io/standards/#cdr-banking-api_get-products)
- **Base URL:** `https://digital-api.banksa.com.au/cds-au/v1`

#### Tags

- CDR
- Open Banking
- Product Reference Data
- Banking
- Public

#### Properties

- [Documentation](https://consumerdatastandardsaustralia.github.io/standards/)
- [API Reference](https://consumerdatastandardsaustralia.github.io/standards/#cdr-banking-api_get-products)
- [OpenAPI](openapi/banksa-cds-banking-products-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### BankSA CDR Product Detail API

Public, unauthenticated Consumer Data Right endpoint returning full detail for a single product (`GET /banking/products/{productId}`). Confirmed live returning HTTP 200 with an `x-v` response header (versions 6 and 7 supported). Part of the same DSB Consumer Data Standards CDR Banking PRD surface as the product listing endpoint.

- **Human URL:** [https://consumerdatastandardsaustralia.github.io/standards/#cdr-banking-api_get-product-detail](https://consumerdatastandardsaustralia.github.io/standards/#cdr-banking-api_get-product-detail)
- **Base URL:** `https://digital-api.banksa.com.au/cds-au/v1`

#### Tags

- CDR
- Open Banking
- Product Reference Data
- Banking
- Public

#### Properties

- [Documentation](https://consumerdatastandardsaustralia.github.io/standards/)
- [API Reference](https://consumerdatastandardsaustralia.github.io/standards/#cdr-banking-api_get-product-detail)
- [OpenAPI](openapi/banksa-cds-banking-products-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

## Common Properties

- [Website](https://www.banksa.com.au/)
- [Privacy Policy](https://www.banksa.com.au/privacy)
- [Domain Security](https://www.banksa.com.au/security)
- [Support](https://www.banksa.com.au/help)
- [LinkedIn](https://www.linkedin.com/company/bank-sa)
- [Documentation](https://consumerdatastandardsaustralia.github.io/standards/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
