# 9 Initial Access and Social Engineering

9 Initial Access and Social Engineering
Technical exploitation and human trust are combined; the lure is adapted to the victim’s role and
sector.
•Method: Spearphishing attachments
How OilRig uses it: Office and RTF documents with macros, exploits or embedded content.
The attachment is usually a delivery mechanism for scripts, exploits or a downloader, not the
final payload.
•Method: Spearphishing links
How OilRig uses it: Redirect victims to credential-harvesting pages or malware delivery
infrastructure; useful to avoid attachment scanning.
•Method: Public vulnerabilities
How OilRig uses it: Faster path to execution when vulnerable software is exposed (CVE-
2017-0199, CVE-2017-11882, later CVE-2024-30088). Needs accurate victim and software intel-
ligence.
•Method: Recruitment and professional lures
How OilRig uses it: HardPass : attackers posed as recruiters on LinkedIn to establish trust
before sending malicious content, making social context part of the attack surface.
•Method: Credential-based access
How OilRig uses it: Stolen or purchased credentials give direct access to email, VPN,
Academic Year 2026/2027 | 19

--- PAGE 20 ---
CTI REPORTAPT34 / OILRIG
remote desktop or cloud services, bypassing controls built only for malware delivery.
•Method: Trusted relationships
How OilRig uses it: Interest in trusted websites, email infrastructure and professional
relationships; even without a proven supply-chain compromise, abusing trusted infrastructure
creates a similar detection challenge.
Evolution
The trend is from attachment-heavy intrusion to a mixed model : exploitation, credential use,
social engineering and abuse of trusted services. The human layer remains important, while the
technical layer has become more flexible.