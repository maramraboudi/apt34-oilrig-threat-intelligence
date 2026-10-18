# 8 Attack Lifecycle and Intrusion Analysis

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
Academic Year 2026/2027 | 18

--- PAGE 19 ---
CTI REPORTAPT34 / OILRIG
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