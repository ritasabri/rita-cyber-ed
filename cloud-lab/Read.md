# Rita Cyber Ed — Cloud Bank Heist Lab

A free, open-source classroom lab for teaching **cloud security misconfigurations** to high school and early-college students. Built by Rita Sabri (CS & Cybersecurity Educator, Cardozo Education Campus, Washington D.C.) as a module of the **Curriculum Patch** framework — a methodology for retrofitting existing CS and cybersecurity curricula to address modern cloud and AI threats. Runs entirely in the browser. **No AWS account required.**

🔗 **Try it now:** [ritasabri.github.io/rita-cyber-ed/cloud-lab/](https://ritasabri.github.io/rita-cyber-ed/cloud-lab/)

---

## What this is

Students step into the role of a **junior security analyst at FirstTrust Bank**, which has just migrated to AWS. With read-only access to the production environment, they inspect six AWS services, flag the five real misconfigurations, and — crucially — learn to tell a true misconfiguration apart from a resource that is **public by design**. The lab runs as a 45-minute lesson and needs no AWS account, no API keys, and no budget.

---

## Why it matters

- **Cloud misconfigurations are among the leading causes of real-world breaches.** The 2019 Capital One breach (~100M records) traced back to a misconfigured S3 bucket and an over-permissive IAM role — the exact issues students hunt in this lab.
- Every finding maps to a control in the **CIS AWS Foundations Benchmark v3.0**, the industry-standard cloud security checklist.
- **Cloud security is one of the most in-demand skill areas** in cybersecurity — yet most K–12 CS and cybersecurity curricula don't teach it hands-on.
- Built to clear the real barriers: no budget, no AWS account, no API keys, nothing for a school firewall to block.

---

## What's in this repo

| File | What it is | Use for |
|---|---|---|
| `index.html` | Interactive audit lab (single HTML file, no build) | Deploy via GitHub Pages; share URL with students |
| `Cloud_Bank_Heist_Lab_Student_Handout.tex` / `.pdf` | Student audit sheet: goal, warm-up, guided audit, CER exit ticket | Print one per student; collect after lab |
| `Cloud_Bank_Heist_Teacher_Key.pdf` | **CONFIDENTIAL** — the five findings, the trap, and scaffolded hints | Teacher reference only; do not distribute |
| `Cloud_Bank_Heist_NICE_Alignment.pdf` | NICE Framework alignment guide | Show admins; embed in PD; justify the lesson |
| `README.md` | This file | Folder navigation |

---

## What students audit: six services, five findings

| # | Service | The issue | Severity | NICE Work Role |
|---|---|---|---|---|
| 1 | `customer-data-prod` (S3 bucket) | Public to the internet — exposes customer PII and SSNs | Critical | Vulnerability Analysis (PD-WRL-007) |
| 2 | `DeveloperRole` (IAM role) | AdministratorAccess wildcard, no MFA, used by interns | Critical | Cybersecurity Architecture (DD-WRL-001) |
| 3 | `payment-processor` (Lambda) | AWS keys, Stripe key, and DB password hardcoded in source | Critical | Secure Software Development (DD-WRL-003) |
| 4 | `production-audit-trail` (CloudTrail) | Logging disabled — no record of any activity | Critical | Defensive Cybersecurity (PD-WRL-001) |
| 5 | `db-server-sg` (Security group) | SSH (22) and MySQL (3306) open to `0.0.0.0/0` | Critical | Systems Security Analysis (IO-WRL-006) |
| 6 | `marketing-assets-public` (S3 bucket) | Public — but **by design**. The trap: flagging it is a false positive. | — | Analyst judgment (T1348) |

---

## How to use this in your classroom

**Quick start (10 minutes):** open the lab, print one handout per student, skim the teacher key so you can give scaffolded hints, then run it as a 45-minute lesson.

### Suggested 45-minute lesson flow

| Time | Phase | What happens |
|---|---|---|
| 0–5 min | Framing | Hook: the Capital One breach was one S3 bucket. Introduce shared responsibility. |
| 5–10 min | Mission brief | Open lab; students read the analyst mission. Set the rule: evidence before flagging. |
| 10–30 min | Audit phase | Students inspect all six services, recording findings and evidence on the handout. |
| 30–40 min | Analysis | Section B metacognitive questions + Think–Pair–Share. |
| 40–45 min | Debrief | Reveal the trap; discuss false positives; tour the careers in the "Did You Know?" boxes. |

### Lab controls

- **Reset audit** — clears all findings to run again
- **Export findings** — generates a plain-text audit report of the student's decisions
- **Show solution summary** — appears after all five critical findings are caught (teacher reveal)

---

## Standards alignment

Verified against the **NICE Workforce Framework for Cybersecurity v2.2.0**.

### NICE Framework Work Roles

| Role ID | Role | Where in the lab |
|---|---|---|
| **PD-WRL-007** | Vulnerability Analysis | Finding 1: identifying deviations from acceptable configurations |
| **DD-WRL-001** | Cybersecurity Architecture | Finding 2: least-privilege / access-control design |
| **DD-WRL-003** | Secure Software Development | Finding 3: secrets management and secure coding |
| **PD-WRL-001** | Defensive Cybersecurity | Finding 4: monitoring and logging (with **PD-WRL-003** Incident Response) |
| **IO-WRL-006** | Systems Security Analysis | Finding 5: network exposure and firewall rules |

**NICE Competency Areas:** NF-COM-001 Access Controls · NF-COM-008 DevSecOps

**NICE TKS by finding:**
- S3 / PII — K1182, S0532, T1118
- IAM — K0742, K0685, S0569
- Lambda secrets — K0814, S0172, T1197
- CloudTrail — K1131, S0866, T1350
- Security group — K0878, S0667, T1559
- Analyst judgment — T1348

**Other standards:** CIS AWS Foundations Benchmark v3.0 · OWASP Top 10 (2021) A05 Security Misconfiguration, A01 Broken Access Control · AP CSP Big Idea 4 (Computing Systems & Networks), Big Idea 5 (5.6 Safe Computing) · PLTW Cybersecurity Unit 2, Unit 4.

---

## Pedagogical design

This lab uses **scaffolded discovery learning**. For each service, students get a neutral description and one focused "think before you flag" question — but never the answer or the specific setting to look for. The judgment happens in the inspecting. The **public-by-design trap** teaches the cost of false positives and the analyst skill of knowing when *not* to flag. The handout closes with a Think–Pair–Share, a Claim–Evidence–Reasoning exit ticket, and a self-reflection scale.

---

## Fork it for your classroom

MIT licensed — fork it freely. Common customizations:

- **Change the scenario** — swap "FirstTrust Bank" for a hospital, school, or retailer in the `SERVICES` array in `index.html`
- **Add or remove services** to fit your time block
- **Add your school branding** to the header
- **Translate** the student handout (LaTeX source is included)

If you make improvements, please open a pull request — this is a living resource.

---

## About the Curriculum Patch

The Cloud Bank Heist Lab is one module in a broader framework called the **Curriculum Patch**: a methodology for updating existing CS and cybersecurity curricula to address modern cloud and AI threats without building entire new courses from scratch. Companion module: the **Prompt Injection Lab** ([../](https://github.com/ritasabri/rita-cyber-ed)).

---

## Citation

> Sabri, R. (2026). *Cloud Bank Heist Lab: A Classroom Tool for Teaching Cloud Security Misconfigurations in K–12 Cybersecurity Education.* Rita Cyber Ed. https://github.com/ritasabri/rita-cyber-ed

Part of the Curriculum Patch framework; presented at the **NICE Conference, June 2026, Philadelphia**.

---

## Contact

**Rita Sabri** — CS & Cybersecurity Educator, Cardozo Education Campus (DCPS), Washington D.C.

- 🌐 Lab: [ritasabri.github.io/rita-cyber-ed/cloud-lab/](https://ritasabri.github.io/rita-cyber-ed/cloud-lab/)
- 🐙 GitHub: [@ritasabri](https://github.com/ritasabri)

---

## License & acknowledgments

MIT License — fork, modify, and use freely for educational purposes. With thanks to **NICE** at NIST for the workforce framework, the **Center for Internet Security** for the AWS Foundations Benchmark, and **OWASP** for the security standards that make this alignment possible.
