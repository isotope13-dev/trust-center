# isotope13 LLC: Corporate Policies

## Acceptable Use

Don't be a jerk. Don't break the law. Violating these policies ends access.

## Access Control

Everyone gets the access they need and nothing more, approved by our CEO, reviewed quarterly, and revoked the day they leave. Production access requires a physical security key—no exceptions.

## Artificial Intelligence

We use AI. Models train only on public uploads.

## Business Continuity & Backups

Production runs independently in 4 US regions. We back up all critical data and test restores yearly. RPO is 1 day; RTO is 7 days.

## Change Management

Every change is documented and passes automated tests before going live; risky changes also get AI review. Only approved, merged code reaches production. Dev stays separate from production.

## Compliance

Our CEO owns security and these policies, and reviews them yearly. We follow the SOC 2 Trust Services Criteria and are working towards SOC 2 Type II, then yearly third-party audits. Findings are tracked and fixed on schedule.

## Data Lifecycle

Uploads and verdicts are public; everything else is customer data, protected by our [Security Measures](SECURITY-MEASURES.md). What we keep, and for how long, is in our [Privacy Policy](PRIVACY.md). Secrets never live in code and rotate on suspected exposure.

## Incident Response

See our [Incident Response Plan](INCIDENT-RESPONSE.md).

## People

Everyone signs these policies, is background-checked, and is security-trained before getting access; training repeats yearly.

## Physical Assets

Every device is tracked, protected, and screen-locked, and encrypted if it holds non-public data. Retired devices are destroyed per NIST SP 800-88. Our dataset and backups are kept in-house; everything else runs in our subprocessors' data centers, whose audited physical security we rely on.

## Risk Management

See our [Risk Assessment](RISK-ASSESSMENT.md).

## Security Operations

Production is firewalled, logged, and monitored by automated alerts around the clock. Admin and deploy activity is reviewed quarterly. Hosts are patched automatically. Dependencies are scanned continuously. Vulnerabilities with an upstream fix are patched within 72 hours if critical, a week if high, and 90 days if medium.

## Vendor

We avoid vendors where possible; those we use get a yearly security review, including their SOC 2 or ISO 27001 report where one exists. See [Approved Subprocessors](../SUBPROCESSORS.md).
