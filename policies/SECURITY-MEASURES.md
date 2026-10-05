# Security Measures

These are the technical measures behind our [DPA](DPA.md) (Annex II). The organisational ones, from staff access to incident response, are our [Corporate Policies](CORPORATE.md). Our [architecture](../architecture/README.md) shows where data flows.

## Minimisation

* IP addresses and user agents stop at Cloudflare's edge, unlogged.
* Scan servers see only the artifact asked about, never who asked.
* Usage records hold an org ID and counts, never the artifact.

## Encryption and Isolation

* Every connection uses TLS, authenticated as our [trust boundaries](../architecture/README.md#trust-boundaries) describe.
* Customer data is encrypted at rest. Our providers hold the keys.
* Artifact analysis runs in disposable VMs with no path to production or customer data.

## Access

* Sessions end 48 hours after sign-in, and every action rechecks membership.
* API tokens carry 130 random bits, at most four per org. Revocation takes effect within 60 seconds.

## Availability

Four US regions each answer on their own. Without colo 1, the others grade with OpenRouter or answer without the LLM's second opinion. Scan servers fail over to a database replica. Backups: [Business Continuity](CORPORATE.md#business-continuity--backups).

We review these measures yearly with our [Risk Assessment](RISK-ASSESSMENT.md).
