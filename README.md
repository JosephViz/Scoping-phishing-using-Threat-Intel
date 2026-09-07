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
- ChatGPT/Claude for generating the emails, fake scenario, and organization
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
 - Abnormal IP address and Domain Name: 192.174.87.78 & "altamimitex.com"
 <br/>

 
<img src="https://i.imgur.com/M72GAZu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
 
Analyzing "Email_02_Compensation_Revision.eml" header.<br/>
 Revealed: <br/>
- Failed Authentication results (SPF, DKIM, and DMARC)<br/>
- Abnormal IP address & Domain Name: 192.174.87.78 & "altamimitex.com"
<br/>


<img src="https://i.imgur.com/sPtooMa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/C6NnVQq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
<br/>
<br/>

<p align="center">
 
 ## Threat Intel

<p align="center">

IOC Enrichment Through AbuseIPDB(192.178.87.78)
<br/>
Revealed: <br/>
- IP was reported 65 times.<br/>
- Confidence of Abuse is 21%<br/>
- City, Domain Name, and Country <br/>
- Reporting of recent activities and IoA Timestamps<br/>
<img src="https://i.imgur.com/TxnNSP3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<img src="https://i.imgur.com/QOuD60c.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
 
IOC Enrichment Through AbuseIPDB(104.168.133.62) 
<br/>
 Revealed: <br/>
- IP was reported 3 times; Confidence of Abuse:0%<br/>
- City, Domain Name, and Country<br/>
- Reporting of recent activities and IoA Timestamps <br/> 
<img src="https://i.imgur.com/I9dOxQU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/HLzcsST.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">

Malicious Domain Analysis via VirusTotal(hxxps://altamimitex.com)
<br/>
Revealed: <br/>
- Domain name has been reported "malicious" by 20 different security vendors<br/>
- First Submission, Last Submission, and Last Analysis<br/>
- Flagged "phishing", "malware", and "Malicious" <br/>
<img src="https://i.imgur.com/5CkU5G4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<img src="https://i.imgur.com/cChUYQk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">

Malicious Domain Analysis via VirusTotal(hxxps://metalurgicasdelhenaresloeches.com)
<br/>
Revealed: <br/>
- Domain name has been reported "Malicious" by 14 different security vendors<br/>
- First Submission, Last Submission, and Last Analysis<br/>
- Flagged "phishing", and "Malicious" <br/>
<img src="https://i.imgur.com/53VNpdA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<img src="https://i.imgur.com/xqtI4fW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

## How far did this spread? Who clicked? and who's actually compromised? via Azure Data explorer

<p align="center">

Ran a KQL query specifying mail delivery. Scoping it by SenderIP, SPF/DKIM/DMARC results, and campaign
<br/>
Revealed: <br/>
- Campaign A, 192.174.87.78 sent 9 messages to 9 different employees. One was trashed, while another was quarentined<br/>
- Campaign B, 104.168.133.62, sent 8 messages to 8 different employeess. however 2/8 messages were blocked.<br/>
<img src="https://i.imgur.com/myF79C5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<br />
<br />

<p align="center">

Minimizing the scope by querying who clicked on what, and who submitted credentials
<br/>
Revealed: <br/>
- In campaign A, four employees clicked on the "hxxps://altamimitex.com" link while two of them clicked and submitted credentials.<br/>
- In campaign B, two employees clicked on the "hxxps://metalurgicasdelhenaresloeches.com” link and both submitted credentials.<br/>
<img src="https://i.imgur.com/ZyKv5Sv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<img src="https://i.imgur.com/wKQC9lZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">

User login activity Investigation(User:Maria)
<br/>
Revealed: <br/>
- User signed in from Miami at 12:45:00PM before submitting credentials<br/>
- At 2:39:41pm, after Maria submitted credentials, logs reveal a sign-in from Amsterdam, NL, via Linux<br/>
- IP address: 198.18.7.21 <br/>
- last login was at 2:41:02pm, in which unknown entity went into Microsoft 365<br/>
- Reveals impossible trave and stolen credentials
<img src="https://i.imgur.com/ngi3mnO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<br />
<br />

<p align="center">

User login activity Investigation(User:Samuel Price)
<br/>
Revealed: <br/>
- User signed in from Miami at 2:16:00pm before submitting credentials<br/>
- At 2:46:54pm, after Samuel Price submitted credentials, logs reveal a sign-in from Stockholm SE via Linux.<br/>
- IP address: 198.18.7.44 <br/>
- First and Last Login was at 2:46:45pm, in which unknown entity went into Microsoft 365
- Reveals impossible trave and stolen credentials
<img src="https://i.imgur.com/rZDUGie.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<br />
<br />

<p align="center">

User login activity Investigation(User:Caleb Wright)
<br/>
Revealed: <br/>
- User signed in from Miami at 2:30:00pm before submitting credentials<br/>
- At 2:59:33pm, after Caleb Wright submitted credentials, logs reveal a sign-in from Amsterdam, NL, via Linux.<br/>
- IP address: 198.18.7.21 <br/>
- First and last login was at 2:59:33pm, in which external threat actor went into Microsoft 365
- Reveals impossible trave and stolen credentials
<img src="https://i.imgur.com/epBdHCT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<br />
<br />

<p align="center">

User login activity Investigation(User:Priya Noir)
<br/>
Revealed: <br/>
- Logs indicate "Priya Noir" account was not accessed by the threat actor at any given time.
<img src="https://i.imgur.com/O0XGYnM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<br />
<br />

