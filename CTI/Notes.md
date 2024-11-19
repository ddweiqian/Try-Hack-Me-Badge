Cyber Threat Intelligence(CTI) is evidence-based knowledge about adversaries, including their indicators, tactics, motivations, and actionable advice against them.

# Cyber Threat Intelligence
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
