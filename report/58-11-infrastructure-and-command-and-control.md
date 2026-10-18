# 11 Infrastructure and Command-and-Control

11 Infrastructure and Command-and-Control
The important shift is not where the server sits, but how well the traffic imitates normal business
activity.
Academic Year 2026/2027 | 20

--- PAGE 21 ---
CTI REPORTAPT34 / OILRIG
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
Academic Year 2026/2027 | 21

--- PAGE 22 ---
CTI REPORTAPT34 / OILRIG