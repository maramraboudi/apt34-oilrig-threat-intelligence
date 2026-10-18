# 4 Subgroups and Related Actors

4 Subgroups and Related Actors
Related does not mean identical: the report keeps confirmed and assessed relationships apart.
Figure 3:How strong is each relationship? Confidence bars follow the assessments cited in this section.
4.1 Lyceum (HEXANE / Storm-0133)
ESET describes Lyceum as anOilRig subgroupand links it to activity against Israeli government,
local-government and healthcare organizations. Tools attributed to this subgroup includeDanBot,
Shark, Milan, Marlin, Solar, Mango, OilForceGTXand downloaders that use legitimate cloud
services for C2. Other vendors track Lyceum separately, which illustrates the naming problem: the
subgroup label keeps a link to the OilRig ecosystemwithoutassuming one identical operational team.
4.2 BladedFeline
Inresearchpublishedon5June2025, ESETassessedwithMEDIUMconfidencethatBladedFeline
is an OilRig subgroup. The assessment rests on three observations: shared Middle Eastern espionage
targeting (including Iraqi and Kurdish officials), OilRig tools such asRDATandVideoSRVon
compromised systems, and code similarities between BladedFeline’sPrimeCacheIIS module and
OilRig’s RDAT backdoor. It is likely related, butnot an unquestionable synonym.
4.3 Collaboration with other Iranian actors
ESET reported cooperation betweenMuddyWaterand Lyceum in 2025. Overlap between Iran-
aligned groups is better described as anoperational relationshipthan as proof of a single organization.
4.4 Confirmed versus assessed relationships
•Confirmed:explicit, well-supported equivalence (for example APT34 = OilRig in MITRE).
•Assessed:evidence points to shared operators or tooling but does not prove organizational
identity (for example BladedFeline).
Academic Year 2026/2027 | 12

--- PAGE 13 ---
CTI REPORTAPT34 / OILRIG
•Evidence: Infrastructure
Value for linking: Links campaigns through domains, IPs, services
Strength: High if several pivots agree
Main limitation: Rotates quickly
•Evidence: Malware / code
Value for linking: Connects samples through implementation traits
Strength: High if distinctive
Main limitation: Code can be reused or copied
•Evidence: TTPs
Value for linking: Shows recurring behavior
Strength: Medium–High
Main limitation: Many actors share techniques
•Evidence: Targeting
Value for linking: Ties campaigns to strategic priorities
Strength: Medium
Main limitation: Several groups target the same sectors
•Evidence: Timing
Value for linking: Supports operational continuity
Strength: Medium
Main limitation: Correlation is not causation
•Evidence: Aliases
Value for linking: Normalizes vendor reporting
Strength: High for explicit equivalence
Main limitation: Taxonomies conflict
Academic Year 2026/2027 | 13

--- PAGE 14 ---
CTI REPORTAPT34 / OILRIG