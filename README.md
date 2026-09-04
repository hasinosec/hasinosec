<p align="center">
  <img src="assets/header-banner.svg" alt="Ismail Hassan — Cloud Security & DevSecOps Engineer" width="100%" />
</p>

<h1 align="center">Ismail Hassan</h1>

<h3 align="center">Cloud Security &amp; DevSecOps Engineer&nbsp;|&nbsp;AWS &middot; Azure &middot; Terraform &middot; IAM &middot; Detection Engineering</h3>

## About

I work on cloud security and DevSecOps. I started in security research, finding and
reporting vulnerabilities, and moved to the other side: building the controls that
stop them.

Most of my time now is in AWS and Terraform — IAM, network design, encryption,
logging, and security checks in CI so bad configuration never reaches an account.
I also work with Azure. On the research side I have 5 assigned CVEs and valid bug
bounty reports on Bugcrowd and HackerOne.

**Reach me:** [LinkedIn](https://www.linkedin.com/in/ismail-h-1229a92a7/) · [Upwork](https://www.upwork.com/freelancers/~01e73f14f1161c7f0d) · manhasino@gmail.com

## Featured Projects

| Project | What it proves | Stack |
| --- | --- | --- |
| **[File Vault](https://github.com/hasinosec/file-vault)** | Security built into cloud infrastructure as reviewable code: least-privilege IAM, private data services, KMS encryption, secrets management, logging, security CI | Terraform · AWS · GitHub Actions |
| **[Failed Login Detector](https://github.com/hasinosec/failed-login-detector)** | Detection logic for brute-force activity: parse auth logs, group failures by source IP, alert on a threshold within a time window | Python · MITRE ATT&CK T1110 |
| **[File Integrity Monitor](https://github.com/hasinosec/file-integrity-monitor)** | SHA-256 baseline, then detect modified, new, and deleted files with severity | Python |
| **AWS Secure Baseline** *(building now)* | Account guardrails: org CloudTrail, Config + CIS pack, Security Hub, GuardDuty, IAM Identity Center, KMS, Prowler score in CI | Terraform · AWS Organizations |
| **Azure Secure Baseline** *(building now)* | Entra ID, Conditional Access and PIM as code, Azure Policy guardrails, Key Vault, diagnostics to Log Analytics | Terraform · Microsoft Entra |

## Cloud Security & DevSecOps

I harden a cloud account in layers and put the security checks in CI so nothing
insecure ships.

![Cloud security reference model](assets/cloud-security-model.svg)

**File Vault** puts this into practice — full [architecture and threat model](https://github.com/hasinosec/file-vault/blob/main/THREAT_MODEL.md) in the repo:

- The EC2 role can reach one S3 bucket, one secret, and the CloudWatch agent. Nothing else.
- The database runs in private subnets. Only the app's security group can connect to it.
- S3 is encrypted with a KMS key I manage, versioned, and blocks all public access. A bucket policy rejects any request that is not over TLS.
- The database password is generated and held by Secrets Manager. It never appears in the code or the Terraform state.
- The instance requires IMDSv2 and uses an encrypted root volume.
- Every push runs gitleaks, Checkov, tfsec and Trivy. Checkov reports 94 passing checks and 13 I chose to accept, each with a reason written in the code.

![DevSecOps pipeline](assets/devsecops-pipeline.svg)

## Security Research

Five CVEs, all in the Budibase platform, published as GitHub Security Advisories and
credited to [@Hasinohacker](https://github.com/Hasinohacker).

![CVE portfolio](assets/cve-portfolio.svg)

**Identity & access control**

- [CVE-2026-25040](https://github.com/budibase/budibase/security/advisories/GHSA-4wfw-r86x-qxrm) — Critical — Creator role can invite users with Admin or any role
- [CVE-2026-25045](https://github.com/budibase/budibase/security/advisories/GHSA-2g39-332f-68p9) — Critical — missing RBAC; privilege escalation and IDOR in role management

**Authentication**

- [CVE-2026-73407](https://github.com/budibase/budibase/security/advisories/GHSA-mqhr-6j6h-74p5) — Critical — REST datasource credential theft via cross-origin auth leak
- [CVE-2026-25043](https://github.com/budibase/budibase/security/advisories/GHSA-277c-prw2-rqgh) — Medium — unauthenticated password-reset endpoint with no rate limiting

**Server-side**

- [CVE-2026-73409](https://github.com/budibase/budibase/security/advisories/GHSA-ppr4-5f46-j9c6) — High — filesystem existence/read oracle via builder-controlled MongoDB certificate path

### Bug bounty

- **[Bugcrowd](https://bugcrowd.com/h/ismailhacker)** — 7 valid submissions, 77.78% accuracy
- Focus: broken access control, IDOR, business-logic abuse
- Hall of Fame: Amplitude
- **[HackerOne](https://hackerone.com/hasinohacker)** — valid report and thanks from Weights & Biases

## Hands-On Practice

![TryHackMe](assets/thm-stats.svg)

262 [TryHackMe](https://tryhackme.com/p/Hasinosec) rooms across Linux, networking, web
and API security, enumeration, and privilege escalation. Top 1% of users, and #53 on
the Nigeria all-time board.

## Skills

![Capability map](assets/capabilities.svg)

**Core capabilities**

- **Cloud (AWS):** IAM and least privilege, VPC and network segmentation, S3 and RDS hardening, KMS, Secrets Manager, CloudTrail, CloudWatch
- **Infrastructure as code:** Terraform — module design, remote state, plan review
- **DevSecOps:** GitHub Actions, Checkov, tfsec, Trivy, gitleaks, policy-as-code, dependency and container scanning
- **Application & API security:** OWASP Top 10 and API Security Top 10, access-control and business-logic testing, secure code review, Burp Suite
- **Languages:** Python, JavaScript and Node.js, Bash

**Also working with**

- **Azure:** Entra ID and RBAC, PIM, Conditional Access, Key Vault, Azure Policy, Microsoft Sentinel and KQL
- **Kubernetes:** admission policy, network policy, runtime detection
- **SIEM and analysis:** Splunk, Wireshark

## Now / Next

- **Now:** AWS Secure Baseline, Azure Secure Baseline, a policy-as-code guardrail kit for Terraform.
- **Next:** cloud detection rules (CloudTrail and Entra sign-in logs) mapped to MITRE ATT&CK, and a Kubernetes hardening lab.

## Connect

[LinkedIn](https://www.linkedin.com/in/ismail-h-1229a92a7/) &middot;
[TryHackMe](https://tryhackme.com/p/Hasinosec) &middot;
[HackerOne](https://hackerone.com/hasinohacker) &middot;
[Bugcrowd](https://bugcrowd.com/h/ismailhacker) &middot;
[Upwork](https://www.upwork.com/freelancers/~01e73f14f1161c7f0d)
