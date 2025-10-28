# Experiment-4: Analyze Email Headers and Detect Email Spoofing Using Mail Header Analyzer

## Aim
To analyze email headers and detect possible spoofing or malicious activity using Mail Header Analyzer.

---

## Requirements
- Mail Header Analyzer tool  
- Any email client (Gmail / Outlook / Yahoo) with suspicious email samples  

---

## Description
An email header contains routing information, including sender, recipient, subject, and most importantly, the path the email took across servers.  
Attackers often forge headers to trick recipients, called *email spoofing*.  

By analyzing headers, we can identify:  
- Real sender IP address  
- Authentication results (SPF, DKIM, DMARC)  
- Time delays between servers  
- Signs of spoofing / phishing  

---

## Procedure — Steps to Analyze Email Headers

*Step-1:* First, get the email header. In Gmail, select the mail, click the three dots, and choose *Show Original*.  


![(images/exp4-step1.png)](https://github.com/Yaswanth767/Digital-Forensics/blob/da133ced184283758bc66cba602e27290183df88/images/Screenshot%202025-09-02%20131305.png)


*Step-2:* After clicking *Show Original*, you will see the raw message with sender and receiver details.  

![(images/exp4-step2.png)](https://github.com/Yaswanth767/Digital-Forensics/blob/da133ced184283758bc66cba602e27290183df88/images/Screenshot%202025-09-02%20131334.png)

*Step-3:* Use the *Mail Header Analyzer tool* for easy reading and analysis.  



*Step-4:* Copy and paste the entire header text into the tool and click *Analyze Header*.  


![(images/exp4-step4.png)](https://github.com/Yaswanth767/Digital-Forensics/blob/eee1af0a1e9d2fddf3ff8c48823137f46d9a0264/images/Screenshot%202025-09-02%20131423.png)

*Step-5:* Identify key header fields:  
- From  
- To  
- Subject  
- Date  
- Return-Path  
- Received  
- Message-ID  
- SPF / DKIM / DMARC
  
![(images/exp4-step5.png)](https://github.com/Yaswanth767/Digital-Forensics/blob/eee1af0a1e9d2fddf3ff8c48823137f46d9a0264/images/Screenshot%202025-09-02%20131550.png)

*Step-6:* Check for IP addresses and hostnames.  
- Use tools like *WHOIS* or online IP lookup services to identify the geographical location and ownership of IP addresses found in the Received lines.  
- Verify if any IPs are suspicious or if the hostname doesn’t match the expected sending server.

![(images/exp4-step6.png)](https://github.com/Yaswanth767/Digital-Forensics/blob/eee1af0a1e9d2fddf3ff8c48823137f46d9a0264/images/Screenshot%202025-09-02%20131644.png)

*Step-7:* Examine the SPF, DKIM, and DMARC results:  
- *SPF (Sender Policy Framework):* Checks if the sender’s server/IP is authorized for that domain.  
- *DKIM (DomainKeys Identified Mail):* Ensures the email content wasn’t changed.  
- *DMARC (Domain-based Message Authentication, Reporting & Conformance):* Provides domain-level email authentication, policy, and reporting.

  
![(images/exp4-step7.png)](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/9fbbaf3e036c541c5ecf03ce8b980e220c3d37a3/images/WhatsApp%20Image%202025-09-01%20at%2012.29.05.jpeg)


- SPF Sender Policy Framework → Checks if the sender’s server/IP is allowed for that
domain
- DKIM DomainKeys Identified Mail → Ensures email content wasn’t changed.

![(images/exp4-step7.png)](https://github.com/Yaswanth767/Digital-Forensics/blob/eee1af0a1e9d2fddf3ff8c48823137f46d9a0264/images/Screenshot%202025-09-02%20131535.png)


![(images/exp4-step7.png)](https://github.com/Yaswanth767/Digital-Forensics/blob/eee1af0a1e9d2fddf3ff8c48823137f46d9a0264/images/Screenshot%202025-09-02%20131849.png)

---

## Expected Output
- The Mail Header Analyzer highlights key email header fields.  
- Authentication checks (SPF/DKIM/DMARC) show whether the email is genuine or spoofed.  
- Suspicious IP addresses or mismatched hostnames can be identified.  
- Email spoofing or phishing attempts are detected.  
