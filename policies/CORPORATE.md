# isotope13 LLC: Corporate Policies

### Acceptable Use

Don't be a jerk. Don't break the law.

### Access Control

You get the access you need and nothing more, reviewed regularly and revoked the day you leave. Authentication requires a physical security key—no exceptions.

### Artificial Intelligence

We use AI. Models never train on your account or requests. Uploads are public and may be used for training.

### Business Continuity & Backups

Our production API endpoints run independently in 4 US regions. We back up all critical data.

### Change Management

Every production change is documented, and every code and config change is reviewed before going live. Dev stays separate from production.

### Compliance

Our security program follows the SOC 2 Trust Services Criteria. We are working towards SOC 2 Type II and GDPR compliance with annual third-party audits. Findings are tracked and fixed on schedule.

### Data Lifecycle

Everything is encrypted at rest and in transit.

| Data | Shared | Kept |
| --- | --- | --- |
| Account: OAuth identity, org, tokens | No | Until you leave, then deleted within 30 days |
| Request logs: IP address, packages, URLs, hashes | No | 7 days |
| Usage metrics, per org | No | 90 days |
| Verdicts | Yes, with anyone asking about the same artifact | Indefinitely |
| Uploads | Yes, publicly downloadable | Indefinitely, even after you leave |

### Incident Response

Something breaks, we fix it fast. Critical incidents reach affected customers within 24 hours of discovery. That includes any unauthorized access to, loss, or disclosure of customer data, followed by a written report.

### Physical Assets

Every device is tracked and fully encrypted. Retired devices are destroyed using NIST SP 800-88 techniques.

### Risk Management

We assess risk yearly to spot threats and plan long-term mitigations.

### Security Operations

We avoid running our own operating system stack. Where we must, environments stay patched, firewalled, and monitored, with critical patches applied within 8 hours.

### Vendor

We avoid third-party vendors where possible. The ones we use face a yearly security review. See [Approved Subprocessors](../SUBPROCESSORS.md).
