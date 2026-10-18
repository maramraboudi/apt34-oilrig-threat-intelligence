# 25 Future Outlook

25 Future Outlook
The most likely direction is continued movement toward trusted infrastructure and identity-based
access. OilRig’s use of Exchange and cloud-service-powered tooling shows why future campaigns
may lean on legitimate enterprise platforms instead of easily blocked dedicated servers.
•Area: TTPs
Expectation: Continued blending of phishing, exploitation, valid accounts, scripting and cloud
APIs; fewer obvious malware stages and more legitimate-looking administration.
•Area: Cloud and SaaS
Expectation: Microsoft 365 and similar platforms stay attractive: authentication, storage,
messaging and APIs without an obviously malicious destination.
•Area: Targeting
Expectation: Strategic government and critical-industry organizations; suppliers and trusted
partners as indirect paths to higher-value victims.
•Area: Malware
Expectation: Modular, lightweight tools handing communication and storage to legitimate
services.
•Area: Infrastructure
Expectation: Dedicated servers coexisting with compromised sites, cloud accounts, email
systems and APIs; blocking by IP or domain becomes insufficient.
25.1 Early-warning indicators of a new campaign
Watch for new Microsoft Graph/OneDrive applications, unusual Exchange automation, new cloud
accounts linked to phishing, recurring victim organizations, new downloader families with similar
configuration formats, and repeated use of the same identity or credential-theft workflow.
Academic Year 2026/2027 | 46

--- PAGE 47 ---
CTI REPORTAPT34 / OILRIG
Conclusion
APT34/OilRig is a mature Iranian cyber-espionage capability whose strength comes from persistence
and adaptation, not from reliance on a single malware family. Across campaigns it has combined
socialengineering, exploitation, scripting, credentialtheft, compromisedinfrastructureandlegitimate
enterprise services.
The clearest lesson for defenders is that OilRig cannot be stopped by IOC blocking alone. Organi-
zations need visibility across identity, endpoint, email, DNS, network and cloud layers, with threat
intelligence used to connect those observations into one intrusion story.
Top priorities
1. Phishing-resistant identity protection and credential hygiene
2. Rapid patching of exposed systems
3. Strong endpoint telemetry (PowerShell, scheduled tasks, credential stores)
4. Microsoft 365 and Exchange monitoring
5. Continuous hunting for abnormal use of trusted services
Academic Year 2026/2027 | 47

--- PAGE 48 ---
CTI REPORTAPT34 / OILRIG
References and Intelligence Sources
MITRE ATT&CK
•OilRig (G0049), Version 5.0, last modified 31 July 2026
•Techniques: T1133, T1110, T1049, T1021.004, T1572, T1087.001, T1069.001, T1007, T1105
•SEASHARPEE (S0185), OilRig web shell
Government sources
•CISA, Securing Core Cloud Identity Infrastructure, 15 July 2025
•CISA/FBI, Iranian Government-Sponsored APT Actors Compromise Federal Network, Deploy
Crypto Miner, Credential Harvester, 2022
•CISA/FBI/ACSC/NCSC, Iranian Government-Sponsored APT Actors Exploiting Microsoft Ex-
change and Fortinet Vulnerabilities, 2021
Security vendors
•Mandiant / Google Cloud, Targeted Attacks against Banks in the Middle East, 22 May 2016
(attribution update 8 December 2017)
•Mandiant / Google Cloud, New Targeted Attack in the Middle East by APT34, 7 December
2017
•Mandiant / Google Cloud, Hard Pass: Declining APT34’s Invite to Join Their Professional
Network, 18 July 2019
•Google Cloud, Updated Cyber Threat Actor Naming System, 2026
•Palo Alto Networks Unit 42, OilRig / QUADAGENT research; Iranian-linked cyber operations
threat brief
•ESET Research, OilRig’s Outer Space and Juicy Mix, 21 September 2023
•ESET Research, Iran-linked OilRig attacks Israeli organizations with cloud service-powered
downloaders, 14 December 2023
•ESET Research, Iran-aligned BladedFeline spies on Iraqi and Kurdish officials, 5 June 2025
•ESET, APT Activity Report, October 2025–March 2026, 28 May 2026
Source reliability
•Tier: Tier 1
Sources: MITRE ATT&CK, government advisories
Best used for: Documented techniques, attribution assessments, defensive guidance
•Tier: Tier 2
Sources: Primary security-vendor research
Best used for: Malware, infrastructure, campaign and victim evidence
•Tier: Tier 3
Sources: Reputable secondary and open-source reporting
Best used for: Chronology and context; corroboration preferred
IOC confidence is HIGH when reported directly by a primary source, MEDIUM when independently
correlated, andLOWwhenbasedmainlyonuncorroboratedreporting. Coretechnicalandattribution
claims prioritize MITRE, government and primary vendor research.
Academic Year 2026/2027 | 48

--- PAGE 49 ---
CTI REPORTAPT34 / OILRIG
Appendix A: Acronyms and Terminology
•APT
Meaning: Advanced Persistent Threat
•EWS
Meaning: Exchange Web Services
•C2
Meaning: Command and Control
•DGA
Meaning: Domain Generation Algorithm
•CTI
Meaning: Cyber Threat Intelligence
•OSINT
Meaning: Open-Source Intelligence
•IOC
Meaning: Indicator of Compromise
•MFA
Meaning: Multi-Factor Authentication
•TTP
Meaning: Tactics, Techniques and Procedures
•SaaS
Meaning: Software as a Service
•M365
Meaning: Microsoft 365
•EDR
Meaning: Endpoint Detection and Response
Academic Year 2026/2027 | 49