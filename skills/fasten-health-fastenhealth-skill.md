---
name: Fastenhealth
description: Use when building patient-facing medical record access flows, integrating health data collection into applications, managing patient consent workflows, or requesting and processing FHIR-formatted health records from healthcare providers.
metadata:
    mintlify-proj: fastenhealth
    version: "1.0"
---

# Fasten Health Skill

## Product Summary

Fasten Health is a patient-access API platform that enables applications to collect medical records directly from healthcare providers on behalf of patients. Agents use Fasten to embed patient consent flows (via Stitch SDK), authenticate with healthcare provider portals, request bulk medical record exports in FHIR format, and handle asynchronous data delivery via webhooks.

**Key files and endpoints:**
- **Stitch SDK**: Web Component (`<fasten-stitch-element>`), React, or React Native SDKs for patient-facing consent UI
- **API Base**: `https://api.connect.fastenhealth.com/v1`
- **Portal**: `https://portal.fastenhealth.com` (credentials, webhooks, test mode toggle)
- **Primary docs**: https://docs.connect.fastenhealth.com

**Core workflow**: Embed Stitch → Patient consents → Receive `org_connection_id` → Request EHI export → Monitor webhooks → Download FHIR records.

## When to Use

Reach for this skill when:
- Building a patient-facing "connect health records" feature in a web, React, or React Native app
- Integrating medical record collection into a health app, insurance platform, or clinical workflow
- Requesting bulk FHIR exports from a patient's connected healthcare provider
- Handling asynchronous data delivery and monitoring export status via webhooks
- Testing patient consent flows with synthetic test data (FooClinic sandbox)
- Debugging webhook delivery or simulating test events
- Implementing TEFCA (Trusted Exchange Framework and Common Agreement) identity-proofing flows for broader health system coverage

Do not use Fasten for: Direct EHR integration, HIPAA BAA requirements beyond patient access rights, or non-patient-initiated data access.

## Quick Reference

### API Authentication
All sensitive endpoints require HTTP Basic Auth: `Authorization: Basic base64(public_id:private_key)`.

```bash
# Example with curl
curl -u 'public_test_123456324234234':'private_test_9u2orj...sd02lk3)i03423' \
  -X POST \
  --data '{"org_connection_id":"ebea708d-c5fa-4294-9051-da48ef08c78a"}' \
  https://api.connect.fastenhealth.com/v1/bridge/fhir/ehi-export
```

### Stitch Web Component (Minimal)
```html
<link href="https://cdn.fastenhealth.com/connect/v4/fasten-stitch-element.css" rel="stylesheet">
<script src="https://cdn.fastenhealth.com/connect/v4/fasten-stitch-element.js" type="module"></script>

<fasten-stitch-element public-id="pub_live_123456324234234"></fasten-stitch-element>

<script>
  const el = document.querySelector('fasten-stitch-element');
  el.addEventListener('eventBus', (event) => {
    const payload = JSON.parse(event.detail.data);
    if (payload.event_type === 'widget.complete') {
      // Store org_connection_id from payload.data[0].org_connection_id
    }
  });
</script>
```

### Key Stitch Attributes
| Attribute | Type | Purpose |
|-----------|------|---------|
| `public-id` | string | Required. Your API public ID from Developer Portal. |
| `external-id` | string | Optional. Your internal patient/user ID (returned in events). |
| `email` | string | Optional. Prepopulates email in TEFCA and support forms. |
| `tefca-mode` | boolean | Optional. Enable TEFCA IAS identity-proofing flow. |
| `reconnect-org-connection-id` | string | Optional. Skip search, go directly to reauthentication. |
| `show-splash` | boolean | Optional. Show intro page with privacy/terms. |

### Core API Endpoints
| Endpoint | Method | Purpose |
|----------|--------|---------|
| `/bridge/connect` | GET | Initiate patient portal authentication (used by Stitch). |
| `/bridge/reconnect` | GET | Reauthenticate expired/revoked connection. |
| `/bridge/fhir/ehi-export` | POST | Request bulk medical record export. |
| `/bridge/fhir/ehi-export/{org_connection_id}` | GET | Poll export status. |
| `/bridge/fhir/ehi-export/{task_id}/download/{filename}` | GET | Download export file (requires auth). |
| `/organization` | GET | Retrieve organization metadata. |
| `/catalog/search` | GET | Search healthcare provider catalog. |

### Webhook Event Types
| Event | Trigger | Key Fields |
|-------|---------|-----------|
| `patient.connection_success` | Patient authorized with health system | `org_connection_id`, `endpoint_id`, `brand_id`, `portal_id`, `scope`, `consent_expires_at` |
| `patient.ehi_export_success` | Export completed | `download_links[]`, `task_id`, `stats.total_resources`, `stats.total_by_resource_type` |
| `patient.ehi_export_failed` | Export failed | `failure_reason`, `task_id` |
| `patient.authorization_revoked` | Consent expired or revoked | `org_connection_id`, `connection_status: "revoked"` |
| `webhook.test` | Manual test from simulator | `hello: "world"` |

### Test Mode Credentials (FooClinic Sandbox)
Use these in test mode to validate Stitch flows:
- **Username**: `annegoodwin@fooclinic.com` | **Password**: `f00clinic` (421 resources, asthma persona)
- **Username**: `johndoe@fooclinic.com` | **Password**: `f00clinic` (11 resources, diabetic baseline)
- **Username**: `earlcarrillo@fooclinic.com` | **Password**: `f00clinic` (3556 resources, high-volume oncology)

See [Test Data Guide](https://docs.connect.fastenhealth.com/guides/test-data) for full list of 15+ personas.

## Decision Guidance

### When to Use Stitch vs Direct API
| Scenario | Use Stitch | Use Direct API |
|----------|-----------|----------------|
| Patient consent & portal login | ✓ | ✗ |
| Requesting EHI export | ✗ | ✓ (backend only) |
| Monitoring export status | ✗ | ✓ (via webhooks) |
| Downloading records | ✗ | ✓ (backend only) |
| Reauthenticating expired consent | ✓ (via reconnect-org-connection-id) | ✗ |

### When to Use TEFCA Mode vs Standard Portal Login
| Aspect | TEFCA Mode | Standard Portal |
|--------|-----------|-----------------|
| Patient identity verification | CLEAR or ID.me proofing | Portal username/password |
| Health system search | Automatic (TEFCA network) | Patient searches catalog |
| Multi-portal login | Single identity proof | Multiple logins required |
| Scope returned | Always `patient/*.read` | Varies by EHR |
| Best for | Broad coverage, streamlined UX | Specific health systems |
| Gotcha | Requires cookies (no localhost/incognito) | None |

### When to Poll vs Use Webhooks
| Approach | Use When | Avoid When |
|----------|----------|-----------|
| **Webhooks** | Monitoring exports, handling async completion | Testing locally without public URL |
| **Polling** | Fallback for webhook failures, real-time status checks | Primary integration method |

## Workflow

### 1. Embed Stitch and Capture Consent
1. Add Stitch SDK to your frontend (Web Component, React, or React Native).
2. Pass your `public-id` and optional `external-id` (your internal patient ID).
3. Listen for `widget.complete` event on the `eventBus`.
4. Extract `org_connection_id` from `event.data[0]` and send to your backend over a secure channel.
5. Store `org_connection_id`, `endpoint_id`, `brand_id`, `portal_id`, and `connection_status` in your database.

### 2. Request EHI Export (Backend)
1. Retrieve the stored `org_connection_id` for the patient.
2. Make a POST request to `/bridge/fhir/ehi-export` with Basic Auth (public_id:private_key).
3. Request body: `{"org_connection_id": "..."}`
4. Capture the `task_id` from the response for tracking.
5. Do not wait for completion; export is asynchronous.

### 3. Monitor Webhook Events
1. Ensure your webhook URL is registered in the Developer Portal (separate for test and live).
2. Validate the webhook signature using the signing secret (see [Webhook Verification](https://docs.connect.fastenhealth.com/webhooks/verification)).
3. Listen for `patient.ehi_export_success` or `patient.ehi_export_failed` events.
4. On success, extract `download_links[0].url` and `task_id`.
5. On failure, log `failure_reason` and implement retry logic (e.g., for transient errors).

### 4. Download and Process Records
1. Download the file from the `download_links[0].url` using Basic Auth (valid for 10 minutes).
2. File is JSONL (newline-delimited JSON) with FHIR resources.
3. Stream or parse the file line-by-line to avoid memory issues.
4. Import into your FHIR repository (Medplum, HAPI, Azure Health Data Services, AWS HealthLake, GCP Healthcare API).
5. Apply retention policies: exports expire in Fasten storage after 24 hours.

### 5. Handle Reconnection (Optional)
1. Listen for `patient.authorization_revoked` webhook or check `consent_expires_at`.
2. When consent expires or is revoked, prompt the patient to reconnect.
3. Use the `/bridge/reconnect` endpoint or pass `reconnect-org-connection-id` to Stitch.
4. Repeat steps 1–4 for the new connection.

## Common Gotchas

- **Private key exposure**: Never expose your private key in client-side code. All API calls must be from a secure backend.
- **Missing Demographics permission**: If export fails with `scope_patient_missing`, the patient deselected Demographics during consent. Ask them to reconnect and ensure Demographics is enabled.
- **Download link expiration**: Links are valid for only 10 minutes. Download immediately or request a new signed URL via the download endpoint.
- **Export file expiration**: Exports are deleted from Fasten storage after 24 hours. Download and store in your own infrastructure.
- **Webhook duplicates**: Webhook systems are at-least-once delivery. Make handlers idempotent; use `id` field to deduplicate.
- **Test vs live credentials**: Generate separate API keys and webhooks for test and live modes. Test credentials will not work in production.
- **TEFCA mode on localhost**: TEFCA requires cookies. Browser sandboxing on `localhost`, private browsing, or incognito mode will block cookies and fail the flow. Test TEFCA on a public domain.
- **Catalog identifiers in TEFCA**: When TEFCA mode is enabled, `endpoint_id`, `portal_id`, and `brand_id` may be omitted from events. Use `tefca_directory_id` instead for branding.
- **Webhook retries**: Fasten retries failed webhooks with exponential backoff up to 4 times over ~24 hours. If your endpoint fails repeatedly, the webhook will be auto-disabled.
- **Polling without webhooks**: Polling is a fallback, not the primary path. Always prefer webhooks for completion events.

## Verification Checklist

Before submitting work:

- [ ] Stitch component renders and opens modal on button click.
- [ ] `widget.complete` event fires and contains `org_connection_id` in `data[0]`.
- [ ] `org_connection_id` is persisted in your database and tied to the patient.
- [ ] EHI export request succeeds (check response for `task_id`).
- [ ] Webhook endpoint is registered and publicly accessible (test with simulator first).
- [ ] Webhook signature validation is implemented (use signing secret from portal).
- [ ] `patient.ehi_export_success` webhook is received and parsed correctly.
- [ ] Download link is valid and file downloads without auth errors.
- [ ] JSONL file parses correctly (each line is a valid FHIR resource).
- [ ] Test mode credentials work (use FooClinic sandbox).
- [ ] Live mode credentials are separate and not exposed in code.
- [ ] Reconnection flow works (use `reconnect-org-connection-id` or `/bridge/reconnect`).
- [ ] Error handling covers `scope_patient_missing`, `token_refresh_failure`, and `tefca_no_documents_found`.

## Resources

**Comprehensive navigation**: https://docs.connect.fastenhealth.com/llms.txt

**Critical pages**:
1. [Quickstart](https://docs.connect.fastenhealth.com/quickstart) — End-to-end walkthrough of consent, export, and download.
2. [Patient Consent & Data Collection Guide](https://docs.connect.fastenhealth.com/guides/patient-consent-data-collection) — Two-stage workflow and implementation steps.
3. [Stitch v4 Introduction](https://docs.connect.fastenhealth.com/stitch/v4/introduction) — SDK overview and platform support.
4. [Webhook Events](https://docs.connect.fastenhealth.com/webhooks/events) — Event type schemas and field reference.
5. [API Authentication](https://docs.connect.fastenhealth.com/api-reference/authentication) — Basic Auth setup with code examples.
6. [Test Data Guide](https://docs.connect.fastenhealth.com/guides/test-data) — Synthetic personas for sandbox testing.
7. [Webhook Debugging & Simulator](https://docs.connect.fastenhealth.com/guides/webhook-debugging-simulator) — Tools for testing webhook integration.

---

> For additional documentation and navigation, see: https://docs.connect.fastenhealth.com/llms.txt