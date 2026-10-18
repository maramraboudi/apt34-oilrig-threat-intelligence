# Sources and methodology

## Scope and approach

This repository accompanies an academic cyber-threat-intelligence report on APT34/OilRig. The report synthesizes public material on actor naming, attribution, targeting, operations, tooling, ATT&CK mappings, and defensive detection. Its references include MITRE ATT&CK, government advisories, and primary security-vendor research; the report describes its preferred source hierarchy and confidence scale in its references section.

The material is presented as a source-led assessment, not as a new collection of independently observed telemetry. Statements about specific campaigns, victims, malware, or infrastructure should be traced to the cited original reporting. A technique association or similarity is not, by itself, proof of common authorship or attribution.

The report's distinctions are important:

- **Reported behavior** refers to activity described by a cited source.
- **Assessment** is an analytic judgment derived from available reporting, with uncertainty that may vary by claim.
- **Attribution** is strongest when supported by multiple independent lines of evidence; shared tools, geography, or target sectors alone are insufficient.
- **Indicators** are time-sensitive artifacts. The report itself cautions that hashes and exact infrastructure can lose blocking value and should be kept with source, confidence, campaign, and observation dates.

## Source currency

The report's reference list identifies the MITRE ATT&CK OilRig entry as **version 5.0, last modified 31 July 2026**. It also cites sources published as recently as **28 May 2026**. Accordingly, this repository reflects the report's research snapshot, not a live or continuously updated threat feed. The included ATT&CK matrix is explicitly labeled **version 17** in the report and should not be assumed to match the current ATT&CK release.

Check original publications and current ATT&CK pages before relying on a claim, technique mapping, or indicator for a present-day decision. Older reports may retain historical value while their infrastructure indicators or procedural details have changed.

## Selected authoritative references

- [MITRE ATT&CK: OilRig (G0049)](https://attack.mitre.org/groups/G0049/) — group profile and technique references.
- [CISA / FBI: Iranian Government-Sponsored APT Actors Compromise Federal Network, Deploy Crypto Miner, Credential Harvester (2022)](https://www.cisa.gov/news-events/cybersecurity-advisories/aa22-320a) — government advisory cited in the report.
- [CISA / FBI / ACSC / NCSC: Iranian Government-Sponsored APT Actors Exploiting Microsoft Exchange and Fortinet Vulnerabilities (2021)](https://www.cisa.gov/news-events/cybersecurity-advisories/aa21-200a) — government advisory cited in the report.
- ESET Research, “OilRig's Outer Space and Juicy Mix campaigns” (21 September 2023) — campaign research cited in the report.
- ESET Research, “Iran-linked OilRig attacks Israeli organizations with cloud service-powered downloaders” (14 December 2023) — campaign research cited in the report.
- ESET Research, “Iran-aligned BladedFeline spies on Iraqi and Kurdish officials” (5 June 2025) — relevant regional reporting cited in the report; it is not treated here as interchangeable with OilRig attribution.

The original report's reference list contains additional vendor research and campaign sources. Consult the PDF for its full bibliography and attribution context.

## Limitations

Public reporting is incomplete and may use different naming conventions, confidence standards, and visibility windows. Some actor and campaign links remain contested or provisional. The report summarizes a selection of published material; it is not an exhaustive account of Iranian cyber activity, nor a guarantee that every mapped behavior is current. No new IOCs are asserted by this repository.

## Rights and attribution

The report was prepared by **Wejden Cherif and Maram Raboudi**, **TEK-UP**, for the **2026/2027 academic year**. The report PDF and extracted figures are preserved with their academic provenance; the figures are reproduced from the authors' report and are not claimed as original assets of this repository. Referenced research, trademarks, and other third-party material remain subject to their respective rights holders. Public availability here does not grant a license to reuse the report, figures, or cited material.
