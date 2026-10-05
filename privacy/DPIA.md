# Data Protection Impact Assessment: Uploads

Uploads are public, shared with the security community, and used to train our models. Some contain personal data, like a maintainer's email in package metadata, an attacker's handle in malware, or credentials the malware stole. This is our GDPR Article 35 assessment, and the legitimate-interest balancing test behind our [Privacy Policy](README.md).

## Necessity

Malware can't be judged, or defended against, without its contents.

## Balancing

* **Our interest:** detecting supply-chain malware, which protects the same people the data is about
* **Their expectations:** most of it, like a maintainer's email, is already public; stolen credentials are not
* **Risk to them:** wider exposure of mostly public data; for stolen credentials, wider misuse, though publication also helps victims find and revoke them

## Safeguards

* We tell uploaders not to include personal data
* Uploads aren't linked to accounts or IP addresses, and request logs are deleted after 7 days
* We redact personal data from uploads on request

## Conclusion

Our interest outweighs the residual risk: low for most data, medium for stolen credentials. Neither is high, so no regulator consultation is needed. We review this yearly with our [Risk Assessment](../security/RISK-ASSESSMENT.md).
