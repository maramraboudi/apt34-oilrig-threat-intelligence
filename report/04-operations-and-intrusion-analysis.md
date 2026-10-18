# Chapter III - Operations and intrusion analysis

### Report page 18

CHAPTER III Known Operations
8 Attack Lifecycle and Intrusion Analysis
Not every campaign uses every stage, but the pattern is remarkably consistent.
A typical intrusion can be read as one chain:reconnaissance→phishing or exploitation→
script-basedexecution→persistence→credentialtheft→discovery→lateralmovement
→collection→C2 over cloud, web, DNS or Exchange→exfiltration.
Figure 4:End-to-end OilRig attack chain; red marks the credential stage.
•Stage: Reconnaissance
Observed OilRig behavior: Identifies accounts, domain groups, network connections,
services, software and configuration; uses fake VPN portals, conference registrations and job
sites to gather information
MITRE ATT&CK: T1583.001, T1087, T1046, T1016, T1049, T1518
•Stage: Initial access
Observed OilRig behavior: Malicious Office documents, malicious links, compromised
email accounts, exploitation of public vulnerabilities; VPN, Citrix and OWA for access
MITRE ATT&CK: T1566.001, T1204, T1203, T1133, T1586.002
•Stage: Execution
Observed OilRig behavior: PowerShell, Windows Command Shell, VBScript, WMI and
Office macros: flexible execution without one fixed malware family
MITRE ATT&CK: T1059.001/.003/.005, T1047
•Stage: Persistence
Observed OilRig behavior: Scheduled tasks, Windows services, registry mechanisms,
Outlook Home Page abuse, remote-access accounts, web shells
MITRE ATT&CK: T1053.005, T1543.003, T1137.004, T1505.003, T1133
•Stage: Privilege escalation
Observed OilRig behavior: Credentials first, then local escalation; CVE-2024-30088 ex-
ploited for SYSTEM-level execution
MITRE ATT&CK: T1068, T1078
•Stage: Defense evasion
Observed OilRig behavior: Encoded or obfuscated files, masquerading, file deletion,
legitimate cloud services, compromised sites; malware tested against security products
MITRE ATT&CK: T1027, T1036, T1070.004, T1102, T1218.001
•Stage: Credential access
Observed OilRig behavior: Browser stealers, Credential Manager theft, LaZagne ,
Mimikatz , keyloggers
MITRE ATT&CK: T1555.003/.004, T1003, T1056.001, T1110

![Figure 04: End-to-end OilRig attack chain, highlighting credential access.](../figures/figure-04-intrusion-chain.png)

### Report page 19

•Stage: Discovery
Observed OilRig behavior: Users and groups, password policy, processes, services, network
configuration, connections, installed software
MITRE ATT&CK: T1087, T1069, T1201, T1057, T1007, T1016, T1049, T1033, T1518
•Stage: Lateral movement
Observed OilRig behavior: Valid accounts, RDP, SSH/PuTTY, tunneling tools such as
Plink or ngrok
MITRE ATT&CK: T1078, T1021.001/.004, T1572, T1219
•Stage: Collection
Observed OilRig behavior: Credentials, browser data, clipboard, screenshots, files, system
information
MITRE ATT&CK: T1119, T1115, T1113, T1217, T1555
•Stage: Command & control
Observed OilRig behavior: HTTP and DNS first; later compromised servers, Exchange,
Microsoft Graph, OneDrive; DNS as fallback
MITRE ATT&CK: T1071.001/.004, T1102, T1572, T1008, T1573.002
•Stage: Exfiltration
Observed OilRig behavior: Blended into existing channels: Exchange, FTP, cloud storage,
sometimes separate from the main C2 path
MITRE ATT&CK: T1048.003
8.1 Impact assessment
OilRig is an espionage actor, so destruction is not the normal end state. The main business risk is
loss ofcredentials, confidential information and strategic intelligence, followed by persistent
unauthorized access. In sensitive sectors that access can also reveal operations, relationships and
future targets.
9 Initial Access and Social Engineering
Technical exploitation and human trust are combined; the lure is adapted to the victim’s role and
sector.
•Method: Spearphishing attachments
How OilRig uses it: Office and RTF documents with macros, exploits or embedded content.
The attachment is usually a delivery mechanism for scripts, exploits or a downloader, not the
final payload.
•Method: Spearphishing links
How OilRig uses it: Redirect victims to credential-harvesting pages or malware delivery
infrastructure; useful to avoid attachment scanning.
•Method: Public vulnerabilities
How OilRig uses it: Faster path to execution when vulnerable software is exposed (CVE-
2017-0199, CVE-2017-11882, later CVE-2024-30088). Needs accurate victim and software intel-
ligence.
•Method: Recruitment and professional lures
How OilRig uses it: HardPass : attackers posed as recruiters on LinkedIn to establish trust
before sending malicious content, making social context part of the attack surface.
•Method: Credential-based access
How OilRig uses it: Stolen or purchased credentials give direct access to email, VPN,

### Report page 20

remote desktop or cloud services, bypassing controls built only for malware delivery.
•Method: Trusted relationships
How OilRig uses it: Interest in trusted websites, email infrastructure and professional
relationships; even without a proven supply-chain compromise, abusing trusted infrastructure
creates a similar detection challenge.
Evolution
The trend is from attachment-heavy intrusion to a mixed model : exploitation, credential use,
social engineering and abuse of trusted services. The human layer remains important, while the
technical layer has become more flexible.
10 Credential Access and Identity Operations
Malware can be removed; a stolen password, session or cloud identity keeps working.
Credentials are among OilRig’s most valuable forms of access. The aim is rarely collection for its
own sake: it is theconversion of credentials into further access.
•Technique: Credential harvesting
Why it matters: Phishing pages, browser extraction, dumping tools and targeted collection
turn endpoint access into reusable identities.
•Technique: Browser credential theft
Why it matters: Tools extract saved passwords and authentication material; browsers are
attractive because users reuse credentials across business services.
•Technique: Windows Credential Manager
Why it matters: Stores credentials for remote services and applications; targeted during
post-compromise collection (for example by VALUEVAULT).
•Technique: Keylogging
Why it matters: Captures passwords that are not stored locally and reveals operational
conversations and user behavior.
•Technique: Valid accounts
Why it matters: The actor authenticates through normal enterprise pathways , reducing the
malware needed and the noise produced.
•Technique: Credential reuse
Why it matters: Allows movement between systems and access to higher-value accounts;
password reuse is a strategic risk, not only a user-level weakness.
•Technique: Identity-based persistence
Whyitmatters: Accesstiedtoanaccount, tokenorremote-servicecredentialsurvivesmalware
removal, so monitoring authentication behavior is as important as endpoint cleanup.
11 Infrastructure and Command-and-Control
The important shift is not where the server sits, but how well the traffic imitates normal business
activity.

### Report page 21

Figure 5:Evolution of OilRig command-and-control approaches, from attacker-owned servers to legitimate cloud
APIs. Trend: the malicious traffic increasingly looks like normal business traffic.
11.1 Traditional infrastructure
Domains.Attacker-registered domains, dynamic subdomains and domains tied to malicious down-
loaders; rotation keeps access alive when infrastructure is exposed.
IP addresses.Dedicated C2 hosts and infrastructure connected to compromised services. IP
indicators help retrospective hunting but age quickly.
DNS.DNS served both for discovery and as a covert or fallback channel. DNSpionage and related
tools showed its value; BONDUPDATER used a domain-generation algorithm (DGA) so that fixed
blocking becomes unreliable.
11.2 Compromised infrastructure and web servers
Compromised websites let OilRig’s traffic appear to come from a legitimate organization. The Outer
Space and Juicy Mix campaigns used compromised Israeli websites for C2, reducing dependence on
obviously malicious servers. Web shells and compromised web servers provided both a foothold and
a communication layer inside ordinary HTTP requests.
11.3 Exchange and cloud-based C2
•Exchange C2:PowerExchange used Microsoft Exchange email as the command channel; com-
mands and results move through a system defenders expect to be active.
•CloudC2:SC5k, ODAgent, OilCheckandOilBoosterusedMicrosoftGraph, OneDrive, Outlook
and Exchange Web Services for command retrieval, payload delivery and data transfer. The
visible destination belongs to a trusted provider, which makes infrastructure attribution and
blocking much harder.
11.4 Reuse, rotation and operational security
Infrastructure reuse often appears at the operational level (similar C2 patterns, hosting choices,
malware behavior and victim targeting) rather than as one reused IP. OilRig can change domains,
servers, compromised websites and cloud accounts while keeping the same workflow, which is why
defenders should favor behavioral and identity-based detection.

![Figure 05: Evolution of reported OilRig command-and-control approaches.](../figures/figure-05-command-and-control-evolution.png)
