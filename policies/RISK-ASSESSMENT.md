# Risk Assessment

Our CEO assesses risk yearly and after major changes. Uploads and verdicts are public, and queries aren't linked to accounts in our database, so there is little to steal. What remains:

| Risk | Likelihood | Impact | Mitigation |
| --- | --- | --- | --- |
| Training data corrupted to make malware look clean | Low | High | Caught in weekly triage and repaired automatically |
| Cloudflare account taken over to watch customer queries | Low | High | Security keys; queries kept 7 days |
| Code host account or dependency compromised to ship malicious code | Low | High | Security keys; dependencies scanned; only approved, merged code deploys |
| Denial of service against the customer API | Medium | Medium | Cloudflare absorbs it; 4 independent regions |
| Malware escaping an analysis VM | Low | Medium | Disposable VMs with no path to production or customer data |
| Data deleted, by mistake or attack | Low | Medium | Customer data backed up within Cloudflare; ZFS snapshots of our dataset; restores tested yearly |
| Fire or theft at our on-prem site | Low | Medium | The data there is public, and the other three regions keep serving; the dataset is backed up to Cloudflare R2 |
| Our CEO unavailable | Low | High | Production is automated; incident and vulnerability response waits for our return |
| Fraud: stolen cards buying access | Low | Low | Stripe screens payments |
| Fraud: our CEO bypassing controls | Low | Medium | Accepted: there's no one else to check |
| Personal data, including stolen credentials, in public uploads | Medium | Medium | [Data Protection Impact Assessment](DPIA.md) |
