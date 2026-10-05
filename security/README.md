# Security Measures

These are our technical and organisational measures, and Annex II of any data processing agreement we sign, including our own [DPA](../legal/DPA.md). Our [architecture](ARCHITECTURE.md) shows where data flows.

## 1. Program

**1.1 Ownership.** Our CEO owns security and these measures, and reviews them yearly.

**1.2 Standards.** We follow the SOC 2 Trust Services Criteria.

**1.3 People.** Everyone signs these measures, is background-checked, and is security-trained before getting access. Training repeats yearly.

**1.4 Acceptable Use.** Use company systems and data only for work, keep customer data on approved systems, report suspected incidents at once, and obey the law. Violations end access.

## 2. Access

**2.1 Least Privilege.** Staff get the access they need and nothing more, approved by our CEO.

**2.2 Strong Authentication.** Production access requires a physical security key—no exceptions. No credentials are shared.

**2.3 Access Reviews.** Access and admin activity are reviewed quarterly. Access is revoked the day someone leaves.

**2.4 Customer Sessions.** Sessions end 48 hours after sign-in, and every action rechecks membership.

**2.5 API Tokens.** Tied to organization, not per-user. Revocation within 60 seconds.

**2.6 Physical Security.** Our hosted regions run in our subprocessors' data centers, whose audited physical security we rely on. Our on-prem region, with our public dataset, sits in a locked, alarmed room and holds no customer data. Every device is tracked, screen-locked, and encrypted if it holds non-public data.

## 3. Data Protection

**3.1 Classification.** Uploads and verdicts are public; everything else is customer data.

**3.2 Minimisation.** IP addresses and user agents stop at Cloudflare's edge, unlogged. Scan servers see only the artifact asked about, and LLMs only excerpts of the scanner's evidence—never the file or who asked.

**3.3 Encryption.** Every connection uses TLS, authenticated as our [trust boundaries](ARCHITECTURE.md#trust-boundaries) describe. Cloudflare accepts only TLS 1.2 or newer, with FIPS-compliant cipher suites. Customer data lives in Workers KV, [encrypted at rest](https://developers.cloudflare.com/kv/reference/data-security/) with AES-256-GCM.

**3.4 Keys and Secrets.** We hold no encryption keys for customer data; Cloudflare manages them. Our secrets never live in code, and rotate at least every 180 days and at once on suspected exposure.

**3.5 Retention and Disposal.** Retention is in our [Privacy Policy](../privacy/README.md). When an agreement ends, we securely delete the customer's data within 30 days. Retired devices are destroyed per NIST SP 800-88.

## 4. Network and Infrastructure

**4.1 Perimeter.** Cloudflare is the only way in and absorbs denial-of-service attacks. Our colos have no inbound ports.

**4.2 Hardening.** Servers run a minimal, hardened operating system.

**4.3 Isolation.** Artifact analysis runs in disposable VMs with no path to production or customer data.

**4.4 Monitoring and Logging.** Automated alerts watch production around the clock and page our CEO, who is always on call. Request logs are kept 7 days in Cloudflare, where they can't be edited. Admin and audit logs—Cloudflare account activity, production access, and deploys—are kept 1 year.

## 5. Application Security

**5.1 Secure Development.** We build against the OWASP Top 10. Every change is documented and passes automated tests; risky changes also get AI review. Only approved, merged code reaches production; deploys refuse anything else.

**5.2 Separation of Environments.** Development stays separate from production.

**5.3 Vulnerability Reporting.** Researchers may test us under our [Vulnerability Disclosure Policy](VULN-DISCLOSURE.md).

## 6. Risk and Vendors

**6.1 Vendor Security.** We review every vendor's security yearly, including their SOC 2 or ISO 27001 report where one exists. See our [Approved Subprocessors](../privacy/SUBPROCESSORS.md).

**6.2 Risk Assessment.** We assess risk yearly and after major changes. See our [Risk Assessment](RISK-ASSESSMENT.md).

## 7. Vulnerability Management

**7.1 Scanning and Patching.** Hosts patch automatically and dependencies are scanned continuously. Vulnerabilities with an upstream fix are patched within 72 hours if critical, a week if high, and 90 days if medium.

**7.2 Penetration Testing.** An independent firm tests us yearly.

## 8. Continuity

**8.1 Recovery.** Our [Continuity Plan](CONTINUITY.md) sets how we recover each component. We back up all critical data and test restores yearly. Customer data backups stay within Cloudflare. RPO is 1 day; RTO is 7 days.

**8.2 Redundancy.** Analysis runs independently in four US regions: three hosting providers and one on-prem. Cached verdicts are served from Cloudflare even when every backend is down. Cloudflare is our only critical provider: if it is down, so are we.

## 9. Incidents

**9.1 Response Policy.** We handle incidents under our [Incident Response Plan](INCIDENT-RESPONSE.md), rehearsed yearly.

**9.2 Breach Notification.** We notify customers within 48 hours of discovering a breach, and regulators within 72 hours where the law requires.

## 10. Audits

**10.1 Independent Audits.** We will complete a SOC 2 Type II audit by September 21, 2027, then audit yearly. Findings are tracked and fixed on schedule.

**10.2 Reports.** We share our SOC 2 report, once available, and our penetration test summary on request.
