# Simpro (simpro)

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
