# Contents and list of figures

### Report page 2

Contents
List of Figures 6
Introduction 7
1 Executive Summary 8
1.1 Key intelligence findings . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 8
1.2 Threat assessment . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 8
1.3 Key takeaways for defenders . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 8
CHAPTER I Profile of the Malicious Actor 9
2 Identity and Known Aliases . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 9
2.1 Who calls it what . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 9
3 Attribution Assessment . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 10
3.1 Evidence supporting Iranian alignment . . . . . . . . . . . . . . . . . . . . . . . . . 10
3.2 Confidence model . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 11
3.3 Alternative hypotheses . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 12
4 Subgroups and Related Actors . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 12
4.1 Lyceum (HEXANE / Storm-0133) . . . . . . . . . . . . . . . . . . . . . . . . . . . 12
4.2 BladedFeline . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 12
4.3 Collaboration with other Iranian actors . . . . . . . . . . . . . . . . . . . . . . . . 12
4.4 Confirmed versus assessed relationships . . . . . . . . . . . . . . . . . . . . . . . . 12
CHAPTER II Main Objective and Motivation 14
5 Motivation and Strategic Objectives . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 14
5.1 Strategic outcomes and operational enablers . . . . . . . . . . . . . . . . . . . . . . 14
5.2 Four operational characteristics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 14
6 Geopolitical Context and Intelligence Requirements . . . . . . . . . . . . . . . . . . . . . 15
6.1 Regional context . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 15
6.2 OilRig inside Iran’s cyber ecosystem . . . . . . . . . . . . . . . . . . . . . . . . . . 15
6.3 Likely intelligence requirements . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 15
6.4 Evolution of objectives . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 15
7 Targeting and Victimology . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
7.1 Geography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
7.2 Sector by sector . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
7.3 Target-selection patterns . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
CHAPTER III Known Operations 18

### Report page 3

8 Attack Lifecycle and Intrusion Analysis . . . . . . . . . . . . . . . . . . . . . . . . . . . . 18
8.1 Impact assessment . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 19
9 Initial Access and Social Engineering . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 19
10 Credential Access and Identity Operations . . . . . . . . . . . . . . . . . . . . . . . . . . 20
11 Infrastructure and Command-and-Control . . . . . . . . . . . . . . . . . . . . . . . . . . 20
11.1 Traditional infrastructure . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 21
11.2 Compromised infrastructure and web servers . . . . . . . . . . . . . . . . . . . . . 21
11.3 Exchange and cloud-based C2 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 21
11.4 Reuse, rotation and operational security . . . . . . . . . . . . . . . . . . . . . . . 21
CHAPTER IV Timeline of Activities 22
12 Operational Timeline 2014–2026 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 22
12.1 Milestone table . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 22
12.2 The four eras . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 23
13 Evolution of APT34 Tradecraft . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 24
13.1 Cloud adoption and emerging trends . . . . . . . . . . . . . . . . . . . . . . . . . 24
CHAPTER V Campaigns Conducted 25
14 Campaign Cards . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 25
14.1 Middle Eastern banking operations . . . . . . . . . . . . . . . . . . . . . . . . . . 25
14.2 POWRUNER: BONDUPDATER . . . . . . . . . . . . . . . . . . . . . . . . . . . 25
14.3 DNSpionage: Karkoff . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 25
14.4 HardPass . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 25
14.5 Outer Space . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 26
14.6 Juicy Mix . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 26
14.7 Cloud-service-powered downloaders . . . . . . . . . . . . . . . . . . . . . . . . . . 26
14.8 PowerExchange . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 26
14.9 Israeli operations as a pattern . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 27
14.10 Recent and related activity . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 27
15 Cross-Campaign Comparison . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 27
CHAPTER VI Toolkit of the Malicious Actor 29
16 Malware and Tooling Ecosystem . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 29
16.1 Toolkit at a glance . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 29
16.2 Script era: Helminth, POWRUNER, BONDUPDATER, SideTwist . . . . . . . . 30
16.3 .NET and DNS era: Karkoff, DNSpionage . . . . . . . . . . . . . . . . . . . . . . 31
16.4 Compromised-site era: Solar and Mango . . . . . . . . . . . . . . . . . . . . . . . 31
16.5 Enterprise-service era: PowerExchange and cloud downloaders . . . . . . . . . . . 31
16.6 Malware evolution in one sentence . . . . . . . . . . . . . . . . . . . . . . . . . . . 31

### Report page 4

17 Credential-Stealing Tools and Code Reuse . . . . . . . . . . . . . . . . . . . . . . . . . . 31
17.1 Credential tooling . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 31
17.2 Relationships between tools . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 32
18 MITRE ATT&CK Mapping . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 32
18.1 Technique highlights . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 33
CHAPTER VII Detection, Risk and Defense 35
19 CTI Analyst Analysis of APT34’s Juicy Mix Campaign . . . . . . . . . . . . . . . . . . . 35
19.1 Campaign Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 35
19.2 Threat Actor and Strategic Intent . . . . . . . . . . . . . . . . . . . . . . . . . . . 35
19.3 Initial Access . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 36
19.4 Execution and Persistence . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 36
19.5 Command and Control . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 37
19.6 Discovery and Remote Command Execution . . . . . . . . . . . . . . . . . . . . . 37
19.7 Credential and Browser Data Collection . . . . . . . . . . . . . . . . . . . . . . . 37
19.8 Post-Compromise Tooling . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 38
19.9 Collection and Exfiltration . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 38
19.10 Evolution from Outer Space to Juicy Mix . . . . . . . . . . . . . . . . . . . . . . 38
19.11 MITRE ATT&CK Interpretation . . . . . . . . . . . . . . . . . . . . . . . . . . 39
19.12 CTI Analyst Assessment . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 39
19.13 Intelligence Value for Defenders . . . . . . . . . . . . . . . . . . . . . . . . . . . 40
20 Indicators of Compromise . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 40
20.1 Documented indicators . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 41
20.2 File names and other artifact types . . . . . . . . . . . . . . . . . . . . . . . . . . 41
21 Detection and Hunting Opportunities . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 42
21.1 Behavioral sequence . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 43
21.2 Threat-hunting hypotheses . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 43
22 Threat Intelligence Analysis and Correlation . . . . . . . . . . . . . . . . . . . . . . . . . 43
22.1 Three intelligence levels . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 43
22.2 How campaigns are linked to OilRig . . . . . . . . . . . . . . . . . . . . . . . . . . 44
22.3 Confidence scale used in this report . . . . . . . . . . . . . . . . . . . . . . . . . . 44
22.4 Known unknowns and collection priorities . . . . . . . . . . . . . . . . . . . . . . 44
23 Risk and Threat Assessment . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 45
24 Defensive Recommendations . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 45
25 Future Outlook . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 46
25.1 Early-warning indicators of a new campaign . . . . . . . . . . . . . . . . . . . . . 46
Conclusion 47

### Report page 5

References and Intelligence Sources 48
MITRE ATT&CK . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 48
Government sources . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 48
Security vendors . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 48
Source reliability . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 48
Appendix A: Acronyms and Terminology 49

### Report page 6

List of Figures
1 Simplified OilRig attack lifecycle . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 8
2 Naming landscape around G0049 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 9
3 Confidence levels for reported and assessed relationships . . . . . . . . . . . . . . . . . 12
4 End-to-end OilRig attack chain . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 18
5 Evolution of OilRig command-and-control approaches . . . . . . . . . . . . . . . . . . 21
6 Selected milestones in the public history of APT34/OilRig . . . . . . . . . . . . . . . . 22
7 Analytical evolution of OilRig tooling . . . . . . . . . . . . . . . . . . . . . . . . . . . 29
8 MITRE ATT&CK Enterprise Matrix, version 17 . . . . . . . . . . . . . . . . . . . . . 33
9 Representative ATT&CK techniques used by OilRig . . . . . . . . . . . . . . . . . . . 33
10 Overview of components used in OilRig’s Juicy Mix campaign . . . . . . . . . . . . . . 35
11 String obfuscation function used by Mango’s VBS dropper . . . . . . . . . . . . . . . . 36
12 Overview of OilRig’s Outer Space compromise chain . . . . . . . . . . . . . . . . . . . 39
