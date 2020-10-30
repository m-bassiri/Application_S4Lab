# VulPecker: An Automated Vulnerability Detection System Based on Code Similarity Analysis  
In this paper, the authors has developed a technique for *Source code vulnerability detection problem* (Is a target source code vulnerable to a given vulnerability? If so, which segment of it?) **VulPecker** system utilizes code similarity algorithms to solve this problem.  
First of all the system uses three datasets:
- *NVD (National Vulnerability Dataset)*: The dataset contains basic information about vulnerabilities identified by CVE-ID.
- *VCID (Vulnerability Code Instance Dataset)*: Provided by authors containing C/C++ codes that are vulnerable to some vulnerabilities according to NVD.
- *VPD (Vulnerability Patch Dataset)*: Provided by authors containing several vulnerability diff hunks.
  
The system consists of two phases: *learning phase* and *detection phase*  
The input of learning phase is aforementioned datasets and this phase generates two outputs: 
1. *CVE-to-algorithm mapping*: A feature vector (including basic features, whitespace changes, variable changes, line modification, etc.) is extracted from diff hunks in VPD. Then candidate code similarity algorithms are tested on different vulnerable codes and a mapping between CVE-IDs and correspondent algorithm that fits the vulnerability best, is generated.
2. *Vulnerability signatures*: 
