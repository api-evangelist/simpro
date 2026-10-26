# Simpro (simpro)

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

Simpro (simPRO) is field service management and project/business management software for the trades - electrical, plumbing, HVAC, security, fire, and other contractors. It covers estimating, quoting, job management, scheduling and dispatch, asset maintenance, inventory and catalog, purchasing, timesheets, and invoicing.

## Access Model (Read This First)

**Simpro's REST API v1.0 is not a shared, self-service public API.** It is a capability of a Simpro Premium subscription, and every point of access is scoped to a specific customer build:

- **Per-build host.** The API is served from the customer's own build subdomain - `https://{build}.simprosuite.com/api/v1.0` - the same domain used to log in to the Simpro staff portal. There is no single global API endpoint.
- **Customer-provisioned credentials.** Authentication is OAuth2. An account administrator registers an API application on the build and issues client credentials; the integration then requests access tokens from `https://{build}.simprosuite.com/oauth2/token` and sends them as `Authorization: Bearer ACCESS_TOKEN`. Both the client credentials and authorization code grants are supported.
- **Company-scoped resources.** Almost every resource is nested under a company: `/api/v1.0/companies/{companyID}/...`, where `companyID` is `0` on single-company builds and `>= 0` on multi-company builds.
- **Rate limit.** 10 API calls per second, scoped to the whole build (shared across companies and integrations). Over-limit requests return HTTP 429.

The catalog entry here models a representative subset of the API. The full published reference spans 300+ resource types.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/simpro/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/simpro/refs/heads/main/apis.yml)

## Tags

- Field Service Management
- Trades
- Job Management
- Project Management
- Scheduling
- Inventory
- Estimating
- Workforce
- SaaS
- Contractors

## Timestamps

- **Created:** 2026-07-12
- **Modified:** 2026-07-12

## APIs

All APIs share the per-build base URL `https://{build}.simprosuite.com/api/v1.0` and are documented at the [Simpro Developer Center](https://developer.simprogroup.com/apidoc/).

### Simpro Companies API

List and retrieve the companies configured on a Simpro build. The company is the top-level scope for nearly every other resource.

- **Human URL:** [https://developer.simprogroup.com/apidoc/](https://developer.simprogroup.com/apidoc/)
- **Base URL:** `https://{build}.simprosuite.com/api/v1.0`

#### Tags

- Companies
- Configuration

#### Properties

- [Documentation](https://developer.simprogroup.com/)
- [API Reference](https://developer.simprogroup.com/apidoc/)
- [OpenAPI](openapi/simpro-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/simpro.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/simpro.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Simpro Customers API

Create, list, retrieve, update, and delete company (organization) and individual customers - the entities that receive invoices for work performed.

- **Human URL:** [https://developer.simprogroup.com/apidoc/](https://developer.simprogroup.com/apidoc/)
- **Base URL:** `https://{build}.simprosuite.com/api/v1.0`

#### Tags

- Customers
- CRM

### Simpro Sites API

Manage customer sites and service locations that jobs, quotes, and assets are associated with.

- **Human URL:** [https://developer.simprogroup.com/apidoc/](https://developer.simprogroup.com/apidoc/)
- **Base URL:** `https://{build}.simprosuite.com/api/v1.0`

#### Tags

- Sites
- Locations

### Simpro Jobs API

Create, list, retrieve, update, and delete jobs - the core unit of field service work, tracking scheduling, stock, vendor orders, contractor work orders, customer assets, forms, and totals.

- **Human URL:** [https://developer.simprogroup.com/apidoc/](https://developer.simprogroup.com/apidoc/)
- **Base URL:** `https://{build}.simprosuite.com/api/v1.0`

#### Tags

- Jobs
- Work Orders
- Field Service

### Simpro Quotes API

Create, list, retrieve, update, and delete quotes and estimates, including their totals. Quotes convert to jobs within Simpro.

- **Human URL:** [https://developer.simprogroup.com/apidoc/](https://developer.simprogroup.com/apidoc/)
- **Base URL:** `https://{build}.simprosuite.com/api/v1.0`

#### Tags

- Quotes
- Estimating

### Simpro Invoices API

Create, list, retrieve, update, and delete customer invoices raised from jobs and projects.

- **Human URL:** [https://developer.simprogroup.com/apidoc/](https://developer.simprogroup.com/apidoc/)
- **Base URL:** `https://{build}.simprosuite.com/api/v1.0`

#### Tags

- Invoices
- Billing

### Simpro Schedules API

List and retrieve schedule records - the assignments of staff to jobs and activities that drive field workforce planning.

- **Human URL:** [https://developer.simprogroup.com/apidoc/](https://developer.simprogroup.com/apidoc/)
- **Base URL:** `https://{build}.simprosuite.com/api/v1.0`

#### Tags

- Scheduling
- Dispatch

### Simpro Vendor Orders API

Create, list, retrieve, update, and delete vendor (purchase) orders raised to suppliers for materials and stock.

- **Human URL:** [https://developer.simprogroup.com/apidoc/](https://developer.simprogroup.com/apidoc/)
- **Base URL:** `https://{build}.simprosuite.com/api/v1.0`

#### Tags

- Purchasing
- Vendor Orders

### Simpro Cost Centers API

Manage accounting cost centers under company setup that job and project financials are allocated against.

- **Human URL:** [https://developer.simprogroup.com/apidoc/](https://developer.simprogroup.com/apidoc/)
- **Base URL:** `https://{build}.simprosuite.com/api/v1.0`

#### Tags

- Accounting
- Cost Centers
- Setup

### Simpro Stock API

List and retrieve catalog stock items held on storage devices (warehouses, vans, and other locations).

- **Human URL:** [https://developer.simprogroup.com/apidoc/](https://developer.simprogroup.com/apidoc/)
- **Base URL:** `https://{build}.simprosuite.com/api/v1.0`

#### Tags

- Inventory
- Stock
- Catalog

### Simpro Webhooks API

Create, list, retrieve, update, and delete webhook subscriptions. Simpro POSTs HTTPS callbacks to your endpoint on subscribed build events - server-to-endpoint HTTP, not a streaming or WebSocket transport.

- **Human URL:** [https://developer.simprogroup.com/apidoc/](https://developer.simprogroup.com/apidoc/)
- **Base URL:** `https://{build}.simprosuite.com/api/v1.0`

#### Tags

- Webhooks
- Events
- Notifications

## Common Properties

- [Domain Security](security/simpro-domain-security.yml)
- [Authentication](authentication/simpro-authentication.yml)
- [LinkedIn](https://www.linkedin.com/company/simpro-software)
- [Website](https://www.simprogroup.com/)
- [Documentation](https://developer.simprogroup.com/)
- [Plans](plans/simpro-plans-pricing.yml)
- [Rate Limits](rate-limits/simpro-rate-limits.yml)
- [Fin Ops](finops/simpro-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
