# 5 Motivation and Strategic Objectives

5 Motivation and Strategic Objectives
OilRig is an intelligence collector, not a criminal money-maker.
APT34/OilRig is best assessed as a strategic cyber-espionage actor rather than a financially mo-
tivated group. Public reporting consistently links its activity to the collection of information that
supports Iranian geopolitical, economic and national-security interests. Mandiant’s 2017 assessment
described a long-term operation focused heavily onreconnaissance. The victim list (governments,
banks, energy and oil-and-gas, chemical, telecom and, later, Israeli healthcare, manufacturing and
local government) matches intelligence requirements, not opportunistic profit.
5.1 Strategic outcomes and operational enablers
•Level: Strategic outcome
Objective: Intelligence on government decision-making, economic activity, energy and other
strategic sectors
What it looks like in practice: Mailboxes, documents, screenshots and system information
collected from high-value victims
•Level: Strategic outcome
Objective: Use of trusted relationships and supply-chain paths to reach higher-value targets
What it looks like in practice: Compromised websites and professional/social lures
•Level: Operational enabler
Objective: Credentials and reusable access
What it looks like in practice: Browser theft, Credential Manager theft, keylogging, valid
accounts
•Level: Operational enabler
Objective: Long-term persistence
What it looks like in practice: Malware, scheduled tasks, services, web shells, cloud accounts
•Level: Operational enabler
Objective: Internal reconnaissance
What it looks like in practice: Hosts, accounts, services, processes, network connections
•Level: Operational enabler
Objective: Reliable C2 paths
What it looks like in practice: HTTP/DNS, Exchange, Microsoft Graph, OneDrive
5.2 Four operational characteristics
•Persistence and adaptability.OilRig mixes conventional intrusion methods with custom
tooling. It has used spearphishing and malicious documents, exploited newly disclosed vulnera-
bilities (Mandiant documented CVE-2017-0199 and CVE-2017-11882 in 2017) and relied heavily
on PowerShell and other scripting.
•Blending with trusted infrastructure.Early operations used attacker-controlled
HTTP/DNS servers and compromised websites; later activity moved into Microsoft Ex-
change, email and Microsoft Graph/OneDrive. Malicious traffic can therefore resemble ordinary
enterprise communication, which weakens simple IP and domain blocking.
•Credential-centric persistence.Browser credential theft, Windows Credential Manager ac-
cess, keylogging and valid accounts turn one infected endpoint into identity-based access that
can survive malware removal.
Academic Year 2026/2027 | 14

--- PAGE 15 ---
CTI REPORTAPT34 / OILRIG
•Human-focused social engineering.The 2019 HardPass campaign used LinkedIn and re-
cruitment themes to build trust with targets in energy, government and oil and gas, bypassing
defenses that only watch email.