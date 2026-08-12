<p align="center">
  <img src="assets/ismail-hassan-profile.jpg" width="130" alt="Photo of Ismail Hassan" />
</p>

<h1 align="center">Hi 👋, I'm Ismail Hassan</h1>

<h3 align="center">Cloud Security &amp; Information Security Engineer | Application Security | Security Operations</h3>

I am an information-security researcher and developer who enjoys understanding how systems fail, then building practical controls to make them safer. My work combines application-security research, cloud-security engineering, detection automation, and responsible vulnerability disclosure.

- 🔭 Building security-focused cloud and detection projects
- 🌱 Currently learning **Splunk, Microsoft Sentinel, and Wireshark** through legal home-lab exercises
- 💬 Ask me about **web/API security, IAM, Terraform, Python automation, and responsible disclosure**

## Security Operations & Detection 🛡️

I enjoy the full security-operations workflow: turning raw security events into useful alerts, investigating suspicious behaviour, and improving detections over time. The projects below are practical Python examples of log monitoring and defensive automation.

| Project | Detection focus | What it demonstrates |
| --- | --- | --- |
| [Failed Login Detector](https://github.com/hasinosec/failed-login-detector) | Potential brute-force activity | Analyses authentication logs, groups failed attempts by source IP, and flags repeated failures within a configurable time window. |
| [File Integrity Monitor](https://github.com/hasinosec/file-integrity-monitor) | Unexpected file changes | Creates SHA-256 baselines and identifies monitored files that have been modified, added, or deleted. |

These projects relate to common SOC activities: alert analysis, detection logic, investigation of suspicious activity, and automation of repetitive checks.

### Failed Login Detection Flow

![Illustrative workflow for the Failed Login Detector](assets/failed-login-detector-flow.svg)

### File Integrity Monitoring Flow

![Illustrative workflow for the File Integrity Monitor](assets/file-integrity-monitor-flow.svg)

## Cloud Security Engineering ☁️

I developed **File Vault**, a secure document-upload platform that models a small-company AWS architecture. The project is designed to demonstrate how security is built into cloud infrastructure: controlling identity access, protecting data, separating networks, securely managing secrets, and collecting audit evidence.

```mermaid
flowchart LR
    User[User] --> App[Application]
    App --> S3[Encrypted private S3 storage]
    App --> RDS[Private RDS PostgreSQL]
    App --> Secrets[AWS Secrets Manager]
    Audit[CloudTrail and CloudWatch] --- App
    Audit --- S3
    Audit --- RDS
```

![Illustrative File Vault architecture](assets/file-vault-architecture.svg)

*This is a simplified view of how I designed File Vault to protect documents, isolate data services, manage secrets, and capture security-relevant activity. Account-specific infrastructure details remain private during the final security review.*

File Vault demonstrates:

- **Identity and access management:** least-privilege IAM roles and narrowly scoped permissions help ensure each service has only the access it needs.
- **Network security:** VPC segmentation and private data services reduce unnecessary exposure of the database and storage layer.
- **Data protection:** encrypted, versioned S3 storage with public-access blocking helps protect uploaded documents from accidental exposure or loss.
- **Secrets management:** database credentials are stored in AWS Secrets Manager instead of source code or configuration files.
- **Visibility and auditability:** CloudWatch and CloudTrail support monitoring, log collection, and investigation of important cloud activity.
- **Infrastructure as code:** Terraform makes the cloud configuration repeatable, reviewable, and easier to assess for security misconfigurations.
- **Security automation:** GitHub Actions, Checkov, and Trivy are used to support CI/CD checks and policy-as-code scanning before infrastructure changes are deployed.

## Security Research & Bug Bounty 🔍

I have reported and helped resolve 10+ vulnerabilities through public bug bounty and coordinated-disclosure programmes, including reports affecting Budibase, DataZone.co, Beefree.com, Amplitude, Weights & Biases, Greptile, and CodeRabbit. My goal is to help organisations understand, fix, and prevent security issues through clear, responsible reporting.

### Research Areas & Testing Methodologies

**Access control & authentication:** broken access control, IDOR, missing authentication for critical functions, privilege escalation, authentication bypass, JWT testing, and role-based access-control testing.

**Web & API security:** SQL injection, stored/reflected/DOM XSS, CSRF, SSRF, RCE, path traversal, deserialisation risks, XXE, HTTP request smuggling, and WebSocket security testing.

**Application logic & data protection:** business-logic flaws, race conditions, insecure password-reset flows, information disclosure, PII exposure, JavaScript analysis, and API abuse.

**Modern security research:** prompt-injection testing and AI-application security research, performed only within authorised scope.

### CVEs Assigned

### CVE-2026-73407 — Critical

I reported an unauthenticated cross-origin authentication leak in Budibase REST datasources. A public query could send stored datasource credentials to an attacker-controlled destination. [Official advisory](https://github.com/budibase/budibase/security/advisories/GHSA-mqhr-6j6h-74p5)

### CVE-2026-73409 — High

I reported a server-side filesystem existence/read oracle caused by builder-controlled MongoDB certificate paths. The issue could reveal whether sensitive server-side paths existed. [Official advisory](https://github.com/budibase/budibase/security/advisories/GHSA-ppr4-5f46-j9c6)

### CVE-2026-25040 — Critical

I reported an API privilege-escalation issue where a Creator role could invite users with Admin or arbitrary roles. [Official advisory](https://github.com/budibase/budibase/security/advisories/GHSA-4wfw-r86x-qxrm)

### CVE-2026-25045 — Critical

I reported a missing-RBAC issue involving privilege escalation and IDOR in user-role management. [Official advisory](https://github.com/budibase/budibase/security/advisories/GHSA-2g39-332f-68p9)

### CVE-2026-25043 — Medium

I reported an unauthenticated password-reset endpoint that lacked rate limiting and could be abused for email flooding. [Official advisory](https://github.com/budibase/budibase/security/advisories/GHSA-277c-prw2-rqgh)

### What this demonstrates

These reports cover different security failure modes: access-control flaws, insecure API behaviour, credential exposure, unauthenticated attack paths, and unsafe server-side file handling. Together, they show how I investigate a vulnerability from discovery and impact analysis through responsible disclosure, remediation discussion, and public security-advisory publication.

## CTFs & Hands-On Security Learning 🎯

I use legal Capture The Flag (CTF) labs and learning environments to practise security skills safely. On [TryHackMe](https://tryhackme.com/p/Hasinosec), I have completed **262 rooms**, earned **23 badges**, and reached the platform's **top 1%** (rank **10,599** at the time of this update).

My completed labs cover Linux, networking, web and API security, enumeration, vulnerability analysis, exploitation fundamentals, and privilege escalation. CTFs help me understand how attackers discover weaknesses while reinforcing the defensive controls needed to prevent them.

### TryHackMe Learning Highlights

- **Security foundations:** Linux Fundamentals, Network Fundamentals, How the Web Works, Security Awareness, and Introduction to Security Engineering.
- **Web application security:** OWASP Top 10, SQLMap, web fundamentals, and practical testing concepts.
- **Infrastructure and cloud security:** Introduction to IaC Security and secure infrastructure concepts.
- **Windows and network labs:** Ice, Blue, Metasploitable, and other controlled environments for understanding Windows and network attack paths.
- **Research and investigation:** OhSINT, Hash Cracker, and Mr. Robot.
- **Consistency:** completed 7-day and 30-day learning streak challenges, plus Advent of Cyber 2024.

I am currently ranked **#53 on TryHackMe's Nigeria all-time leaderboard** (rank at the time of this update).

## Featured Projects

- **File Vault** *(private while sanitising infrastructure information)* — Terraform-managed AWS document platform with private RDS, encrypted S3, least-privilege IAM, logging, and CI security checks.
- [Failed Login Detector](https://github.com/hasinosec/failed-login-detector) — Python-based security-monitoring tool that analyses authentication logs, identifies repeated failed-login activity by source IP, and flags potential brute-force behaviour within a configurable time window.
- [File Integrity Monitor](https://github.com/hasinosec/file-integrity-monitor) — Python SHA-256 monitor that reports modified, new, and deleted files.

## Security Approach

I approach security from both sides: understanding how vulnerabilities can be discovered and abused, then applying controls that make systems more resilient.

```mermaid
flowchart LR
    Research[Security research] --> Controls[Preventive controls]
    Controls --> Monitoring[Monitoring and detection]
    Monitoring --> Triage[Alert triage and investigation]
    Triage --> Improvement[Improve controls and detection]
    Improvement --> Research
```

I am particularly interested in secure cloud architecture, API security, access control, monitoring, detection engineering, and incident response.

## Skills 🛠️

### ☁️ Cloud Security

AWS · IAM and least privilege · VPC and network segmentation · S3 encryption and public-access blocking · RDS security · AWS Secrets Manager · CloudTrail · CloudWatch · Terraform · policy as code · cloud-security posture management

### 🛡️ Security Operations & Detection

Security monitoring · log analysis · alert triage · threat hunting · incident response fundamentals · detection engineering · file-integrity monitoring · brute-force detection · vulnerability research

### 📚 Security Tool Learning Lab

I am building a legal home-lab workflow to practise security monitoring and network analysis on systems and traffic that I own or am explicitly authorised to test.

- **Wireshark:** inspecting packet captures to understand protocols, DNS requests, connections, and suspicious network patterns.
- **Splunk:** learning how to ingest logs, search events, build dashboards, and create simple detection queries.
- **Microsoft Sentinel:** learning SIEM concepts, log analytics, analytics rules, and incident investigation workflows.

This is an active learning area. I will publish a separate lab project with real, sanitised screenshots and documented findings after completing the exercises.

### 🔍 Application Security & Bug Bounty

OWASP Top 10 · OWASP API Security Top 10 · API testing · secure code review · SAST/DAST concepts · responsible disclosure · access-control testing · business-logic testing · web application penetration testing

### ⚙️ DevSecOps & CI/CD Security

GitHub Actions · infrastructure-as-code security · Checkov · Trivy · dependency and container-scanning concepts · security checks before deployment · secure configuration review

### 💻 Tools & Languages

Burp Suite · Python · JavaScript · Node.js · Terraform · Git · GitHub · AWS CLI

## Connect

- [LinkedIn](https://www.linkedin.com/in/ismail-h-1229a92a7/)
- [TryHackMe](https://tryhackme.com/p/Hasinosec)
