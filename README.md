# Ismail Hassan

**Information Security | Application Security | Penetration Testing**

Security researcher focused on finding and responsibly disclosing real-world application vulnerabilities. I am also building hands-on cloud security engineering skills through AWS infrastructure and security automation projects.

## Security Research & Bug Bounty

I have reported and helped resolve 10+ vulnerabilities through public bug bounty and coordinated disclosure programmes, including reports affecting Budibase, DataZone.co, Beefree.com, Amplitude, Weights & Biases, Greptile, and CodeRabbit.

Areas explored include:

- Broken access control and insecure direct object references (IDOR)
- Server-side request forgery (SSRF)
- Remote code execution (RCE)
- API and role-based access-control testing

### CVEs Assigned

| CVE | Advisory | Description |
| --- | --- | --- |
| [CVE-2026-25040](https://github.com/budibase/budibase/security/advisories/GHSA-4wfw-r86x-qxrm) | GHSA-4wfw-r86x-qxrm | Privilege Escalation via API Abuse — Creator Can Invite Users with Admin/Any Role |
| [CVE-2026-25045](https://github.com/budibase/budibase/security/advisories/GHSA-2g39-332f-68p9) | GHSA-2g39-332f-68p9 | Critical Privilege Escalation & IDOR via Missing RBAC on User Role Management (Creator-Role) |
| [CVE-2026-25043](https://github.com/budibase/budibase/security/advisories/GHSA-277c-prw2-rqgh) | GHSA-277c-prw2-rqgh | Unauthenticated Password Reset Endpoint Lacks Rate Limiting, Enabling Email Flooding |

## Cloud Security — Hands-On Learning

I am developing practical AWS cloud-security skills through **File Vault**, a secure document-upload platform that models a small-company architecture.

Current areas of work:

- Least-privilege IAM and scoped application permissions
- VPC network segmentation and private data services
- Encrypted, versioned S3 storage with public-access blocking
- Private RDS PostgreSQL and Secrets Manager for credentials
- CloudWatch and CloudTrail logging and audit trails
- Terraform infrastructure as code
- CI/CD and policy-as-code scanning with GitHub Actions, Checkov, and Trivy

## Featured Projects

- [File Vault](https://github.com/hasinosec/file-vault) — Terraform-managed AWS platform with private RDS, encrypted S3, least-privilege IAM, monitoring, and CI.
- [Failed Login Detector](https://github.com/hasinosec/failed-login-detector) — Python tool that detects potential brute-force attacks from authentication logs.
- [File Integrity Monitor](https://github.com/hasinosec/file-integrity-monitor) — Python SHA-256 monitor that reports modified, new, and deleted files.

## Skills & Interests

**Security Operations:** security monitoring, alert analysis, threat hunting, incident response, and vulnerability research.

**Application Security:** OWASP Top 10, API Security Top 10, secure code review, SAST/DAST concepts, and coordinated vulnerability disclosure.

**Cloud Security:** AWS, IAM, Terraform, CloudTrail, CloudWatch, policy as code, and cloud-security posture management.

**Tools & Languages:** Burp Suite, GitHub Actions, Checkov, Trivy, Python, JavaScript, and Node.js.
