# 1 Executive Summary

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
Academic Year 2026/2027 | 8

--- PAGE 9 ---
CTI REPORTAPT34 / OILRIG