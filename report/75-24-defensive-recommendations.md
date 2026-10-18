# 24 Defensive Recommendations

24 Defensive Recommendations
The strongest defense is layered detection: identity, endpoint, email, DNS/network and cloud data
correlated, not run as isolated controls.
•Layer: Prevention
Recommended actions: Patch public-facing systems quickly, remove unnecessary internet
exposure, enforce least privilege, segment sensitive systems, restrict execution from user-writable
directories.
•Layer: Identity protection
Recommended actions: Phishing-resistant MFA, separate privileged accounts, conditional
access, credential hygiene, session/token monitoring, rapid revocation after suspected compro-
mise. CISA recommends phishing-resistant MFA, strong passwords, account auditing and least
privilege against Iranian threat activity.
•Layer: Email security
Recommended actions: Block or detonate suspicious Office/RTF attachments, inspect URLs,
protect external forwarding, monitor compromised accounts, train users on recruitment and
business-themed lures.
•Layer: Endpoint security
Recommended actions: Monitor script interpreters, scheduled tasks, unusual child processes,
browser credential-store access, credential dumping, suspicious files in AppData or temp loca-
tions.
Academic Year 2026/2027 | 45

--- PAGE 46 ---
CTI REPORTAPT34 / OILRIG
•Layer: Network monitoring
Recommended actions: Watch direct-to-IP connections, unusual DNS, HTTP POST traffic,
tunneling tools, unexpected outbound connections from servers and admin systems.
•Layer: Cloud security
Recommended actions: Detailed Microsoft 365 audit logging; monitor Graph, OneDrive,
Exchange and OAuth; restrict application consent; investigate new accounts, tokens, service
principals. CISA highlights authentication, token, logging and third-party risks in cloud identity
infrastructure.
•Layer: Incident response
Recommendedactions: Isolateaffectedendpoints, revokesessionsandcredentials, investigate
identity providers and domain controllers, preserve cloud and endpoint logs, search for lateral
movement before restoration.
•Layer: Threat hunting
Recommended actions: Hypothesis-driven hunts on PowerShell, credential stores, scheduled
tasks, DNS, Exchange automation, cloud API access, remote-service authentication.
•Layer: CTI integration
Recommended actions: Normalize aliases, ingest time-scoped IOCs, map observations
to ATT&CK, keep campaign-specific confidence scores; use behavior and relationships as the
durable intelligence layer.