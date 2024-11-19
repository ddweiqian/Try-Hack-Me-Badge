Cyber Threat Intelligence(CTI) is evidence-based knowledge about adversaries, including their indicators, tactics, motivations, and actionable advice against them.

# Introduction to Cyber Threat Intelligence
## Understanding and Using Data, Information, and Intelligence in CTI
**Data Collection:** 
Begin by collecting discrete data points (like IP addresses, URLs, and file hashes) from sources such as your firewall logs, server activity, and network traffic. This data will later be used to identify and verify specific threats.
**Building Information:** 
Combine multiple data points to create information by identifying activities or patterns that indicate a potential threat. For example, tracking how often an unusual IP range tries to access your network can help you analyze access patterns.
**Generating Intelligence:** 
Correlate data and information to extract insights. For instance, if the same IP shows repeated access attempts alongside unauthorized login attempts, you might recognize a pattern of suspicious behavior that indicates a possible brute-force attack.

## Applying CTI to Protect Assets and Inform Decision-Making
Use CTI findings to **prioritize critical assets** by assessing which systems are most vulnerable or likely to be targeted, helping you allocate resources for protection more effectively.

**Provide actionable insights to decision-makers** on high-risk areas. For example, if intelligence shows an increase in phishing attacks in your sector, this information could justify investments in anti-phishing solutions and user training.
Use intelligence reports to **shape security awareness programs** and training for employees, emphasizing identified vulnerabilities or common attack techniques.

## Key Questions to Develop Threat Context
**Identify Adversaries and Motives:** Analyze intelligence to understand who your likely attackers are (e.g., competitors, hacktivists, cybercriminal groups) and their possible motivations (e.g., financial gain, sabotage).

**Capabilities:** Look for patterns in the tactics used by past adversaries to gauge their technical capabilities and the level of threat they pose.

**Indicators of Compromise (IOCs):** Define a set of IOCs (such as specific file signatures or network behaviors) to help your team detect signs of compromise early.

## Source-Based Threat Intelligence Gathering
**Internal Sources:** Leverage system logs, incident reports, and vulnerability assessment results to understand current security posture and identify recurring issues.

**Community Sources:** Participate in open forums and dark web monitoring to gain insights into new threats and how other organizations respond to them.

**External Sources:** Use threat intelligence feeds (both commercial and open-source) to stay informed about global cyber threats and any specific vulnerabilities impacting similar organizations.

## Applying Threat Intelligence Classifications in Practice
**Strategic Intelligence:** Use strategic reports to guide long-term security investments and inform upper management of the organization’s risk landscape. This might involve identifying trends (e.g., increased ransomware attacks) that could shape company policies and cybersecurity budget allocations.

**Technical Intelligence:** Analyze artefacts such as malicious code or phishing emails to understand the technical details of attacks and create specific defensive measures.
**Tactical Intelligence:** Monitor TTPs to refine real-time response strategies. For example, if an attack uses a specific exploit or phishing method, tactical intel helps adjust defenses to counter similar attacks immediately.

**Operational Intelligence:** Investigate adversaries’ intent and potential targets within your environment. Use this intelligence to prioritize protections around the most critical assets, ensuring that key systems, data, and processes have adequate safeguards.

# CTI Lifecycle
<img src= "https://github.com/user-attachments/assets/aa58ea8b-49f2-4d54-8b36-d9a0bf60f1c7" alt="image" width="500" height="300">

## Direction
Every threat intel program requires to have objectives and goals defined, involving identifying the following parameters:

- Information assets and business processes that require defending.
- Potential impact to be experienced on losing the assets or through process interruptions.
- Sources of data and intel to be used towards protection.
- Tools and resources that are required to defend the assets.
  
This phase also allows security analysts to pose questions related to investigating incidents.

## Collection
Once objectives have been defined, security analysts will gather the required data to address them. Analysts will do this by using commercial, private and open-source resources available. Due to the volume of data analysts usually face, it is recommended to automate this phase to provide time for triaging incidents.

## Processing
Raw logs, vulnerability information, malware and network traffic usually come in different formats and may be disconnected when used to investigate an incident. This phase ensures that the data is extracted, sorted, organised, correlated with appropriate tags and presented visually in a usable and understandable format to the analysts. SIEMs are valuable tools for achieving this and allow quick parsing of data.

## Analysis
Once the information aggregation is complete, security analysts must derive insights. Decisions to be made may involve:

- Investigating a potential threat through uncovering indicators and attack patterns.
- Defining an action plan to avert an attack and defend the infrastructure.
- Strengthening security controls or justifying investment for additional resources.


## Dissemination
Different organisational stakeholders will consume the intelligence in varying languages and formats. For example, C-suite members will require a concise report covering trends in adversary activities, financial implications and strategic recommendations. At the same time, analysts will more likely inform the technical team about the threat IOCs, adversary TTPs and tactical action plans.

As part of the dissemination phase of the lifecycle, CTI is also distributed to organisations using published threat reports. These reports come from technology and security companies that research emerging and actively used threat vectors. They are valuable for consolidating information presented to all suitable stakeholders. Some notable threat reports come from [Mandiant](https://cloud.google.com/security/resources), [Recorded Future](https://www.recordedfuture.com/resources) and [AT&TCybersecurity](https://levelblue.com/).

## Feedback
The final phase covers the most crucial part, as analysts rely on the responses provided by stakeholders to improve the threat intelligence process and implementation of security controls. Feedback should be regular interaction between teams to keep the lifecycle working.

# CTI Standards & Frameworks

Standards and frameworks provide structures to rationalise the distribution and use of threat intel across industries. They also allow for common terminology, which helps in collaboration and communication. Here, we briefly look at some essential standards and frameworks commonly used.

## MITRE ATT&CK
The [ATT&CK framework](https://attack.mitre.org/) is a knowledge base of adversary behaviour, focusing on the indicators and tactics. Security analysts can use the information to be thorough while investigating and tracking adversarial behaviour.

![image](https://github.com/user-attachments/assets/f27bfa9a-7ac4-451f-9818-7b1ef8be33de)

## TAXII
[The Trusted Automated eXchange of Indicator Information (TAXII)](https://oasis-open.github.io/cti-documentation/taxii/intro) defines protocols for securely exchanging threat intel to have near real-time detection, prevention and mitigation of threats. The protocol supports two sharing models:

- **Collection:** Threat intel is collected and hosted by a producer upon request by users using a request-response model.
- **Channel:** Threat intel is pushed to users from a central server through a publish-subscribe model.

## STIX
[Structured Threat Information Expression (STIX)](https://oasis-open.github.io/cti-documentation/stix/intro) is a language developed for the "specification, capture, characterisation and communication of standardised cyber threat information". It provides defined relationships between sets of threat info such as observables, indicators, adversary TTPs, attack campaigns, and more.

## Cyber Kill Chain
Developed by Lockheed Martin, the Cyber Kill Chain breaks down adversary actions into steps. This breakdown helps analysts and defenders identify which stage-specific activities occurred when investigating an attack. The phases defined are shown in the image below.

![image](https://github.com/user-attachments/assets/23dfb103-08d7-4a8e-803e-8286c288c55f)

![image](https://github.com/user-attachments/assets/b0aaf185-1852-4f22-b323-42a9d091fafa)

Over time, the kill chain has been expanded using other frameworks such as ATT&CK and formulated a new Unified Kill Chain.

## The Diamond Model

![image](https://github.com/user-attachments/assets/0c30ef04-62d5-4ee1-b793-b89b9fe03d1c)

The diamond model looks at intrusion analysis and tracking attack groups over time. It focuses on four key areas, each representing a different point on the diamond. These are:

- **Adversary:** The focus here is on the threat actor behind an attack and allows analysts to identify the motive behind the attack.
- **Victim:** The opposite end of adversary looks at an individual, group or organisation affected by an attack.
- **Infrastructure:** The adversaries' tools, systems, and software to conduct their attack are the main focus. Additionally, the victim's systems would be crucial to providing information about the compromise.
- **Capabilities:** The focus here is on the adversary's approach to reaching its goal. This looks at the means of exploitation and the TTPs implemented across the attack timeline

An example of the diamond model in play would involve an adversary targeting a victim using phishing attacks to obtain sensitive information and compromise their system, as displayed on the diagram. As a threat intelligence analyst, the model allows you to pivot along its properties to produce a complete picture of an attack and correlate indicators.

# Threat Intelligence Tools


## Threat Intelligence

Threat Intelligence is the analysis of data and information using tools and techniques to generate meaningful patterns on how to mitigate against potential risks associated with existing or emerging threats targeting organisations, industries, sectors or governments.

To mitigate against risks, we can start by trying to answer a few simple questions:

- Who's attacking you?
- What's their motivation?
- What are their capabilities?
- What artefacts and indicators of compromise should you look out for?


### Threat Intelligence Classifications:
Threat Intel is geared towards understanding the relationship between your operational environment and your adversary. With this in mind, we can break down threat intel into the following classifications: 

- Strategic Intel: High-level intel that looks into the organisation's threat landscape and maps out the risk areas based on trends, patterns and emerging threats that may impact business decisions.
- Technical Intel: Looks into evidence and artefacts of attack used by an adversary. Incident Response teams can use this intel to create a baseline attack surface to analyse and develop defence mechanisms.
- Tactical Intel: Assesses adversaries' tactics, techniques, and procedures (TTPs). This intel can strengthen security controls and address vulnerabilities through real-time investigations.
- Operational Intel: Looks into an adversary's specific motives and intent to perform an attack. Security teams may use this intel to understand the critical assets available in the organisation (people, processes, and technologies) that may be targeted.

## UrlScan.io

[Urlscan.io](https://urlscan.io/) is a free service developed to assist in scanning and analysing websites. It is used to automate the process of browsing and crawling through websites to record activities and interactions.

When a URL is submitted, the information recorded includes the domains and IP addresses contacted, resources requested from the domains, a snapshot of the web page, technologies utilised and other metadata about the website.

The site provides two views, the first one showing the most recent scans performed and the second one showing current live scans.

<img src= "https://github.com/user-attachments/assets/8a33ec10-2baa-45b9-92a0-692962be2524" alt="image" width="500" height="300"> <img src= "https://github.com/user-attachments/assets/dfad66f8-cdbc-40c8-af9f-6899610c59b3" alt="image" width="500" height="300"> 

### Scan Results
URL scan results provide ample information, with the following key areas being essential to look at:

- **Summary:** Provides general information about the URL, ranging from the identified IP address, domain registration details, page history and a screenshot of the site.
- **HTTP:** Provides information on the HTTP connections made by the scanner to the site, with details about the data fetched and the file types received.
- **Redirects:** Shows information on any identified HTTP and client-side redirects on the site.
- **Links:** Shows all the identified links outgoing from the site's homepage.
- **Behaviour:** Provides details of the variables and cookies found on the site. These may be useful in identifying the frameworks used in developing the site.
- **Indicators:** Lists all IPs, domains and hashes associated with the site. These indicators do not imply malicious activity related to the site.

https://github.com/user-attachments/assets/6b407e40-6966-432b-888a-5dbd0745e993

**Note:** Due to the dynamic nature of internet activities, data searched can produce different results on different days as new information gets updated.

## Abuse.ch

[Abuse.ch](https://abuse.ch/) is a research project hosted by the Institue for Cybersecurity and Engineering at the Bern University of Applied Sciences in Switzerland. It was developed to identify and track malware and botnets through several operational platforms developed under the project. These platforms are:

- **Malware Bazaar:**  A resource for sharing malware samples.
- **Feodo Tracker:**  A resource used to track botnet command and control (C2) infrastructure linked with Emotet, Dridex and TrickBot.
- **SSL Blacklist:**  A resource for collecting and providing a blocklist for malicious SSL certificates and JA3/JA3s fingerprints.
- **URL Haus:**  A resource for sharing malware distribution sites.
- **Threat Fox:**  A resource for sharing indicators of compromise (IOCs).
Let us look into these platforms individually.

### [MalwareBazaar](https://bazaar.abuse.ch/)
As the name suggests, this project is an all in one malware collection and analysis database. The project supports the following features:

- **Malware Samples Upload:** Security analysts can upload their malware samples for analysis and build the intelligence database. This can be done through the browser or an API.
- **Malware Hunting:** Hunting for malware samples is possible through setting up alerts to match various elements such as tags, signatures, YARA rules, ClamAV signatures and vendor detection.

https://github.com/user-attachments/assets/33c50d21-037d-4dc7-8612-f45a0a23ced5

### [FeodoTracker](https://feodotracker.abuse.ch/)
With this project, Abuse.ch is targeting to share intelligence on botnet Command & Control (C&C) servers associated with Dridex, Emotes (aka Heodo), TrickBot, QakBot and BazarLoader/BazarBackdoor. This is achieved by providing a database of the C&C servers that security analysts can search through and investigate any suspicious IP addresses they have come across. Additionally, they provide various IP and IOC blocklists and mitigation information to be used to prevent botnet infections.
![image](https://github.com/user-attachments/assets/1ae19db2-3587-465e-8e90-abe4b629e6b2)

### [SSL Blacklist](https://sslbl.abuse.ch/)
Abuse.ch developed this tool to identify and detect malicious SSL connections. From these connections, SSL certificates used by botnet C2 servers would be identified and updated on a denylist that is provided for use. The denylist is also used to identify JA3 fingerprints that would help detect and block malware botnet C2 communications on the TCP layer.

You can browse through the SSL certificates and JA3 fingerprints lists or download them to add to your deny list or threat hunting rulesets.

![image](https://github.com/user-attachments/assets/5dce89b7-80a4-4fee-bb1f-513d57af8c95)

### [URLhaus](about:blank)
As the name points out, this tool focuses on sharing malicious URLs used for malware distribution. As an analyst, you can search through the database for domains, URLs, hashes and filetypes that are suspected to be malicious and validate your investigations.

The tool also provides feeds associated with country, AS number and Top Level Domain that an analyst can generate based on specific search needs.

![image](https://github.com/user-attachments/assets/d103805a-7583-4ce1-924c-3683ea533d3a)

### [ThreatFox](https://threatfox.abuse.ch/)
With ThreatFox,  security analysts can search for, share and export indicators of compromise associated with malware. IOCs can be exported in various formats such as MISP events, Suricata IDS Ruleset, Domain Host files, DNS Response Policy Zone, JSON files and CSV files.

![image](https://github.com/user-attachments/assets/34672987-9867-4816-8e2a-14c3f0b4f0e3)

## PhishTool
### Email Phishing
Email phishing is one of the main precursors of any cyber attack. Unsuspecting users get duped into opening and accessing malicious files and links sent to them by email, as they appear to be legitimate. As a result, adversaries infect their victims’ systems with malware, harvesting their credentials and personal data and performing other actions such as financial fraud or conducting ransomware attacks.

[PhishTool](https://www.phishtool.com/) seeks to elevate the perception of phishing as a severe form of attack and provide a responsive means of email security. Through email analysis, security analysts can uncover email IOCs, prevent breaches and provide forensic reports that could be used in phishing containment and training engagements.

PhishTool has two accessible versions: **Community** and **Enterprise**. We shall mainly focus on the Community version and the core features in this task. Sign up for an account via this link to use the tool.

The core features include:

- **Perform email analysis:** PhishTool retrieves metadata from phishing emails and provides analysts with the relevant explanations and capabilities to follow the email’s actions, attachments, and URLs to triage the situation.
  
- **Heuristic intelligence:** OSINT is baked into the tool to provide analysts with the intelligence needed to stay ahead of persistent attacks and understand what TTPs were used to evade security controls and allow the adversary to social engineer a target.
  
- **Classification and reporting:** Phishing email classifications are conducted to allow analysts to take action quickly. Additionally, reports can be generated to provide a forensic record that can be shared.

Additional features are available on the Enterprise version:

- Manage user-reported phishing events.
- Report phishing email findings back to users and keep them engaged in the process.
- Email stack integration with Microsoft 365 and Google Workspace.
  
We are presented with an upload file screen from the Analysis tab on login. Here, we submit our email for analysis in the stated file formats. Other tabs include:

- **History:** Lists all submissions made with their resolutions.
- **In-tray:** An Enterprise feature used to receive and process phish reports posted by team members through integrating Google Workspace and Microsoft 365.

![image](https://github.com/user-attachments/assets/c1264675-1685-4920-97c1-96eebfbfb038)

## Cisco Talos Intelligence

IT and Cybersecurity companies collect massive amounts of information that could be used for threat analysis and intelligence. Being one of those companies, Cisco assembled a large team of security practitioners called Cisco Talos to provide actionable intelligence, visibility on indicators, and protection against emerging threats through data collected from their products. The solution is accessible as [Talos Intelligence](https://talosintelligence.com/).

Cisco Talos encompasses six key teams:

- **Threat Intelligence & Interdiction:** Quick correlation and tracking of threats provide a means to turn simple IOCs into context-rich intel.
- **Detection Research:** Vulnerability and malware analysis is performed to create rules and content for threat detection.
- **Engineering & Development:** Provides the maintenance support for the inspection engines and keeps them up-to-date to identify and triage emerging threats.
- **Vulnerability Research & Discovery:** Working with service and software vendors to develop repeatable means of identifying and reporting security vulnerabilities.
- **Communities:** Maintains the image of the team and the open-source solutions.
- **Global Outreach:** Disseminates intelligence to customers and the security community through publications.
- 
More information about Cisco Talos can be found on their [White Paper](https://www.talosintelligence.com/docs/Talos_WhitePaper.pdf)

### Talos Dashboard
Accessing the open-source solution, we are first presented with a reputation lookup dashboard with a world map. This map shows an overview of email traffic with indicators of whether the emails are legitimate, spam or malware across numerous countries. Clicking on any marker, we see more information associated with IP and hostname addresses, volume on the day and the type.

![image](https://github.com/user-attachments/assets/32e10a1d-30bb-4e75-9e36-8a3bc0c285de)

At the top, we have several tabs that provide different types of intelligence resources. The primary tabs that an analyst would interact with are:

- **Vulnerability Information:** Disclosed and zero-day vulnerability reports marked with CVE numbers and CVSS scores. Details of the vulnerabilities reported are provided when you select a specific report, including the timeline taken to get the report published. Microsoft vulnerability advisories are also provided, with the applicable snort rules that can be used

https://github.com/user-attachments/assets/9888ea4e-aa2e-4de4-a209-0a82171598a1

- **Reputation Center:** Provides access to searchable threat data related to IPs and files using their SHA256 hashes. Analysts would rely on these options to conduct their investigations. Additional email and spam data can be found under the **Email & Spam Data tab**.


https://github.com/user-attachments/assets/991ba781-0162-4f00-a438-b6b19b8b05c3

https://github.com/user-attachments/assets/2bef4d89-64de-4ccc-ab79-da20c1672dca


