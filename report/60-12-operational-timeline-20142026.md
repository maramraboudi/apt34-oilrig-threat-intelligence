# 12 Operational Timeline 2014–2026

12 Operational Timeline 2014–2026
Four eras, one mission: strategic intelligence and durable access.
Figure 6:Selected milestones in the public history of APT34 / OilRig. Red markers are the 2017 exploit wave
and the 2023 Exchange-based backdoor.
12.1 Milestone table
•Period: 2014
Milestone: Earliest activity
Intelligence significance: MITRE and Mandiant assess OilRig /APT34 activity from at
least 2014
•Period: 2016
Milestone: Middle Eastern banks
Intelligence significance: Mandiant later attributed a macro-enabled Office spearphishing
campaign to APT34
•Period: 2017
Milestone: POWRUNER / BONDUPDATER
Intelligence significance: Exploitation of CVE-2017-0199 and CVE-2017-11882; PowerShell
and DGA-based C2
•Period: 2018–2019
Milestone: DNSpionage / Karkoff
Intelligence significance: DNS and HTTP communication; Karkoff documented by Cisco
Talos in 2019
•Period: 2019
Milestone: HardPass
Intelligence significance: LinkedIn and recruitment-themed social engineering against strate-
gic sectors
•Period: 2021
Milestone: Outer Space
Intelligence significance: Israeli targeting using Solar and compromised infrastructure
•Period: 2022
Milestone: Juicy Mix
Intelligence significance: Mango and renewed compromise of Israeli organizations
•Period: 2022–2023
Milestone: Cloud-service C2
Academic Year 2026/2027 | 22

--- PAGE 23 ---
CTI REPORTAPT34 / OILRIG
Intelligence significance: SC5k, ODAgent , OilCheck and OilBooster use Microsoft cloud
APIs
•Period: 2023
Milestone: PowerExchange
Intelligence significance: Exchange/email-based C2 against a UAE government organization
•Period: 2024–2025
Milestone: Evolving ecosystem
Intelligence significance: Further exploitation; research into related and subgroup activity (
BladedFeline )
•Period: 2026
Milestone: Current picture
Intelligence significance: MITRE G0049 updated; naming and subgroup relationships keep
evolving
12.2 The four eras
Era 1: Emergence and scripts 2014–2017
WHAT HAPPENED: Activity assessed from at least 2014. By 2016 the group sent macro-enabled
Excel attachments to Middle Eastern banks. In 2017 it expanded PowerShell use and quickly exploited newly
disclosed Office vulnerabilities, using malicious documents and custom PowerShell backdoors (Mandiant, 7
December 2017).
SIGNATURE: Office documents + PowerShell + attacker-owned HTTP/DNS infrastructure.
Era 2: DNS and social engineering 2018–2019
WHAT HAPPENED: DNSpionage hit organizations in Lebanon and the UAE with malicious Office
documents, fake job websites and HTTP/DNS C2. In 2019 Cisco Talos identified Karkoff, a lightweight .NET
backdoor, and linked it to DNSpionage with high confidence through infrastructure overlaps. HardPass
followed, using LinkedIn and recruitment themes (including impersonation of a Cambridge University contact).
SIGNATURE: DNS abuse, fake job lures, trust-based social engineering.
Era 3: Compromised sites and Israeli focus 2020–2022
WHAT HAPPENED: OilRig kept changing tooling and infrastructure instead of relying on one malware
family, moving toward quieter access and compromised infrastructure. In 2021 Outer Space introduced the
Solar backdoor and used a compromised Israeli website as C2; in 2022 Juicy Mix introduced Mango, a successor
to Solar.
SIGNATURE: Compromised legitimate websites for C2; VBS droppers, PowerShell, scheduled tasks and
credential stealers.
Era 4: Exchange and cloud services 2022–2026
WHAT HAPPENED: ESET documented SC5k, ODAgent , OilCheck and OilBooster abusing Microsoft
Graph, OneDrive, Outlook and Exchange Web Services. In May 2023 ESET reported PowerExchange , a
PowerShell backdoor using Exchange email, in a UAE government organization. MITRE updated G0049 in
July 2026, and ESET’s reporting also covers BladedFeline , Lyceum and exploitation of CVE-2024-30088.
SIGNATURE: Legitimate enterprise and cloud platforms as C2 and exfiltration channels.
Reading the timeline
Academic Year 2026/2027 | 23

--- PAGE 24 ---
CTI REPORTAPT34 / OILRIG
Across 12 years the mission is stable and only the tradecraft moves: Office documents and
scripts→compromised websites and credential theft→Exchange-based C2→legitimate cloud
services. The steady aim is to reduce detection while preserving the same collection workflow.