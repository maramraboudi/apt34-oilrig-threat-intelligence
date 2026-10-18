# 22 Threat Intelligence Analysis and Correlation

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
Academic Year 2026/2027 | 43

--- PAGE 44 ---
CTI REPORTAPT34 / OILRIG
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