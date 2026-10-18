# 21 Detection and Hunting Opportunities

21 Detection and Hunting Opportunities
Correlate endpoint, identity, email, DNS, proxy, and cloud telemetry. A single alert may be benign;
prioritize combinations that follow the sequence of initial access, execution, persistence, credential
access, command and control, and collection.
Endpoint execution and persistence
•Look for Office or RTF applications launchingmshta, PowerShell,wscript, orcscript; scripts
or executables written to user-writable directories; and scheduled tasks created shortly after
suspicious execution.
•Enable PowerShell Script Block and Module Logging. Review encoded commands, download
cradles, hidden windows, unusual parent processes, and scripts launched from user profiles or
temporary locations.
•Investigate browser credential-store or Windows Credential Manager access when it follows sus-
picious scripting, backdoor execution, or task creation.
Network and DNS
•Review outbound connections to newly observed domains, direct-to-IP HTTP, unexpected PUT
or POST transfers, and tunneling utilities such as Plink orngrok.
•Hunt for high-entropy or unusually long DNS labels, frequent failed lookups, encoded host in-
formation in queries, and endpoints that switch to DNS after HTTP or HTTPS command-and-
control failures.
Email and identity
•Review Office or RTF attachments, recruitment-themed messages, compromised internal senders,
mismatched reply-to addresses, and messages followed by script-interpreter execution.
•Alert on impossible travel, unusual VPN, OWA, or Citrix access, first-time authentication from
unfamiliar hosts, abnormal administrative logons, and repeated failures followed by success.
Microsoft 365 and Exchange
•Investigate Graph, OneDrive, Outlook, and EWS activity from unfamiliar applications; new
Academic Year 2026/2027 | 42

--- PAGE 43 ---
CTI REPORTAPT34 / OILRIG
OAuth grants; anomalous token use; new or unusual service accounts; automated message cre-
ation or deletion; and machine-generated mail with unusual timing.
Correlate EDR, DNS, email, authentication, proxy, Windows event, PowerShell, Exchange audit,
and Microsoft 365 audit logs. Escalate when multiple independent signals converge rather than on
one static IOC alone.
21.1 Behavioral sequence
Build detections aroundsequences, which are more resilient than any single indicator:
Detection chain
phishing / exploit→script execution→scheduled task→credential access→discovery→cloud
/ Exchange comms
21.2 Threat-hunting hypotheses
•H1.A compromised host uses PowerShell to establishperiodic C2.
•H2.An endpoint is queryingDGA-like domains.
•H3.A user account authenticates from an unusual device after credential theft.
•H4.A cloud API is used forautomated bidirectional file transfer.