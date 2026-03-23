---
layout: default
title: Detection-as-Code CI/CD Pipeline
description: Automated pipeline that validates, checks quality, and converts Sigma detection rules on every commit.
---

# 🛡️ Detection-as-Code CI/CD Pipeline

[![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-CI%2FCD-blue?logo=github-actions)](https://github.com/Mohammd-Amjadi-pentest2/detection-as-code-pipeline/actions)
[![License: MIT](https://img.shields.io/badge/License-MIT-green)](https://github.com/Mohammd-Amjadi-pentest2/detection-as-code-pipeline/blob/main/SECURITY.md)
[![Sigma](https://img.shields.io/badge/Sigma-Rules-orange)](https://github.com/SigmaHQ/sigma)

> Automated GitHub Actions pipeline that validates Sigma rules on every commit — syntax check, quality control, MITRE ATT&CK verification, and Splunk SPL conversion.

---

## 📋 Pipeline Jobs

| Job | Trigger | What it does |
|-----|---------|-------------|
| ✅ Validate Sigma Rules | Every push | Syntax check all .yml rules |
| 🔍 Rule Quality Checks | Every push | Verify required fields + MITRE tags |
| 🔄 Convert to Splunk SPL | Merge to main | Auto-convert rules to SPL |
| 📊 Generate Report | Every push | Markdown table of all rules |

---

## 🗂️ Detection Rules

### Windows Rules

| Rule | Level | MITRE ATT&CK |
|------|-------|--------------|
| [Suspicious PowerShell Encoded Command](rules/windows/suspicious_powershell.yml) | 🔴 HIGH | T1059.001, T1027 |
| [Windows Brute Force Login Attempt](rules/windows/brute_force_login.yml) | 🟡 MEDIUM | T1110, T1110.001 |

### Linux Rules

| Rule | Level | MITRE ATT&CK |
|------|-------|--------------|
| [Linux Sudo Privilege Escalation](rules/linux/privilege_escalation.yml) | 🔴 HIGH | T1548, T1548.003 |

---

## 🚀 How It Works

1. **Push** a Sigma rule to `rules/**/*.yml`
2. **CI Pipeline** automatically runs 4 validation jobs
3. **Quality Check** ensures all required fields and MITRE tags exist
4. **Splunk Conversion** generates `.spl` files for direct use
5. **Report** is generated as a downloadable artifact

---

## 📁 Repository Structure

```
detection-as-code-pipeline/
├── .github/
│   └── workflows/
│       └── detection-pipeline.yml   # CI/CD pipeline
├── rules/
│   ├── windows/
│   │   ├── suspicious_powershell.yml
│   │   └── brute_force_login.yml
│   └── linux/
│       └── privilege_escalation.yml
├── index.md                          # This page
├── README.md
└── SECURITY.md
```

---

## 🔗 Links

- 📦 [GitHub Repository](https://github.com/Mohammd-Amjadi-pentest2/detection-as-code-pipeline)
- ⚙️ [Actions & Pipeline Runs](https://github.com/Mohammd-Amjadi-pentest2/detection-as-code-pipeline/actions)
- 🔒 [Security Policy](https://github.com/Mohammd-Amjadi-pentest2/detection-as-code-pipeline/blob/main/SECURITY.md)

---

*Built by [Mohammd-Amjadi-pentest2](https://github.com/Mohammd-Amjadi-pentest2) · Powered by [Sigma](https://github.com/SigmaHQ/sigma) & GitHub Actions*
