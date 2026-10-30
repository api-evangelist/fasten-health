# Fasten Health

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

Fasten Health is a healthcare data interoperability company offering a unified medical record platform that gives patients and developers access to clinical data across the U.S. healthcare system. Fasten began as an open-source project — Fasten OnPrem, a self-hosted personal/family electronic medical record manager that ingests FHIR Bundles and is distributed under GPL-3.0 with 2.7k+ GitHub stars. The team then productized the connectivity layer as Fasten Connect, a commercial REST + FHIR API and Stitch client SDK suite that lets developers retrieve clinical records from 50,000+ healthcare systems and 60,000+ organizations including Epic, Cerner, MyChart, Kaiser Permanente, HCA, Ascension, Humana, and Medicare. Founded by engineers who lived through the fragmentation of health data firsthand and based in New York City, Fasten ships GPL/MIT/Apache 2.0 open source repos alongside the hosted Fasten Connect platform.

**Areas:** Healthcare · FHIR · Personal Health Record · Electronic Medical Record · Health Data Interoperability · TEFCA · EHI Export · Patient Consent · Self-Hosted · Open Source · HL7 · Healthcare Connectivity

## Fasten Health on APIs.io

Everything profiled for Fasten Health is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/fasten-health/](https://apis.io/providers/fasten-health/)** — or go straight to one of the APIs or properties below.

### APIs (11)

- [Fasten OnPrem](https://apis.io/apis/fasten-health/fasten-onprem/) — Fasten OnPrem is an open-source, self-hosted, personal and family electronic medical record manager written in Go (47%) and TypeScript (35%). It runs as a…
- [Fasten Connect Webhooks](https://apis.io/apis/fasten-health/fasten-connect-webhooks/) — Fasten Connect emits HMAC-verified webhook events to notify integrators of asynchronous operations such as EHI export completion, connection lifecycle…
- [Fasten Stitch Client SDKs](https://apis.io/apis/fasten-health/fasten-stitch/) — Stitch is Fasten Connect's client-side embeddable component that lets a patient pick their healthcare provider, authenticate, and grant data-sharing consent…
- [Fasten Identity Proofing & TEFCA IAS](https://apis.io/apis/fasten-health/fasten-identity-proofing/) — Identity proofing endpoints and guides cover Fasten-issued identity verification as well as a Bring Your Own Identity path for integrators that already meet…
- [gofhir-models](https://apis.io/apis/fasten-health/gofhir-models/) — Apache 2.0 licensed Go client library and generated FHIR resource models used by Fasten's services to parse, validate, and emit FHIR R4 payloads. Maintained…
- [fhir-react](https://apis.io/apis/fasten-health/fhir-react/) — MIT-licensed React component library for rendering FHIR resources, useful for building patient portals and clinical viewers on top of Fasten data.
- [Fasten Toolbox](https://apis.io/apis/fasten-health/fasten-toolbox/) — Standalone FHIR-based developer tools derived from the main Fasten platform, including catalog browsing, display component previews, and other utilities for…
- [Folio](https://apis.io/apis/fasten-health/folio/) — Apache 2.0 licensed modern PDF library for Go with a layout engine, HTML-to-PDF conversion, form-fill support, digital signatures, and barcode rendering.…
- [Fasten Connect Quickstart Sample](https://apis.io/apis/fasten-health/fasten-connect-quickstart/) — MIT-licensed JavaScript starter project that demonstrates an end-to-end Fasten Connect integration — credential setup, Stitch embed, bulk EHI export…
- [Fasten Answers AI](https://apis.io/apis/fasten-health/fasten-answers-ai/) — GPL-3.0 licensed Python proof-of-concept for AI-powered health insights — exploratory work on conversational querying of a patient's longitudinal medical…
- [Fasten Health Bridge API](https://apis.io/apis/fasten-health/fasten-health-bridge-api/) — Customer (organization) facing APIs

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Fasten Health Webhooks](https://apis.io/asyncapis/fasten-health/fasten-health-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [fasten-connect](https://apis.io/servers/fasten-health/fasten-connect/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Fasten Health Agentic Access](https://apis.io/agentic-access/fasten-health/fasten-health-agentic-access/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Fasten Health Connect Overlay](https://apis.io/overlays/fasten-health/fasten-health-connect-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Fasten Health Authentication](https://apis.io/security/fasten-health/fasten-health-authentication/)
- [Fasten Health Domain Security](https://apis.io/security/fasten-health/fasten-health-domain-security/)
- [Fasten Health Trust Center](https://apis.io/security/fasten-health/fasten-health-trust-center/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Fasten Health Scopes](https://apis.io/scopes/fasten-health/fasten-health-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Fasten Health Plans Pricing](https://apis.io/plans/fasten-health/fasten-health-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Fasten Health Rate Limits](https://apis.io/rate-limits/fasten-health/fasten-health-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.fastenhealth.com)
- [Documentation](https://docs.connect.fastenhealth.com)
- [Getting started](https://docs.connect.fastenhealth.com/quickstart)
- [API reference](https://docs.connect.fastenhealth.com/api-reference/introduction)
- [Pricing](https://www.fastenhealth.com)
- [Sign up](https://portal.fastenhealth.com)
- [Support](https://docs.connect.fastenhealth.com/support)
- [Changelog](https://docs.connect.fastenhealth.com/changelog)
- [Blog](https://blog.fastenhealth.com)
- [Compliance](https://trust.fastenhealth.com/)
- [Terms of service](https://policy.fastenhealth.com/terms.html)
- [Privacy policy](https://policy.fastenhealth.com/connect/privacy_policy.html)
- [GitHub](https://github.com/fastenhealth)
- [Status](https://status.fastenhealth.com/)

## API Evangelist rating

**Kin Score 56.1** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 64.3 |
| Contract quality | 58.9 |
| Contract governance | 18.2 |
| Operational transparency | 42.1 |
| Developer ergonomics | 78.6 |
| Access clarity | 39.5 |

**Agent readiness 40.1** — agent-native

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | documented (partial credit) |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | yes |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 41.4** — Health

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/fasten-health/](https://apis.io/providers/fasten-health/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Fasten Health: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/fasten-health/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
