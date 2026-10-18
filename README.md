# APT34 / OilRig: Threat Intelligence

An academic, source-led study of APT34 (OilRig), a suspected Iranian cyber-espionage group tracked by MITRE ATT&CK as [G0049](https://attack.mitre.org/groups/G0049/). The repository brings together the original report, its figures, an analytical overview, and notes on sources and methodology.

> **Scope:** Educational and defensive research. This repository is not an IOC feed and does not provide operational instructions.

## Start here

- [Analytical overview](overview.md) — key findings, confidence distinctions, and defender takeaways.
- [Sources and methodology](sources-and-methodology.md) — source tiers, scope, currency, and limitations.
- [Figure index](figures/README.md) — all 12 report figures, with captions and descriptive alt text.
- [Original academic report (PDF)](APT34-OilRig-threat-intelligence-report.pdf)
- [How to cite this work](CITATION.cff)

## At a glance

The report assesses OilRig as a persistent espionage threat whose reported activity has targeted government and strategically important organizations, particularly in the Middle East. Across campaigns, public reporting describes changes in delivery methods, malware, and command-and-control alongside recurring interest in credentials and access to sensitive information. Defenders should therefore combine identity, endpoint, email, network, and cloud telemetry instead of relying on long-lived hashes or infrastructure indicators alone.

Attribution and campaign linkage are assessments, not certainties. Confidence belongs to individual claims and depends on the underlying evidence; a shared tool, victim sector, or regional focus does not by itself establish that activity belongs to OilRig.

## Selected figure

![OilRig intrusion lifecycle from reconnaissance and initial access through execution, persistence, credential access, discovery, command and control, and exfiltration; credential access is highlighted.](figures/figure-01-attack-lifecycle.png)

*Figure 1. Simplified OilRig attack lifecycle, synthesized in the report from public reporting and MITRE ATT&CK mappings. See the [full figure index](figures/README.md) for the remaining figures and context.*

## Defensive use

- Use ATT&CK mappings as a starting point for coverage review, then verify that detections match your environment and the underlying source.
- Prioritize phishing-resistant authentication, careful privileged-account controls, script and PowerShell visibility, credential-access monitoring, and review of scheduled-task or service creation.
- Correlate endpoint and identity events with email, DNS, network, Exchange, and cloud-service audit logs.
- Treat hashes, domains, IP addresses, and filenames as time-bound evidence. Record provenance and observation dates, and validate indicators before blocking.

These are general defensive priorities drawn from the report, not a claim that any one behavior uniquely identifies OilRig.

## Repository contents

```text
.
├── APT34-OilRig-threat-intelligence-report.pdf
├── CITATION.cff
├── README.md
├── figures/
│   ├── README.md
│   └── figure-*.png
├── overview.md
└── sources-and-methodology.md
```

## Attribution and reuse

The report and extracted figures remain attributable to their authors, and cited material remains subject to its respective rights holders. Their presence in this public repository does not grant a reuse license. See the [methodology and rights note](sources-and-methodology.md#rights-and-attribution).
