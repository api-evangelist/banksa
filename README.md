# BankSA (banksa)

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
