# Chapter VII - Detection, risk, and defense

### Report page 35

CHAPTER VII Detection, Risk and Defense
19 CTI Analyst Analysis of APT34’s Juicy Mix Campaign
19.1 Campaign Overview
The Juicy Mix campaign was an APT34/OilRig cyberespionage operation conducted in 2022 against
Israeli organizations. According to ESET Research, the campaign targeted Israeli organizations and
involved the compromise of a legitimate Israeli job-portal website, which was subsequently used as
command-and-control infrastructure. The operation deployed a new C#/.NET backdoor named
Mango, together with several post-compromise tools designed primarily for credential and browser-
data theft.
From a Cyber Threat Intelligence perspective, Juicy Mix is significant because it demonstrates a
complete intrusion operation rather than an isolated malware deployment. The campaign combined
initial access, execution, persistence, command and control, credential access, collection, and exfil-
tration into a coordinated attack chain.
Figure 10:Overview of components used in OilRig’s Juicy Mix campaign
19.2 Threat Actor and Strategic Intent
The activity was attributed to OilRig/APT34, an Iran-aligned cyberespionage group active since at
least 2014. ESET associates the group with targeting Middle Eastern governments and organizations
in sectors including chemical, energy, financial, and telecommunications.
The targeting observed in Juicy Mix is consistent with this strategic profile. ESET identified Israeli
organizations as the exclusive targets of both the Outer Space campaign in 2021 and the Juicy Mix
campaign in 2022.
The primary objective was intelligence collection, rather than destructive activity. The tools deployed
duringthecampaignprovidedtheoperatorswiththeabilitytoexecutecommands, gatherinformation
from compromised systems, steal browser data and credentials, and transfer selected files to attacker-
controlled infrastructure.

![Figure 10: Components described in the OilRig Juicy Mix campaign.](../figures/figure-10-juicy-mix-components.png)

### Report page 36

19.3 Initial Access
The first stage of the operation involved VBS droppers, which ESET assesses were likely distributed
through spearphishing emails.
The VBS dropper served several functions:
•Delivered the Mango backdoor to the victim system.
•Decoded the embedded payload.
•Created persistence through a scheduled task.
•Registered the compromised machine with the C2 infrastructure.
The dropper also used string obfuscation techniques to make its code more difficult to analyze and
detect. The embedded Mango payload was stored as Base64-encoded data and reconstructed during
execution.
Figure 11:String obfuscation function used by Mango’s VBS dropper
From a CTI perspective, this stage demonstrates the combination of social engineering, scripting,
payload delivery, and obfuscation to establish the initial foothold.
19.4 Execution and Persistence
After the VBS dropper executed, it installed the Mango backdoor and established persistence through
a scheduled task.
According to ESET’s analysis, the scheduled task executed Mango repeatedly at approximately
32-second intervals, allowing the backdoor to maintain continuous communication with its C2 infras-
tructure.
This behavior is important for CTI analysts because scheduled-task creation shortly after suspicious
script execution can provide a strong behavioral indicator of compromise.
The attacker therefore transformed the initial execution into a persistent foothold:
VBS execution→Mango deployment→Scheduled Task→Repeated execution

![Figure 11: String obfuscation function associated with Mango's VBS dropper.](../figures/figure-11-mango-vbs-obfuscation.png)

### Report page 37

19.5 Command and Control
Once Mango was installed, it established communication with an attacker-controlled C2 server.
A particularly important characteristic of the campaign was the use of a legitimate Israeli job-
portal website that had previously been compromised by OilRig. The website was abused as C2
infrastructure, allowing malicious communication to blend with legitimate web traffic.
Mango used encrypted communication and generated a victim identifier based on the machine name
and username. Commands were exchanged through HTTP requests, with the data protected using
XOR encryption and Base64 encoding, while TLS provided an additional layer of protection.
This represents an important CTI observation:
APT34 did not rely exclusively on dedicated attacker-owned infrastructure; it also abused
legitimate compromised infrastructure to make its communications less conspicuous.
19.6 Discovery and Remote Command Execution
The Mango backdoor provided operators with functionality for interacting with the compromised
system.
Its commands included:
•Executing files and shell commands.
•Enumerating directories.
•Retrieving information from the victim system.
•Downloading files.
•Uploading selected files to the C2 server.
The ability to execute shell commands gave the operators flexibility after initial compromise. Instead
of embedding every capability directly into the malware, the attackers could use the backdoor to
perform additional operations when required.
For a CTI analyst, this means that the presence of Mango should not be analyzed independently. Its
installation represented a platform for subsequent attacker activity.
19.7 Credential and Browser Data Collection
A major objective of the Juicy Mix operation was the theft of information stored by web browsers
and Windows.
ESET identified previously undocumented browser-data stealers deployed alongside Mango. These
tools targeted Chrome and Edge and collected:
•Browser cookies.
•Browsing history.
•Stored credentials.
ESET also identified a tool designed to steal information from Windows Credential Manager.
This capability significantly increased the value of the compromise. Browser credentials and authen-
tication material could potentially provide access to additional services and accounts.
From a CTI perspective, the deployment of dedicated credential-stealing tools demonstrates that the
operation was focused on expanding access and extracting valuable intelligence, rather than simply
maintaining a single compromised endpoint.

### Report page 38

19.8 Post-Compromise Tooling
APT34 did not depend exclusively on Mango.
ESET identified SampleCheck5000 (SC5k) among the post-compromise tools used by OilRig. SC5k
used the Microsoft Office Exchange Web Services API for command and control. Operators could
place commands and payloads inside draft email messages, which the downloader retrieved from the
compromised Exchange account.
SC5k could:
•Retrieve commands from Exchange drafts.
•Download additional payloads.
•Execute commands using cmd.exe.
•Store command output.
•Transfer files from a local staging directory.
•Return results through Exchange draft messages.
This is particularly relevant from a CTI perspective because it demonstrates alternative C2 mecha-
nisms and the abuse of legitimate enterprise services.
19.9 Collection and Exfiltration
After obtaining access and collecting credentials and browser information, the attackers could stage
and transfer selected data.
Mango included functionality to upload selected files to the C2 server. SC5k also supported file
exfiltration from local staging directories.
The overall collection process can therefore be represented as:
Identify valuable information→Collect→Stage locally→Transfer to C2
The campaign’s focus on browser credentials, cookies, browsing history, system information, and
selected files indicates an intelligence-collection objective.
19.10 Evolution from Outer Space to Juicy Mix
An important CTI finding is the relationship between the Outer Space campaign in 2021 and Juicy
Mix in 2022.
ESET identified multiple similarities between the two campaigns:
•Both targeted Israeli organizations.
•Both compromised legitimate Israeli websites for C2.
•Both used VBS droppers.
•Both deployed C#/.NET backdoors.
•Both used similar post-compromise tooling.
•Mango was developed as a successor to Solar.

### Report page 39

Figure 12:Overview of OilRig’s Outer Space compromise chain
Mango retained similarities with Solar while introducing additional capabilities, including TLS-based
C2 communication, native Windows APIs for executing files and commands, improved obfuscation,
and additional exfiltration functionality.
This evolution is important intelligence because it demonstrates that APT34 learned from previous
operations and modified its tooling rather than completely changing its operational methodology.
19.11 MITRE ATT&CK Interpretation
The Juicy Mix activity maps to the following MITRE ATT&CK techniques. Each row connects an
observed behavior to its corresponding attack stage and technique identifier.
Attack stage Observed behavior ATT&CK
technique
Initial access Spearphishing or malicious VBS deliveryT1566
Execution Visual Basic ScriptT1059.005
Execution Shell command executionT1059.003
Persistence Scheduled taskT1053.005
Command &
Control
Application-layer communication over web protocolsT1071.001
Credential access Browser credential theftT1555.003
Credential access Windows Credential Manager accessT1555.004
Collection Local data stagingT1074.001
Exfiltration Transfer of selected filesT1041
This mapping turns the campaign narrative into a structured view of adversary behavior.
19.12 CTI Analyst Assessment
From a CTI analyst perspective, the most important characteristic of Juicy Mix is the relationship
between the individual activities.
A single PowerShell or script execution event may not indicate compromise. Similarly, a scheduled
task or an external HTTPS connection may be legitimate.
However, the combination of:
Targeted delivery→VBS execution→Scheduled Task→Mango installation
→C2 communication→Discovery→Credential theft→Data staging→
Exfiltration

![Figure 12: OilRig Outer Space compromise chain.](../figures/figure-12-outer-space-compromise-chain.png)

### Report page 40

creates a recognizable intrusion pattern.
This allows CTI teams to move beyond static indicators such as hashes, domains, and IP addresses
and focus on behavioral intelligence.
The campaign also demonstrates APT34’s ability to reuse successful operational concepts while
improving its technical implementation. The transition from Solar to Mango illustrates this evolution
clearly: the underlying operational model remained similar, while the backdoor gained additional
capabilities and stronger obfuscation.
19.13 Intelligence Value for Defenders
The Juicy Mix campaign provides several actionable intelligence points for security operations:
•Monitor suspicious VBS and scripting activity, particularly when originating from email-delivered
content.
•Detect newly created scheduled tasks associated with scripts or unusual executable locations.
•Monitor PowerShell and command-shell execution following suspicious initial access.
•Monitor access to browser credential stores and Windows Credential Manager.
•Inspect outbound connections to unusual or compromised legitimate websites.
•Monitor abnormal HTTP/HTTPS communication from endpoints.
•Correlate endpoint, email, identity, DNS, and network telemetry.
•Hunt for sequences of behaviors rather than isolated indicators.
The objective is to detect the intrusion before credential theft and data exfiltration are completed.
20 Indicators of Compromise
Treat IOCs as time-bound evidence, not permanent signatures.
Older domains and hashes identify historical campaigns, while behavioral indicators (PowerShell
execution, DNStunneling, Exchange-basedC2, MicrosoftGraphabuse)stayusefulfornewervariants.
The examples below come from documented OilRig/APT34 reporting and are suitable for controlled
threat hunting or retrospective analysis.
Handle with care
Domains and IPs are shown defanged ([.]). Validate every historical indicator against live
telemetry before blocking: infrastructure can be recycled, sinkholed or reassigned.

### Report page 41

20.1 Documented indicators
Indicator Type Confidence Context
63D66D99E46FB93676A4F475A65566
D8
MD5 HIGH 2017 APT34 malicious
RTF
C9F16F0BE8C77F0170B9B6CE876ED
7FB
MD5 HIGH dupdatechecker.exe (2017)
1DE4810A10FA2D73CC589CA403A43
90B02C6DA5E
SHA-1 HIGH Solar.exe (ESET)
CB26EBDE498ECD2D7CBF1BC498E
1BCBB2619A96C
SHA-1 HIGH Mango.exe (ESET)
94.23.172[.]164 IPv4 HIGH 2017 APT34 host serving
dupdatechecker.doc
199.102.48[.]42 IPv4 HIGH ESET-reported host tecfor
sc-001-site1.gtempurl[.]co
m; Outer Space / Juicy
Mix
proxychecker[.]pro Domain HIGH POWRUNER /
BONDUPDATER C2
mumbai-m[.]site Domain HIGH BONDUPDATER DGA
infrastructure
rdppath[.]com Domain HIGH QUADAGENT C2
dns-update[.]club, cpuproc[.]com,
acrobatverify[.]com
Domain HIGH Historical OilRig reporting
hxxp://94.23.172[.]164/dupdatechecker
.doc
URL HIGH 2017 download URL
hxxp://mumbai-m[.]site/b.txt, hxxp://
dns-update[.]club/v.txt
URL HIGH Proxy / web-log hunting
HKCU\Office365DCOMCheckRegistry HIGH QUADAGENT session ID
and pre-shared key
20.2 File names and other artifact types
Treat these artifacts as leads for correlation, not standalone proof. Their value increases when they
appear on the same host or account and align with the campaign timeline, suspicious execution, or
network activity.
Endpoint and host artifacts
•File names:Reported examples includedupatechecker.exe,hUpdateCheckers.ps1,
Office365DCOMCheck.ps1and its VBS variant,SystemDiskClean.ps1and its VBS variant,
AdobeAcrobatLicenseVerify.ps1, andOut.jpgunder the user’s roaming application-data
directory. Names alone are weak indicators because legitimate software may use similar strings;
check path, signer, parent process, hash, and creation time.
•Registry:Correlate the QUADAGENTHKCU\Office365DCOMCheckkey with associated
scheduled-task creation and PowerShell or VBScript execution. Treat the key in isolation as
insufficient evidence.
•Mutexes and named pipes:Public reporting does not establish a stable universal mutex or
pipe. Preserve any campaign-specific value with its sample hash, source, and observation date;
absence of a known value is not evidence that the host is clean.
•Browser and Windows credentials:Investigate suspicious access to Chrome or Edge profile
data and Windows Credential Manager when it follows an unusual script, backdoor, or scheduled
task.

### Report page 42

Delivery, network, and cloud artifacts
•Email:Review recruitment-themed lures, malicious Office or RTF attachments, spoofed or
compromised senders, mismatched reply-to addresses, and content tailored to the recipient’s
role. Mandiant also reported macro-enabled XLS attachments used against banks.
•DNS:Hunt for BONDUPDATER-like DGA subdomains, DNSpionage-style DNS command and
control, and QUADAGENT fallback queries. High-entropy or rapidly changing subdomains from
one endpoint are more useful when correlated with process, host, and timing data.
•Cloud services:Review unusual Microsoft Graph, OneDrive, Outlook, or Exchange Web Ser-
vices activity from compromised endpoints; newly created attacker-controlled cloud accounts;
unexpected OAuth grants; and API access by unfamiliar applications or service accounts.
Validity and handling:Hashes and exact URLs may have high source confidence but little current
blocking value. Infrastructure indicators decay faster than behavioral patterns. Store each indicator
with its source, confidence, campaign, and first-seen and last-seen dates; validate historical indicators
against current telemetry before blocking.
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

### Report page 43

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
22 Threat Intelligence Analysis and Correlation
22.1 Three intelligence levels
•Strategic intelligence
– Question:Why is the actor operating, and whom does it target?
– Answer:Public assessments describe an Iran-aligned espionage mission focused on strategic
intelligence collection, especially from governments and strategically important industries in
the Middle East.
– OilRig example:Repeated interest in government, energy, finance, chemical, and telecom-
munications organizations.
•Operational intelligence
– Question:How are campaigns conducted and sustained?
– Answer:Campaigns combine targeted access, malware or legitimate-service command and
control, persistence, credential theft, collection, and exfiltration; infrastructure and tools
change across operations.
– OilRig example:Outer Space and Juicy Mix shared Israeli targeting and compromised-site
command and control; Mango followed Solar while extending its capabilities.
•Tactical intelligence
– Question:What can defenders detect or act on now?
– Answer:Hunt for documented indicators where relevant, and prioritize behaviors such as
suspicious PowerShell, scheduled tasks, credential-store access, DNS patterns, and unusual
Exchange or cloud API activity.
– OilRig example:Correlate endpoint, identity, DNS, email, and Microsoft 365 telemetry
instead of relying on a single hash or domain.

### Report page 44

22.2 How campaigns are linked to OilRig
No single clue proves that two campaigns belong to OilRig. Stronger attribution combines several
independent evidence categories.
•Correlation method: Domain and IP
How it works and its limit: DNS history, certificates, hosting patterns, passive DNS,
registration data; strongest when several features converge.
•Correlation method: Malware code
How it works and its limit: Shared code, configuration formats, function names, encryption
routines, development mistakes; beware common libraries and copied public code.
•Correlation method: Shared infrastructure
How it works and its limit: Reused servers, compromised sites, cloud accounts or email
infrastructure; confidence rises when reused together with the same malware or victim profile.
•Correlation method: Shared TTPs
How it works and its limit: PowerShell, scheduled tasks, credential theft, DNS/HTTP C2
and cloud services form a behavioral fingerprint, more durable than IOCs.
•Correlation method: Targeting overlap
How it works and its limit: Weak alone, because several Iranian groups pursue similar
requirements.
•Correlation method: Timing
How it works and its limit: New infrastructure soon after old infrastructure is exposed
shows continuity; supports, never replaces, technical evidence.
22.3 Confidence scale used in this report
•HIGH:directly documented by a primary source or supported by multiple independent sources.
•MEDIUM:strong correlation or a single reliable source, with meaningful uncertainty.
•LOW:plausible assessment with limited direct evidence.
•Unknown:insufficient public evidence for a defensible assessment.
Confidence should attach to each claim, not only to the actor name.
22.4 Known unknowns and collection priorities
Intelligence gaps
PublicreportingdoesnotprovideacompletecurrentIOCset, acompletevictimlist, orvisibility
into OilRig’s private cloud accounts and infrastructure. Exact relationships among vendor-
named clusters and the extent to which older tools remain active are also unresolved. Some
malware families are known only from limited samples.
Collection priorities:identity providers, Microsoft 365, Exchange, DNS, PowerShell, endpoint
process trees, browser credential access and outbound network traffic. These sources cover OilRig’s
strongest observable behaviors.
23 Risk and Threat Assessment

### Report page 45

Threat level: HIGH
For organizations in OilRig’s historically targeted sectors and regions the threat is high. The
risk comes from persistence, credential theft, trusted-service abuse and the ability to blend
into normal enterprise operations.
•Dimension: Potential impact
Assessment: Loss of sensitive information, credentials, strategic communications and intellec-
tual property; compromised identities can create secondary access to partners and other systems.
•Dimension: Likelihood of targeting
Assessment: Highest where the organization has strategic value to Iranian intelligence require-
ments, operates in a historically targeted sector, or exposes email, VPN, Exchange, identity or
cloud infrastructure.
•Dimension: Most exposed sectors
Assessment: Government, financial services, energy and oil/gas, chemical, telecommunica-
tions.
•Dimension: Attack surface
Assessment: Public-facing applications, remote access services, email, identity providers,
Microsoft 365, Exchange, browser credentials, endpoints.
•Dimension: Business risk
Assessment: Confidential-data loss, regulatory exposure, account compromise, incident-
response costs, compromise of trusted relationships.
•Dimension: Strategic risk
Assessment: For governments and strategic industries, long-term national, economic and
competitive consequences even without immediate destruction.
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

### Report page 46

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
25 Future Outlook
The most likely direction is continued movement toward trusted infrastructure and identity-based
access. OilRig’s use of Exchange and cloud-service-powered tooling shows why future campaigns
may lean on legitimate enterprise platforms instead of easily blocked dedicated servers.
•Area: TTPs
Expectation: Continued blending of phishing, exploitation, valid accounts, scripting and cloud
APIs; fewer obvious malware stages and more legitimate-looking administration.
•Area: Cloud and SaaS
Expectation: Microsoft 365 and similar platforms stay attractive: authentication, storage,
messaging and APIs without an obviously malicious destination.
•Area: Targeting
Expectation: Strategic government and critical-industry organizations; suppliers and trusted
partners as indirect paths to higher-value victims.
•Area: Malware
Expectation: Modular, lightweight tools handing communication and storage to legitimate
services.
•Area: Infrastructure
Expectation: Dedicated servers coexisting with compromised sites, cloud accounts, email
systems and APIs; blocking by IP or domain becomes insufficient.
25.1 Early-warning indicators of a new campaign
Watch for new Microsoft Graph/OneDrive applications, unusual Exchange automation, new cloud
accounts linked to phishing, recurring victim organizations, new downloader families with similar
configuration formats, and repeated use of the same identity or credential-theft workflow.

### Report page 47

Conclusion
APT34/OilRig is a mature Iranian cyber-espionage capability whose strength comes from persistence
and adaptation, not from reliance on a single malware family. Across campaigns it has combined
socialengineering, exploitation, scripting, credentialtheft, compromisedinfrastructureandlegitimate
enterprise services.
The clearest lesson for defenders is that OilRig cannot be stopped by IOC blocking alone. Organi-
zations need visibility across identity, endpoint, email, DNS, network and cloud layers, with threat
intelligence used to connect those observations into one intrusion story.
Top priorities
1. Phishing-resistant identity protection and credential hygiene
2. Rapid patching of exposed systems
3. Strong endpoint telemetry (PowerShell, scheduled tasks, credential stores)
4. Microsoft 365 and Exchange monitoring
5. Continuous hunting for abnormal use of trusted services
