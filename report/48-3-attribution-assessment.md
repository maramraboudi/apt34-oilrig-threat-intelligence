# 3 Attribution Assessment

3 Attribution Assessment
Iran alignment is well supported; exact organizational control is not public.
Attribution should be written as an evidence-based confidence judgment, never as a binary fact.
For OilRig, several independent evidence streams point the same way, and that convergence is what
makes the case strong.
3.1 Evidence supporting Iranian alignment
•Evidence type: Government assessment
What the public record shows: Mandiant assessed in 2017 that APT34 operated on behalf of
the Iranian government; MITRE repeats this and calls OilRig a suspected Iranian threat group.
•Evidence type: Infrastructure
Academic Year 2026/2027 | 10

--- PAGE 11 ---
CTI REPORTAPT34 / OILRIG
What the public record shows: Historical infrastructure contained references to Iran and
used Iranian infrastructure.
•Evidence type: Targeting
What the public record shows: Government, energy, financial, chemical, telecom and Israeli
strategic organizations fit an intelligence-collection profile.
•Evidence type: Technical tradecraft
What the public record shows: A recurring mix of PowerShell, DNS/HTTP C2, credential
theft, Office exploitation, scheduled tasks and custom downloaders appears across campaigns.
•Evidence type: Malware continuity
What the public record shows: Tool succession such as Solar→Mango; ESET assigned
SC5k, OilCheck, ODAgent and OilBooster to OilRig with HIGH confidence.
•Evidence type: Behavior
What the public record shows: Repeated compromise of the same victims and migration
from dedicated C2 to cloud services show a stable operational culture even as tools change.
3.2 Confidence model
•Dimension: Iran alignment
Basis: Infrastructure references, targeting, consistent independent reporting
Confidence: HIGH
•Dimension: Cyber-espionage mission
Basis: Long-term reconnaissance and collection across strategic sectors
Confidence: HIGH
•Dimension: Government sponsorship
Basis: Mandiant and MITRE assessments; organizational details not public
Confidence: HIGH (details not public)
•Dimension: APT34↔OilRig overlap
Basis: MITRE merged previously separate records
Confidence: HIGH
•Dimension: Lyceum relationship
Basis: ESET describes Lyceum/HEXANE/Storm-0133 as an OilRig subgroup
Confidence: HIGH (ESET tracking)
•Dimension: BladedFeline relationship
Basis: ESET: likely subgroup, based on tools, code similarity and targeting
Confidence: MEDIUM
•Dimension: Exact operators / team
Basis: Identities not established; not proven that every cluster is one team
Confidence: LOW / unknown
Overall judgment
APT34/ OilRig is an Iran-aligned, state-sponsored or state-directed cyber-espionage actor, with
HIGH confidence at the broad actor level. The evidence is much stronger for Iran alignment
than for claims about internal structure or individual operators; subgroup claims must keep
their own confidence labels. This prevents over-attribution while remaining useful to defenders.
Academic Year 2026/2027 | 11

--- PAGE 12 ---
CTI REPORTAPT34 / OILRIG
3.3 Alternative hypotheses
Some overlaps could reflectother Iranian groups, shared contractors, copied tools or com-
mon open-source components. Lyceum and other Iranian clusters share parts of the regional
targeting picture, so every cross-group relationship must be assessed on its own. Overall attribution
to the OilRig/APT34 cluster isHIGH, but attribution of an individual campaign, subgroup or alias
may be lower.