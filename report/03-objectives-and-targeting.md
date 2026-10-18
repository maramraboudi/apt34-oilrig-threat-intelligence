# Chapter II - Objectives and targeting

### Report page 14

CHAPTER II Main Objective and Motivation
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

### Report page 15

•Human-focused social engineering.The 2019 HardPass campaign used LinkedIn and re-
cruitment themes to build trust with targets in energy, government and oil and gas, bypassing
defenses that only watch email.
6 Geopolitical Context and Intelligence Requirements
6.1 Regional context
OilRig operates in a region shaped by political tension, economic pressure and competition for
influence. Its strongest focus remains the Middle East, where government and strategically important
organizations hold information useful to Iranian interests. This explains the value of energy, finance
and telecom targets. It supports the espionage assessment, but geopolitical relevance alone does not
prove who directed a given intrusion.
6.2 OilRig inside Iran’s cyber ecosystem
Iran’s cyber operations involve several groups with different missions, capabilities and suspected
institutional links. OilRig is one established espionage cluster, not a label for all Iranian activity.
ESET has reported links between OilRig-related activity and other Iran-aligned groups such as
Lyceum and MuddyWater; these remain assessed relationships. MITRE and Mandiant both assess
thatOilRigsupportsIraniangovernmentinterests: itsroleistogainandkeepaccess, stealcredentials,
move through networks and collect information.
6.3 Likely intelligence requirements
•Requirement: Government and diplomatic information
Why OilRig’s targeting suggests it: Policies, negotiations, officials and regional relation-
ships
•Requirement: Economic intelligence
Why OilRig’s targeting suggests it: Financial institutions, commercial activity, economic
relationships
•Requirement: Energy and industrial information
Why OilRig’s targeting suggests it: Oil and gas, chemicals, manufacturing and supply
chains
•Requirement: Communications and identity data
Why OilRig’s targeting suggests it: Email, credentials, contacts and access to key
personnel
•Requirement: Regional security information
Why OilRig’s targeting suggests it: Developments relevant to Iran’s political and security
interests
•Requirement: Persistent access
Why OilRig’s targeting suggests it: Credentials and trusted relationships that give
continued access
6.4 Evolution of objectives
Themainobjectiveappearsstable: collectintelligencethatsupportsIranianstrategicinterests. What
changed is how. The group moved from malicious Office documents and PowerShell toward social-
engineering lures, compromised infrastructure, Exchange-based C2 and legitimate cloud services, a
clear effort to be harder to detect while keeping the same mission.

### Report page 16

7 Targeting and Victimology
Targets are chosen for the information and access they offer.
7.1 Geography
OilRig has a strong Middle Eastern focus with selected international victims; MITRE describes ac-
tivity against Middle Eastern and international organizations since at least 2014. Israel became a
recurring focus from 2021, and reporting also names victims in Lebanon, the UAE and, via Bladed-
Feline, Iraq and the Kurdish region.
7.2 Sector by sector
•Sector: Government
Why it is valuable: Policy, diplomacy, regional security, decision makers
Documented evidence: National and local government entities; BladedFeline against Iraqi
and Kurdish officials (ESET, 2025)
•Sector: Energy, oil & gas
Why it is valuable: Infrastructure, production, investment, supply chains, policy
Documented evidence: Mandiant identified energy as one of APT34’s strongest areas of
interest
•Sector: Finance
Why it is valuable: Economic and institutional intelligence
Documented evidence: Middle Eastern banks attacked as early as 2016 with malicious Excel
files
•Sector: Telecom
Why it is valuable: Connects people, systems and other organizations; exposes communica-
tions data and access paths
Documented evidence: Recurring in MITRE and Mandiant reporting
•Sector: Chemical
Why it is valuable: Industrial knowledge, manufacturing capability, links to energy and
economy
Documented evidence: Appears repeatedly in OilRig reporting
•Sector: Healthcare
Why it is valuable: Sensitive data; later expansion of the victim set
Documented evidence: Israeli healthcare organization (ESET)
•Sector: Manufacturing
Why it is valuable: Industrial and supply-chain value
Documented evidence: Israeli manufacturing company (ESET)
7.3 Target-selection patterns
OilRig generally chooses organizations with strategic or information value: access to decision makers,
sensitive data, credentials, communications and trusted relationships. A less prominent organization
can also be chosen as a stepping stone (supply-chain access) toward a higher-value target. The
victimology is consistent with an intelligence-led operation, not indiscriminate compromise.
Intelligence gap
The public record is incomplete. Vendors report only what they discover and investigate, so
the absence of public reporting on a sector or country is an intelligence gap , not proof that

### Report page 17

OilRig does not target it.
Overall targeting assessment
Targeting is strategic and information-driven, with a persistent Middle Eastern focus and re-
curring interest in government, finance, energy, chemical and telecom. Later reporting adds
healthcare, manufacturing and local government. Access to people, credentials, communica-
tions and strategic organizations is itself a primary objective.
