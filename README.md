# Simpro

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

Simpro (simPRO) is field service management and project/business management software for the trades - electrical, plumbing, HVAC, security, fire, and other contractors. It covers the full workflow of estimating, quoting, job management, scheduling and dispatch, asset maintenance, inventory and catalog, purchasing, timesheets, and invoicing. The Simpro REST API v1.0 exposes these resources over HTTPS, but it is not a shared public API - each API runs on the customer's own Simpro Premium build (host https://your-build.simprosuite.com) and is authenticated with OAuth2 credentials provisioned by that build's administrator. Resources are nested under a company at /api/v1.0/companies/{companyID}/... where companyID is 0 on single-company builds.

**Areas:** Field Service · Trade · Job Management · Project Management · Scheduling · Inventory · Estimating · Workforce · Software-as-a-Service · Contractors

## Simpro on APIs.io

Everything profiled for Simpro is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/simpro/](https://apis.io/providers/simpro/)** — or go straight to one of the APIs or properties below.

### APIs (11)

- [Simpro Companies API](https://apis.io/apis/simpro/simpro-companies-api/) — Company information on the build (multi-company aware).
- [Simpro Cost Centers API](https://apis.io/apis/simpro/simpro-cost-centers-api/) — Accounting cost center setup.
- [Simpro Customers API](https://apis.io/apis/simpro/simpro-customers-api/) — Company and individual customers that receive invoices.
- [Simpro Invoices API](https://apis.io/apis/simpro/simpro-invoices-api/) — Customer invoicing.
- [Simpro Jobs API](https://apis.io/apis/simpro/simpro-jobs-api/) — Job lifecycle - scheduling, stock, assets, forms, and billing.
- [Simpro Quotes API](https://apis.io/apis/simpro/simpro-quotes-api/) — Quote creation and management.
- [Simpro Schedules API](https://apis.io/apis/simpro/simpro-schedules-api/) — Resource and staff scheduling records.
- [Simpro Sites API](https://apis.io/apis/simpro/simpro-sites-api/) — Customer sites and service locations.
- [Simpro Stock API](https://apis.io/apis/simpro/simpro-stock-api/) — Inventory held on storage devices.
- [Simpro Vendor Orders API](https://apis.io/apis/simpro/simpro-vendor-orders-api/) — Purchase orders raised to vendors/suppliers.
- [Simpro Webhooks API](https://apis.io/apis/simpro/simpro-webhooks-api/) — Webhook subscriptions for build event notifications.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Simpro Agentic Access](https://apis.io/agentic-access/simpro/simpro-agentic-access/)

#### Collections (12)

Postman and Open Collection request collections.

- [Simpro REST API](https://apis.io/collections/simpro/open-simpro/)
- [Simpro REST Companies API](https://apis.io/collections/simpro/open-simpro-companies-api/)
- [Simpro REST Companies Cost Centers API](https://apis.io/collections/simpro/open-simpro-cost-centers-api/)
- [Simpro REST Companies Customers API](https://apis.io/collections/simpro/open-simpro-customers-api/)
- [Simpro REST Companies Invoices API](https://apis.io/collections/simpro/open-simpro-invoices-api/)
- [Simpro REST Companies Jobs API](https://apis.io/collections/simpro/open-simpro-jobs-api/)
- [Simpro REST Companies Quotes API](https://apis.io/collections/simpro/open-simpro-quotes-api/)
- [Simpro REST Companies Schedules API](https://apis.io/collections/simpro/open-simpro-schedules-api/)
- [Simpro REST Companies Sites API](https://apis.io/collections/simpro/open-simpro-sites-api/)
- [Simpro REST Companies Stock API](https://apis.io/collections/simpro/open-simpro-stock-api/)
- [Simpro REST Companies Vendor Orders API](https://apis.io/collections/simpro/open-simpro-vendor-orders-api/)
- [Simpro REST Companies Webhooks API](https://apis.io/collections/simpro/open-simpro-webhooks-api/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Simpro Authentication](https://apis.io/security/simpro/simpro-authentication/)
- [Simpro Domain Security](https://apis.io/security/simpro/simpro-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Simpro Plans Pricing](https://apis.io/plans/simpro/simpro-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Simpro Rate Limits](https://apis.io/rate-limits/simpro/simpro-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Simpro Finops](https://apis.io/finops/simpro/simpro-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.simprogroup.com/)
- [Documentation](https://developer.simprogroup.com/)
- [Blog](https://www.simprogroup.com/blog)

## API Evangelist rating

**Kin Score 15.0** — emerging · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 66.1 |
| Contract quality | 12.1 |
| Contract governance | 0.0 |
| Operational transparency | 5.3 |
| Developer ergonomics | 21.4 |
| Access clarity | 7.9 |

**Agent readiness 22.9** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | negotiable (partial credit) |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | — |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | documented (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 11.8** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/simpro/](https://apis.io/providers/simpro/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Simpro: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/simpro/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
