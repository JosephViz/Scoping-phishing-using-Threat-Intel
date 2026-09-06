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
 
Email Evidence Dataset used in this walk through: 
<br/>


<img src="https://i.imgur.com/rDLcHGe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
 
Analyzing "Email_01-Reported_Compensation_Acknowledgement" header.<br/>
 Revealed: <br/>
 - Failed Authentication results(SPF,DKIM, and DMARC)<br/>
 - Abnormal IP address and Domain Name.
 <br/>

 
<img src="https://i.imgur.com/M72GAZu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
 
Analyzing "Email_02_Compensation_Revision.eml" header.<br/>
 Revealed: <br/>
- Failed Authentication results (SPF, DKIM, and DMARC)<br/>
- Abnormal IP address & Domain Name
<br/>


<img src="https://i.imgur.com/sPtooMa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<br />
<p align="center">
 
Analyzing "Email_03-Protected_Voice_Message.eml"<br/>
 Revealed: <br/>
- Failed/absent authentication methods(such as, SPF=failed, DKIM=none, DMARC=failed)<br/>
- Phone number: "3055550184"<br/>
- Abnormal Ip and domain: 104.168.133.62 & "metalurgicasfelhenaresloeches[.]com" <br/> 
<img src="https://i.imgur.com/8YRtSWI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
 
<p align="center">
 
Analyzing "Email_04_Missed_Call_Notification.eml”<br/>
 revealed: <br/>
- Same Domain infrastructure as “Email_03_Protected_Voice_Message.eml”  <br/>
- Passed/Failed/absent authentication methods(such as, SPF=passed, DKIM=none, DMARC=failed)<br/>
- Abnormal IP and domain: 104.168.133.62 & "metalurgicasfelhenaresloeches[.]com"
 <br/>
 
 <img src="https://i.imgur.com/ew9w5Xp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
 
<p align="center">
 
Analyzing "Email_05_Voice_Messages_Delivery.eml"<br/>
 revealed: <br/>
- Passed authentication methods(SPF, DKIM, DMARC)<br/>
- same infrastructure as "Email_03_Protected_Voice_Message.eml” & “Email_04_Missed_Call_Notification.eml”<br/>
- Abnormal IP and domain: 104.168.133.62 & "metalurgicasfelhenaresloeches[.]com"
<img src="https://i.imgur.com/rjyA7jO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p align="center">
 
Analyzing "Email_06_BENIGN_Open-Enrichment_FAQ.eml" <br/>
 Revealed: <br/>
- passed authentication methods(SPF, DKIM, DMARC)<br/>
- Consistent domain name throughout "Return-path", "Reply-TO", & "From" <br/>
- Ip and domain: 10.20.5.14 & "hr@benefits.novacrest.example" <br/> 
<img src="https://i.imgur.com/0pC7ELZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
 
Analyzing "Email_07_BENIGN_Teams_Missed_Call.eml"<br/>
 Revealed: <br/>
- Passed authentication methods(SPF, DKIM, DMARC)<br/>
- Consistent domain name throughout "Return-path", "Reply-To", & "From" "<br/>
- Ip and domain: 40.107.22.15 & "teams.microsoft.com"<br/> 
<img src="https://i.imgur.com/h4insFP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
 
Analyzing "Email_08_BENIGN_Invoice.eml”  <br/>
 Revealed: <br/>
- Passed authentication methods (SPF, DKIM, DMARC)<br/>
- Ip and domain name: 10.20.5.14 & "apexoffice.example" <br/> 
<img src="https://i.imgur.com/eV0W0xz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
 
Analyzing “Email_09_BENIGN_SharePoint.em”<br/>
 Revealed: <br/>
- Passed authentication methods(SPF, DKIM, DMARC)<br/>
- IP and domain name: 40.107.22.15 & "sharepoint.com" <br/> 
<img src="https://i.imgur.com/ut9TSV9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
 
Analyzing “Email_10_BENIGN_MFA_Reminder.eml” <br/>
 Revealed: <br/>
- Passed authentication methods(SPF, DKIM, DMARC)<br/>
- Consistent domain name throughout "Return-path", "Reply-To", & "From" "<br/>
- Ip and domain: 10.20.5.14 & "novacrest.example" <br/> 
<img src="https://i.imgur.com/0PHHaV0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
 
Analyzing "Email_03-Protected_Voice_Message.eml"<br/>
 Revealed: <br/>
- Failed/absent authentication methods(such as, SPF=failed, DKIM=none, DMARC=failed)<br/>
- Phone number: "3055550184"<br/>
- Abnormal Ip and domain: 104.168.133.62 & "metalurgicasfelhenaresloeches[.]com" <br/> 
<img src="https://i.imgur.com/8YRtSWI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
 
Analyzing "Email_03-Protected_Voice_Message.eml"<br/>
 Revealed: <br/>
- Failed/absent authentication methods(such as, SPF=failed, DKIM=none, DMARC=failed)<br/>
- Phone number: "3055550184"<br/>
- Abnormal Ip and domain: 104.168.133.62 & "metalurgicasfelhenaresloeches[.]com" <br/> 
<img src="https://i.imgur.com/8YRtSWI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />


