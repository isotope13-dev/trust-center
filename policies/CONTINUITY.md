# Continuity Plan

Our CEO leads recovery, as in our [Incident Response Plan](INCIDENT-RESPONSE.md). We aim to lose at most 1 day of data (RPO) and to recover within 7 days (RTO). Our [architecture](../architecture/README.md) shows the components.

## Failures

| Failure | Effect | Recovery |
| --- | --- | --- |
| Cloudflare | API and dashboard down | Wait for Cloudflare; or in the case of an extended outage; run elsewhere. |
| Customer data lost or corrupted | Sign-in and token checks fail | Restore the latest daily backup, held within Cloudflare |
| One analysis region | The other regions keep answering | Rebuild its servers from our deploy scripts |
| Every analysis region | Cached verdicts are still served; new analysis waits | Rebuild servers, most-used region first |
| Verdict master | Scan servers fail over to its replica | Rebuild the master from the replica |
| Our LLM | Grading falls back to OpenRouter, or to no second opinion | Restart or rebuild it |
| Our in-house dataset | None; serving customers doesn't depend on it | Restore from R2 or ZFS snapshots |
| A sign-in provider | Its users can't reach the dashboard; API tokens still work | Wait for the provider |
| Stripe | New purchases fail; existing access continues | Wait for Stripe, which retries its webhooks |

## Steps

1. **Declare:** start a dated log and tell affected customers what is down
2. **Restore:** the API first, then customer data, then analysis, then the dataset
3. **Verify:** confirm sign-in, token checks, and fresh analysis all work
4. **Review:** within two weeks, write up what happened and what we changed

## Testing

Each year we restore customer data from backup and rehearse losing a region, and keep the notes.
