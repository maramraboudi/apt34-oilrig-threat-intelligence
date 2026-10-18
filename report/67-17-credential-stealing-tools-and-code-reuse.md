# 17 Credential-Stealing Tools and Code Reuse

17 Credential-Stealing Tools and Code Reuse
17.1 Credential tooling
Credential theft is supported by both public and custom tools. MITRE documents LaZagne, PICK-
POCKET, VALUEVAULT, browser stealers such as CDumper and EDumper, and other credential-
focused utilities; Mimikatz and keyloggers also appear in operations.
Academic Year 2026/2027 | 31

--- PAGE 32 ---
CTI REPORTAPT34 / OILRIG
•Tool: LaZagne , Mimikatz
Target: Stored and in-memory credentials
Role in the intrusion: Public credential dumping tools
•Tool: PICKPOCKET, CDumper , EDumper
Target: Browser credentials and data
Role in the intrusion: Custom browser stealers
•Tool: VALUEVAULT
Target: Windows Credential Manager
Role in the intrusion: Custom Credential Manager stealer
•Tool: KEYPUNCH
Target: Keystrokes
Role in the intrusion: Keylogging
These tools turn an endpoint compromise into reusable identity access.
17.2 Relationships between tools
The strongest relationships come from functional succession and shared tradecraft: Mango followed
Solar, andtheclouddownloadersshareoneoperatingmodel. Codeandcapabilityoverlapcansupport
attribution, but should be combined with infrastructure, targeting and timing, never treated as proof
by itself, because common libraries and copied public code create false positives.