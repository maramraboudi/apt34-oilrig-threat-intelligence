# 19 CTI Analyst Analysis of APT34’s Juicy Mix Campaign

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
Academic Year 2026/2027 | 35

--- PAGE 36 ---
CTI REPORTAPT34 / OILRIG
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
Academic Year 2026/2027 | 36

--- PAGE 37 ---
CTI REPORTAPT34 / OILRIG
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
Academic Year 2026/2027 | 37

--- PAGE 38 ---
CTI REPORTAPT34 / OILRIG
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
Academic Year 2026/2027 | 38

--- PAGE 39 ---
CTI REPORTAPT34 / OILRIG
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
Academic Year 2026/2027 | 39

--- PAGE 40 ---
CTI REPORTAPT34 / OILRIG
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