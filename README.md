Purpose

The purpose of this dataset is to collect and document both benign and malicious network behaviors in a controlled virtual environment. The dataset is intended to support cybersecurity research, traffic analysis, behavior classification, and machine learning applications by providing labeled network traffic representing common user activities and malicious attack scenarios.


Motivation

Modern networks generate large amounts of traffic, making it difficult to manually identify malicious behavior. This dataset provides structured, behavior-aware annotations that include high-level intent, behavioral sequences, expected network indicators, human-readable explanations, and MITRE ATT&CK mappings. These additions provide greater context than traditional attack labels and support explainable cybersecurity research and behavioral analysis.


Environment

The dataset was generated using three virtual machines:

- Ubuntu VM Server (target and packet capture machine)
- Kali Linux VM (attacker machine and legitimate user machine)

Traffic was captured using packet capture tools and converted into flow-based records for analysis.


Dataset Structure

The dataset contains both benign and attack scenarios.

Benign Scenarios

N1 – Normal Web Browsing
N2 – Normal SSH Administrative Session
N3 – Normal File Transfer Session

Attack Scenarios

A1 – Port Scanning
A2 – Repeated Failed SSH Login Attempts
A3 – Suspicious Post-Login Activity
A4 – Data Exfiltration
A5 – SSH Brute Force
A6 – Directory Enumeration / Automated Web Requests


The dataset uses the following behavior categories:

Authentication
Web Browsing
File Transfer
Reconnaissance
Discovery
Collection
Exfiltration

Attack scenarios are mapped to relevant MITRE ATT&CK tactics and techniques to provide standardized behavioral context and improve interoperability with threat detection and security analytics frameworks.


Scenario Summaries

N1 – Normal Web Browsing

Label: Benign	
Overall Intent: Access legitimate websites and retrieve web content	
Behavior Sequence: Web Browsing → File Download
Packets: 35,704
Flows: 866
Key Characteristics: HTTPS traffic, browser activity, file download

N2 – Normal SSH Administrative Session

Label: Benign	
Overall Intent: Perform legitimate remote system administration
Behavior Sequence: Authentication → Discovery → File Transfer	
Packets: 19,597
Flows: 5	
Key Characteristics: SSH login, command execution, SCP transfer

N3 - Normal File Transfer Session

Label: Benign
Overall Intent: Transfer authorized files between trusted systems
Behavior Sequence: Authentication → File Transfer
Packets: 3,755
Flows: 156
Key Characteristics: SSH login, SCP upload/download, larger data transfers

A1 - Port Scanning

Label: Attack
Overall Intent: Identify open ports and services on a target system
Behavior Sequence: Reconnaissance 
Packets: 4,033
Flows: 2,005
Key Characteristics: Nmap scanning, multiple destination ports, service enumeration

A2 – Repeated Failed SSH Login Attempts

Label: Attack
Overall Intent: Attempt unauthorized access through repeated failed logins
Behavior Sequence: Authentication
Packets: 3,018
Flows: 434
Key Characteristics: Repeated SSH failures, credential guessing activity

A3 - Successful Login Followed by Malicious Post-Login Activity

Label: Attack
Overall Intent: Explore the system and collect data after gaining access
Behavior Sequence: Authentication → Discovery → Collection → Exfiltration
Packets: 12,675
Flows: 34
Key Characteristics: SSH login, reconnaissance commands, archive creation, SCP transfer

A4 - Suspicious Data Exfiltration

Label: Attack
Overall Intent: Transfer data from the target system to an external host
Behavior Sequence: Exfiltration
Packets: 85,456
Flows: 1,213
Key Characteristics: Large SCP transfers, sustained outbound traffic


A5 - SSH Brute Force

Label: Attack
Overall Intent: Gain unauthorized access by testing multiple passwords
Behavior Sequence: Authentication
Packets: 4,151
Flows: 193
Key Characteristics: Hydra brute-force activity, repeated SSH authentication attempts


A6 – Directory Enumeration

Label: Attack
Overall Intent: Discover web resources and directories on the target server
Behavior Sequence: Reconnaissance
Packets: 4,613
Flows: 1,096
Key Characteristics: Nmap HTTP enumeration, repeated web requests, resource discovery


Intended Use

This dataset is intended for:

Cybersecurity education
Behavioral traffic analysis
Network forensics
Threat hunting and attack detection research
Machine learning classification
MITRE ATT&CK mapping exercises

Disclaimer

All traffic was generated within a controlled laboratory environment using virtual machines. No real systems, sensitive information, or production networks were involved in the creation of this dataset.

