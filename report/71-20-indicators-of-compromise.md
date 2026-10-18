# 20 Indicators of Compromise

20 Indicators of Compromise
Treat IOCs as time-bound evidence, not permanent signatures.
Older domains and hashes identify historical campaigns, while behavioral indicators (PowerShell
execution, DNStunneling, Exchange-basedC2, MicrosoftGraphabuse)stayusefulfornewervariants.
The examples below come from documented OilRig/APT34 reporting and are suitable for controlled
threat hunting or retrospective analysis.
Handle with care
Domains and IPs are shown defanged ([.]). Validate every historical indicator against live
telemetry before blocking: infrastructure can be recycled, sinkholed or reassigned.
Academic Year 2026/2027 | 40

--- PAGE 41 ---
CTI REPORTAPT34 / OILRIG
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
Academic Year 2026/2027 | 41

--- PAGE 42 ---
CTI REPORTAPT34 / OILRIG
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