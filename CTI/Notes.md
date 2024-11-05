Cyber Threat Intelligence(CTI) is evidence-based knowledge about adversaries, including their indicators, tactics, motivations, and actionable advice against them.

# CTI
## 1. Understanding and Using Data, Information, and Intelligence in CTI
### Data Collection: 
Begin by collecting discrete data points (like IP addresses, URLs, and file hashes) from sources such as your firewall logs, server activity, and network traffic. This data will later be used to identify and verify specific threats.
### Building Information: 
Combine multiple data points to create information by identifying activities or patterns that indicate a potential threat. For example, tracking how often an unusual IP range tries to access your network can help you analyze access patterns.
### Generating Intelligence: 
Correlate data and information to extract insights. For instance, if the same IP shows repeated access attempts alongside unauthorized login attempts, you might recognize a pattern of suspicious behavior that indicates a possible brute-force attack.

## 2. Applying CTI to Protect Assets and Inform Decision-Making
>> Use CTI findings to 
### prioritize critical assets 
by assessing which systems are most vulnerable or likely to be targeted, helping you allocate resources for protection more effectively.
>> ### Provide actionable insights to decision-makers 
on high-risk areas. For example, if intelligence shows an increase in phishing attacks in your sector, this information could justify investments in anti-phishing solutions and user training.
>> Use intelligence reports to shape 
### security awareness programs 
and training for employees, emphasizing identified vulnerabilities or common attack techniques.

## 3. Key Questions to Develop Threat Context
### Identify Adversaries and Motives:
Analyze intelligence to understand who your likely attackers are (e.g., competitors, hacktivists, cybercriminal groups) and their possible motivations (e.g., financial gain, sabotage).
### Capabilities: 
Look for patterns in the tactics used by past adversaries to gauge their technical capabilities and the level of threat they pose.
### Indicators of Compromise (IOCs): 
Define a set of IOCs (such as specific file signatures or network behaviors) to help your team detect signs of compromise early.

## 4. Source-Based Threat Intelligence Gathering
### Internal Sources: 
Leverage system logs, incident reports, and vulnerability assessment results to understand current security posture and identify recurring issues.
### Community Sources: 
Participate in open forums and dark web monitoring to gain insights into new threats and how other organizations respond to them.
### External Sources: 
Use threat intelligence feeds (both commercial and open-source) to stay informed about global cyber threats and any specific vulnerabilities impacting similar organizations.

## 5. Applying Threat Intelligence Classifications in Practice
### Strategic Intelligence: 
Use strategic reports to guide long-term security investments and inform upper management of the organization’s risk landscape. This might involve identifying trends (e.g., increased ransomware attacks) that could shape company policies and cybersecurity budget allocations.
### Technical Intelligence: 
Analyze artefacts such as malicious code or phishing emails to understand the technical details of attacks and create specific defensive measures.
### Tactical Intelligence: 
Monitor TTPs to refine real-time response strategies. For example, if an attack uses a specific exploit or phishing method, tactical intel helps adjust defenses to counter similar attacks immediately.
Operational Intelligence: Investigate adversaries’ intent and potential targets within your environment. Use this intelligence to prioritize protections around the most critical assets, ensuring that key systems, data, and processes have adequate safeguards.
# CTI Lifecycle
<img src= "https://github.com/user-attachments/assets/aa58ea8b-49f2-4d54-8b36-d9a0bf60f1c7" alt="image" width="500" height="300">

## 01 Direction
### Set Objectives: 
Define key goals, identifying critical assets, potential impacts of their loss, data sources, and necessary tools/resources.
### Investigation Scope:
Establish focus areas and incident-related questions for further inquiry.
## 02 Collection

### Data Gathering: 
Collect relevant data from commercial, private, and open-source resources. Automate the process to manage high data volumes and enhance efficiency.
## 03 Processing

### Data Structuring: 
Organize raw logs, vulnerability details, and network data into a consistent, visual format. Use SIEM tools for quick parsing and tagging to support analysis.
## 04 Analysis
### Insight Development:
Derive actionable insights by identifying indicators, patterns, and attack tactics. Decide on action plans, defensive measures, and potential resource needs.
## 05 Dissemination 
### Tailored Reporting: 
Share findings with stakeholders in suitable formats:
#### Executives:
Strategic reports with trends, financial impacts, and recommendations.
#### Technical Teams: Detailed threat indicators, tactics, techniques, and procedures (TTPs).
## 06 Feedback
### Continuous Improvement: 
Use stakeholder feedback to refine threat intel processes, enhancing accuracy and responsiveness in future cycles.

# CTI Standards & Frameworks
