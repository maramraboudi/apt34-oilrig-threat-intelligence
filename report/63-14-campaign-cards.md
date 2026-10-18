# 14 Campaign Cards

14 Campaign Cards
Across campaigns the malware changes faster than the mission.
OilRig’s campaigns show a steady shift from conventional spearphishing and custom scripts toward
more selective social engineering, compromised infrastructure and legitimate cloud services. Each
card below summarizes one campaign: when it happened, whom it hit, how access was gained, which
tools were used, how C2 worked, and why it matters to an analyst.
14.1 Middle Eastern banking operations
Middle Eastern Banking Operations May 2016
TARGETS: Employees of Middle Eastern banks
INITIAL ACCESS: Macro-enabled Excel attachments sent by spearphishing
ACTIVITY: Reconnaissance, malicious documents, script execution and malware delivery; Mandiant later
attributed the activity to APT34 (22 May 2016 report; attribution update 8 December 2017)
WHY IT MATTERS: Earliest well-documented OilRig operation; financial targeting fits intelligence
collection, not necessarily financial gain
14.2 POWRUNER: BONDUPDATER
POWRUNER: BONDUPDATER 2017
INITIAL ACCESS: Exploitation of CVE-2017-0199 and CVE-2017-11882 via RTF documents
ATTACK CHAIN: RTF→mshta→PowerShell / VBScript→CertUtil→scheduled tasks
TOOLING: POWRUNER (PowerShell backdoor), BONDUPDATER (downloader with a custom DGA)
C2: DGA-based HTTP/DNS; infrastructure such as proxychecker [.]pro and mumbai -m[.]site
WHY IT MATTERS: Shows how quickly OilRig adopts newly disclosed vulnerabilities
14.3 DNSpionage: Karkoff
DNSpionage: Karkoff 2018–2019
TARGETS: Organizations in Lebanon and the UAE
INITIAL ACCESS: Malicious Office documents; fake job websites
TOOLING: A remote-administration tool using HTTP and DNS; by April 2019 Cisco Talos identified
Karkoff, a lightweight .NET backdoor installable as a Windows service
WHY IT MATTERS: Demonstrates DNS as a covert channel; Talos observed changes in reconnaissance
and infection procedures, and linked Karkoff to DNSpionage with high confidence
14.4 HardPass
HardPass 2019
TARGETS: Energy and utilities, government, oil and gas
Academic Year 2026/2027 | 25

--- PAGE 26 ---
CTI REPORTAPT34 / OILRIG
INITIAL ACCESS: LinkedIn and recruitment-themed conversations (including impersonation of a Cam-
bridge University contact) to build trust before delivering malicious files
TOOLING: New malware families and credential-stealing capabilities
WHY IT MATTERS: Social context became part of the attack surface; the approach bypasses defenses
focused only on email
14.5 Outer Space
Outer Space 2021
TARGETS: Israeli organizations
TOOLING: Solar backdoor; post-compromise tools collecting browser and Windows credential data
C2: A legitimate Israeli human-resources website, compromised and reused as C2
WHY IT MATTERS: First clear example of the compromised-site C2 model; reported by ESET (21
September 2023)
14.6 Juicy Mix
Juicy Mix (MITRE C0044) 2022
TARGETS: Israeli organizations, again
TOOLING: Mango replaces Solar; VBS droppers, PowerShell, scheduled tasks, credential stealers
C2: Compromised Israeli infrastructure
WHY IT MATTERS: Incremental development: the Outer Space playbook reused with a new backdoor
14.7 Cloud-service-powered downloaders
Cloud-Service-Powered Downloaders 2022–2023
TARGETS: Israeli targets that OilRig had to keep access to
TOOLING: SC5k, ODAgent , OilCheck , OilBooster
C2 / EXFIL: Microsoft Graph, OneDrive, Outlook and Exchange Web Services
WHY IT MATTERS: Legitimate cloud services made traditional IP-based blocking much less useful;
ESET published this research on 14 December 2023
14.8 PowerExchange
PowerExchange 2023
TARGETS: A UAE government organization (ESET, May 2023)
TOOLING: PowerExchange , a PowerShell backdoor
C2: Microsoft Exchange and email messages carry commands and stolen data
WHY IT MATTERS: C2 hidden inside normal enterprise messaging workflows
Academic Year 2026/2027 | 26

--- PAGE 27 ---
CTI REPORTAPT34 / OILRIG
14.9 Israeli operations as a pattern
Recurring Israeli Operations 2021 onward
TARGETS: Government, healthcare, manufacturing, local government and other strategic entities
PATTERN: OilRigrepeatedlyreturnedtothesamevictims, deployingnewerdownloadersagainstpreviously
compromised organizations
WHY IT MATTERS: Keeping access to specific victims mattered more than running isolated one-time
campaigns
14.10 Recent and related activity
Recent Activity and Related Clusters 2024–2026
ACTIVITY: MITRE’s current G0049 record includes exploitation of CVE-2024-30088; ESET reported
BladedFeline in 2025 and assessed likely ties to OilRig
CAUTION: Treat these relationships as assessed, not as automatic identity