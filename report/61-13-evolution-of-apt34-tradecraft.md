# 13 Evolution of APT34 Tradecraft

13 Evolution of APT34 Tradecraft
OilRig’s evolution is less about becoming dramatically more sophisticated than about becoming harder
to tell apart from normal enterprise activity.
•Area: Initial access
Earlier: Spearphishing and malicious Office documents
Later: Exploitation, recruitment lures, stolen credentials, abuse of trusted infrastructure
•Area: Malware
Earlier: Script-heavy implants (Helminth, POWRUNER)
Later: Purpose-built .NET backdoors (Solar, Mango), then lightweight cloud-service down-
loaders
•Area: Persistence
Earlier: Scheduled tasks and registry mechanisms
Later: Remote services, web shells, compromised websites and identity-based access
•Area: Credential theft
Earlier: Traditional dumping and keylogging
Later: Specialized theft of browser cookies/history, browser passwords and Credential Manager
data
•Area: C2
Earlier: Attacker-controlled HTTP/DNS
Later: Compromised sites, Exchange, Microsoft Graph, OneDrive, EWS
•Area: Operational security
Earlier: Infrastructure rotation
Later: Obfuscated malware, compromised services, delivery chains adapted after public expo-
sure
13.1 Cloud adoption and emerging trends
Cloud services became operational infrastructure for the actor, not merely victim resources. The
clearest trend is deeper integration with identity and SaaS ecosystems: malicious automation oper-
ating through valid accounts, trusted APIs and ordinary enterprise services will stay hard to detect.
Academic Year 2026/2027 | 24

--- PAGE 25 ---
CTI REPORTAPT34 / OILRIG