# ⚙️ Detection-as-Code CI/CD Pipeline

> Automated GitHub Actions pipeline that validates Sigma rules on every commit — syntax check, quality control, MITRE ATT&CK verification, and Splunk SPL conversion.

![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-CI/CD-blue?logo=github-actions)
![Sigma](https://img.shields.io/badge/Sigma-Validated-green)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 🔄 Pipeline Jobs

| Job | Trigger | What it does |
|---|---|---|
| Validate Sigma Rules | Every push | Syntax check all .yml rules |
| Quality Checks | Every push | Verify required fields + MITRE tags |
| Convert to Splunk | Merge to main | Auto-convert rules to SPL |
| Generate Report | Every push | Markdown table of all rules |

## 💡 Why Detection-as-Code?

Traditional SIEM rule management is manual and error-prone. 
This pipeline brings **software engineering practices** to detection:
- Every rule change is reviewed via Pull Request
- Broken rules are caught before reaching production SIEM
- Rules are automatically converted to multiple SIEM formats

## 🔗 Related Projects

- [sigma-siem-rules](https://github.com/arash-123456/sigma-siem-rules) — The detection rules validated by this pipeline
