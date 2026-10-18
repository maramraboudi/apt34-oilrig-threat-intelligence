# Introduction and executive summary

### Report page 7

Introduction
Modern governments and critical sectors depend on digital systems, and that dependence has opened
the door to Advanced Persistent Threats (APTs): patient, well-resourced operators that target spe-
cific organizations over long periods. Unlike opportunistic cybercrime, an APT is usually driven by
strategic goals such as espionage, intelligence collection or political influence.
APT34, also known asOilRig, is a textbook case of state-aligned cyber activity. It has been
publicly associated with Iranian interests and has targeted government bodies, banks, energy firms,
telecom providers, chemical companies and healthcare organizations, mostly in the Middle East.
This report studies APT34/OilRig from a Cyber Threat Intelligence (CTI) point of view. Listing
malware samples and Indicators of Compromise (IOCs) is not enough; the report therefore works at
three levels:
•Strategic:who the actor is, what it wants, and whom it targets.
•Operational:its campaigns, infrastructure, malware and attack chains.
•Tactical:the techniques, ATT&CK mappings and indicators that defenders can turn into de-
tections.
The analysis relies on public intelligence from MITRE ATT&CK, Mandiant / Google Cloud, ESET,
Cisco Talos, Palo Alto Networks Unit 42 and CISA. Sources are cross-checked so that established
facts are kept apart from assessments and hypotheses, and the report is explicit about the difficulty
of attribution and about the different names vendors give to the same activity.

### Report page 8

1 Executive Summary
1.1 Key intelligence findings
APT34 (OilRig)is a suspected Iranian threat group tracked by MITRE ATT&CK asG0049.
Public reporting traces its activity back to at least 2014. Its victims are mostly in theMiddle East,
with recurring interest ingovernment, finance, energy, chemicalandtelecommunications
organizations.
The strongest assessment is that OilRig conductscyber-espionage in support of Iranian strate-
gic interests. Its campaigns combine spearphishing, exploitation of public vulnerabilities, Power-
Shell and script-based execution, credential theft, scheduled-task persistence, compromised infras-
tructure, DNS/HTTP communication and, more recently, abuse oflegitimate cloud services.
The one thing to remember
OilRig changes its malware faster than it changes its mission . Tools, domains and C2 channels
are replaced as soon as defenders catch up, while the goal stays the same: get in, stay in, steal
credentials, collect information and exfiltrate it.
Figure 1:Simplified OilRig attack lifecycle, synthesized from public reporting and MITRE ATT&CK mappings.
Red = the stage OilRig invests in most: credentials turn one infected host into reusable identity access.
1.2 Threat assessment
The threat is assessed assustained rather than campaign-specific. The group has a long
operational history, repeatedly targets strategically important sectors, keeps developing malware, and
increasingly hides inside services that enterprises already trust:Microsoft Exchange,Microsoft
GraphandOneDrive.
1.3 Key takeaways for defenders
•Monitorbehavior and context, not static IOCs alone: infrastructure and hashes age quickly.
•Prioritizephishing-resistant authentication, PowerShell and script monitoring, and
credential-theft detection.
•Watch for suspiciousscheduled-task and service creationand anomalous Exchange / Mi-
crosoft Graph activity.
•Correlateendpoint, identity, DNS, email, network and cloud telemetry rather than running
them as separate silos.

![Figure 01: OilRig attack lifecycle, with credential access highlighted.](../figures/figure-01-attack-lifecycle.png)
