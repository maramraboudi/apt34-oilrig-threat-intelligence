# Report figures

These 12 images are the analytical figures extracted from the original [APT34/OilRig report](../APT34-OilRig-threat-intelligence-report.pdf). The small institutional logo on the report cover is not included. Page numbers below refer to the report's printed page numbers.

Each figure retains its report caption and has descriptive alt text. Captions and interpretations follow the report; the visuals are not independent evidence of attribution.

## Figure 1 — Simplified OilRig attack lifecycle

![Eight-stage lifecycle from reconnaissance and initial access through execution, persistence, credential access, discovery and lateral movement, command and control, and exfiltration; credential access is highlighted.](figure-01-attack-lifecycle.png)

*Report p. 8. The report synthesizes the lifecycle from public reporting and ATT&CK mappings; red highlights credential access as a high-value stage.*

## Figure 2 — Naming landscape around G0049

![Diagram of threat-actor names associated with MITRE ATT&CK group G0049, illustrating reported or assessed overlap among naming clusters.](figure-02-naming-landscape.png)

*Report p. 9. The report cautions that naming relationships represent reported or assessed overlap, not automatic equivalence.*

## Figure 3 — Confidence levels for reported and assessed relationships

![Confidence comparison for relationships discussed in the report, distinguishing stronger and weaker analytic links.](figure-03-attribution-confidence.png)

*Report p. 12. Confidence levels reflect the report's cited assessments; they are not independent measurements.*

## Figure 4 — End-to-end OilRig attack chain

![Intrusion-chain diagram connecting initial access, execution, persistence, credential access, discovery, command and control, and follow-on activity; credential access is highlighted.](figure-04-intrusion-chain.png)

*Report p. 18. Red marks the credential stage in the reported attack chain.*

## Figure 5 — Evolution of OilRig command-and-control approaches

![Timeline-style comparison of reported command-and-control approaches, from attacker-controlled servers and compromised infrastructure toward the use of legitimate services.](figure-05-command-and-control-evolution.png)

*Report p. 21. The report describes a shift toward legitimate cloud services; this does not make such traffic malicious by itself.*

## Figure 6 — Selected milestones in the public history of APT34/OilRig

![Timeline of selected public reporting milestones associated with APT34/OilRig, including a highlighted 2017 exploit wave.](figure-06-operational-timeline.png)

*Report p. 22. A selected chronology of public reporting, not a complete operational history.*

## Figure 7 — Analytical evolution of OilRig tooling

![Progression of tool families described in public reporting on OilRig, presented as an analytical overview rather than a claim that every tool replaced its predecessor.](figure-07-tooling-evolution.png)

*Report p. 29. The report explicitly describes this as a progression of tool families, not a direct replacement sequence.*

## Figure 8 — MITRE ATT&CK Enterprise Matrix, version 17

![MITRE ATT&CK Enterprise technique matrix reproduced in the report, marked version 17.](figure-08-attack-matrix.png)

*Report p. 33. This is a historical versioned matrix; consult MITRE ATT&CK for current content.*

## Figure 9 — Representative ATT&CK techniques used by OilRig

![Representative ATT&CK techniques grouped by tactic, with credential-access techniques highlighted.](figure-09-representative-techniques.png)

*Report p. 33. Technique associations reflect the report's source review and should be checked against current ATT&CK pages.*

## Figure 10 — Components used in OilRig's Juicy Mix campaign

![Schematic overview of components and relationships described in public reporting on OilRig's Juicy Mix campaign.](figure-10-juicy-mix-components.png)

*Report p. 35. Campaign depiction follows the cited research summarized in the report.*

## Figure 11 — String obfuscation function used by Mango's VBS dropper

![Code-oriented illustration of a string-obfuscation function associated in the cited research with Mango's Visual Basic Script dropper.](figure-11-mango-vbs-obfuscation.png)

*Report p. 36. Included as a figure from the report for analytical context; this repository does not provide operational deployment instructions.*

## Figure 12 — OilRig's Outer Space compromise chain

![Campaign-chain diagram linking a malicious email, a VBS dropper, the Solar backdoor, a SC5k downloader, and communication with legitimate Microsoft Exchange services.](figure-12-outer-space-compromise-chain.png)

*Report p. 39. The chain summarizes the Outer Space campaign as presented in the report's cited research.*
