# VulPecker: An Automated Vulnerability Detection System Based on Code Similarity Analysis  
In this paper, the authors have developed a technique for *Source code vulnerability detection problem* (Is a target source code vulnerable to a given vulnerability? If so, which segment of it?) **VulPecker** system utilizes code similarity algorithms to solve this problem.  
First of all the system uses three datasets:
- *NVD (National Vulnerability Dataset)*: The dataset contains basic information about vulnerabilities identified by CVE-ID.
- *VCID (Vulnerability Code Instance Dataset)*: Provided by authors containing C/C++ codes that are vulnerable to some vulnerabilities according to NVD.
- *VPD (Vulnerability Patch Dataset)*: Provided by authors containing several vulnerability diff hunks.
  
The system consists of two phases: *learning phase* and *detection phase*  
The input of the learning phase is the aforementioned datasets and this phase generates two outputs: 
1. *CVE-to-algorithm mapping*: A feature vector (including basic features, whitespace changes, variable changes, line modification, etc.) is extracted from diff hunks in VPD. Then the candidate code similarity algorithms are tested on different vulnerable codes and a mapping between CVE-IDs and correspondent algorithm that fits the vulnerability best, is generated.
2. *Vulnerability signatures*: First the unpatched diff code (lines prefixed with `-` or no prefix), the patched diff code (lines prefixed with `+`), and the unpatched code fragment corresponding to the vulnerability (using the similarity algorithm corresponding to the vulnerability) are extracted from VPD. Then we preprocess outputs mentioned before and generate vulnerability signature using code similarity algorithm associated with it.
  
In the detection phase, by using the target program and the CVE-to-algorithm mapping, the system generates the program signature. Then the detection engine searches vulnerability signatures in the target program signature and reports the vulnerability and the code fragment corresponded with it. Or informs the user that the program is not vulnerable.  
This system detected 40 vulnerabilities that are not published in NVD. 18 of them are not known for existence and the other 22 are silently patched by their vendors.
