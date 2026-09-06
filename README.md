# Scoping Phishing Campaign using threat Intel
## Objective


This project aimed to scope a simulated phishing campaign by using Open-Source Intelligence(OSINT) to investigate and enrich identified Indicators of Compromise (IOCs). Tools such as VirusTotal and AbuseIPDB were used to analyze suspicious IP addresses and domains, assess their reputationn, and identify potential malicious activity. The investigation focused on correlating threat intelligence findings with the phishing evidence to determine the campaign's scope and strengthen the overall incident analysis.

### Skills Learned


- Phishing Email Analysis
- Threat Intelligence/ OSINT
- IOC Analysis & Enrichment
- Message Trace Analysis
- Incident Triage
- MITRE ATT&CK Mapping
- Incident Response
- Security Documentation & Reporting
- Minor use of KQL queries in Azure

### Tools Used

- source code editor (such as visual code) for analyzing email content & header
- Threat Intelligence & Malware analysis platform (such as VirusTotal) to investigate domains & URLs 
- IP reputation & Threat Intelligence Platform (AbuseIPDB) to investigate IP addresses and reports
- Framework (MITRE ATT&CK) for mapping attacks
- Word document for Reporting


<h2>Program walk-through:</h2>

<p align="center">
Email Evidence Dataset used in this walk through: <br/>
<img src="https://i.imgur.com/rDLcHGe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Analyzing "Email_01-Reported_Compensation_Acknowledgement" header.<br/>
Revealed Failed Authentication results(SPF,DKIM, and DMARC), Abnormal IP address and Domain Name.<br/>
<img src="https://i.imgur.com/M72GAZu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Analyzing "Email_02_Compensation_Revision.eml" header.<br/>
Revealed failed Authentication results (SPF, DKIM, and DMARC), Abnormal IP address, and Domain Name
<img src="https://i.imgur.com/sPtooMa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<br />
Analyzing "Email_03-Protected_Voice_Message.eml  <br/>
 Revealed:<br/>
- Failed/absent authentication methods(such as, SPF=failed, DKIM=none, DMARC=failed)<br/>
- Phone number: "3055550184"<br/>
- Abnormal Ip and domain: 104.168.133.62 & "metalurgicasfelhenaresloeches[.]com <br/> <br/>
<img src="https://i.imgur.com/8YRtSWI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

Analyzing "Email_04_Missed_Call_Notification.eml" <br/>
 Revealed: <br/>
- 
<img src="https://i.imgur.com/ew9w5Xp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
