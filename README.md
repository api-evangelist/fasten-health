# Fasten Health

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
