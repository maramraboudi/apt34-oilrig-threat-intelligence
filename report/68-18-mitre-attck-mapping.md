# 18 MITRE ATT&CK Mapping

18 MITRE ATT&CK Mapping
OilRig swaps malware often but reuses familiar behaviors, which is why ATT&CK is such a good
lens.
The current G0049 record maps activity across the whole intrusion lifecycle. The matrix below shows
representative techniques per tactic; it is deliberately selective, not a full dump of MITRE’s record.
The full enterprise matrix provides broader framework context; it is not an OilRig-specific mapping.
Academic Year 2026/2027 | 32

--- PAGE 33 ---
CTI REPORTAPT34 / OILRIG
Figure 8:MITRE ATT&CK Enterprise Matrix, version 17.
Figure 9:Representative ATT&CK techniques used by OilRig (credential access highlighted).
18.1 Technique highlights
•Tactic: Initial access
Representative techniques: T1566.001, T1566.002, T1203, T1133, T1586.002, T1199
Pattern: Phishing, client exploits, compromised accounts, external remote services
•Tactic: Execution
Representative techniques: T1059.001, T1059.003, T1059.005, T1047, T1218.005
Pattern: Scriptable execution without one fixed executable; mshta in older chains
•Tactic: Persistence
Representative techniques: T1053.005, T1543.003, T1547.001, T1505.003, T1133
Pattern: Choice depends on the victim environment
•Tactic: Credential access
Representative techniques: T1555.003, T1555.004, T1003, T1056.001, T1110
Pattern: One of the most consistent parts of the toolkit
•Tactic: Discovery
Representative techniques: T1087, T1069, T1057, T1007, T1016, T1049, T1518
Pattern: Quiet preparation before selecting the next host or account
•Tactic: Collection
Representative techniques: T1119, T1217, T1115, T1113, T1074
Pattern: Automated collection and local staging
•Tactic: C2
Academic Year 2026/2027 | 33

--- PAGE 34 ---
CTI REPORTAPT34 / OILRIG
Representative techniques: T1071.001, T1071.004, T1102, T1572, T1573.002, T1008
Pattern: HTTP/DNS to compromised servers, Exchange and cloud APIs
•Tactic: Defense evasion
Representative techniques: T1027, T1036, T1070.004, T1564, T1102
Pattern: Obfuscation, masquerading, hidden windows, trusted services
•Tactic: Exfiltration
Representative techniques: T1048.003, T1567.002, T1041
Pattern: Alternative protocols (Exchange, FTP), cloud storage, web services
Coverage gap
ATT&CK gives strong visibility into endpoint and network behavior but not every operational
detail. Gaps are most likely where activity hides inside legitimate services, compromised ac-
counts, cloud APIs or encrypted traffic. Correlate identity, endpoint, DNS, proxy, Exchange
and cloud telemetry rather than relying on malware hashes alone.
Academic Year 2026/2027 | 34

--- PAGE 35 ---
CTI REPORTAPT34 / OILRIG