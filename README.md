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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Fasten Health is a healthcare data interoperability company offering a unified medical record platform that gives patients and developers access to clinical data across the U.S. healthcare system. Fasten began as an open source project — **Fasten OnPrem**, a self-hosted personal/family electronic medical record manager (GPL-3.0, 2.7k+ stars) that ingests FHIR Bundles and runs in Docker on a user's own infrastructure. The team has since productized the connectivity layer as **Fasten Connect**, a commercial REST + FHIR API and Stitch client SDK suite that retrieves patient clinical records from 50,000+ U.S. healthcare systems and 60,000+ organizations including Epic, Cerner, MyChart, Kaiser Permanente, HCA, Ascension, Humana, and Medicare.

Fasten is based in New York City and was founded by engineers who lived through the fragmentation of health data firsthand. The Fasten Connect platform exposes catalog discovery, patient connection orchestration, organization-connection status, bulk EHI (Electronic Health Information) export, TEFCA Individual Access Services workflows, webhook-driven async notifications, and embeddable Stitch UI components for Web, React, and React Native.

## APIs

| Name | Description |
| --- | --- |
| [Fasten OnPrem](https://github.com/fastenhealth/fasten-onprem) | Open-source, self-hosted personal/family electronic medical record manager. Go + TypeScript, GPL-3.0, runs in Docker, ingests FHIR Bundles. |
| [Fasten Connect API](https://docs.connect.fastenhealth.com/api-reference/introduction) | Commercial REST + FHIR API (OpenAPI 1.0.11) for retrieving clinical records from 50,000+ healthcare systems. Catalog, organization connection, EHI export, TEFCA. |
| [Fasten Connect Webhooks](https://docs.connect.fastenhealth.com/webhooks/introduction) | HMAC-verified webhook events for async export completion, connection lifecycle, and TEFCA workflow updates. |
| [Fasten Stitch Client SDKs](https://docs.connect.fastenhealth.com/stitch/v4/introduction) | Embeddable patient-authentication and consent component shipped as a framework-neutral Web Component, React SDK, and React Native SDK. |
| [Fasten Identity Proofing & TEFCA IAS](https://docs.connect.fastenhealth.com/identity-proofing/introduction) | NIST IAL2 identity proofing with Bring Your Own Identity, plus a TEFCA Individual Access Services developer guide. |
| [gofhir-models](https://github.com/fastenhealth/gofhir-models) | Apache 2.0 Go client library and generated FHIR R4 resource models. |
| [fhir-react](https://github.com/fastenhealth/fhir-react) | MIT React component library for rendering FHIR resources. |
| [Fasten Toolbox](https://github.com/fastenhealth/fasten-toolbox) | Standalone FHIR-based developer tools derived from the main platform. |
| [Folio](https://github.com/fastenhealth/folio) | Apache 2.0 modern Go PDF library: layout engine, HTML to PDF, forms, signatures, barcodes. |
| [Fasten Connect Quickstart](https://github.com/fastenhealth/fasten-connect-quickstart) | MIT JavaScript starter showing an end-to-end Fasten Connect integration. |
| [Fasten Answers AI](https://github.com/fastenhealth/fasten-answers-ai) | GPL-3.0 Python proof-of-concept for AI-powered health insights over a longitudinal medical record. |

## Tags

Healthcare, FHIR, Personal Health Record, Electronic Medical Record, Health Data Interoperability, TEFCA, EHI Export, Patient Consent, Self-Hosted, Open Source, HL7, Healthcare Connectivity

## Common Resources

- Website: <https://www.fastenhealth.com>
- Documentation: <https://docs.connect.fastenhealth.com>
- GitHub Organization: <https://github.com/fastenhealth>
- Blog: <https://blog.fastenhealth.com>
- Developer Portal / Sign Up: <https://portal.connect.fastenhealth.com>
- Changelog: <https://docs.connect.fastenhealth.com/changelog>
- FAQ: <https://docs.connect.fastenhealth.com/faqs>
- Support: <https://docs.connect.fastenhealth.com/support>
- Container Image: `ghcr.io/fastenhealth/fasten-onprem`
- License: GPL-3.0 (Fasten OnPrem); MIT / Apache 2.0 for SDKs and libraries

## Maintainers

- Kin Lane &lt;kin@apievangelist.com&gt;
