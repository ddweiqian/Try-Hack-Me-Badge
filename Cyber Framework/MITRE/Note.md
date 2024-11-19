# Introduction to MITRE

For those new to cybersecurity, MITRE(MITRE Adversarial Tactics, Techniques, and Common Knowledge (ATT&CK)) might not be familiar. Even experienced professionals might primarily recognize MITRE for its CVEs ([Common Vulnerabilities and Exposures](https://cve.mitre.org/)) list, a key resource for identifying exploits for specific vulnerabilities. However, MITRE's research spans various fields beyond cybersecurity, all aimed at enhancing the safety, stability, and well-being of our nation. These fields include artificial intelligence, health informatics, and space security, among others.

According to [Mitre.org](https://www.mitre.org/who-we-are): "At MITRE, we solve problems for a safer world. Through our federally funded R&D centers and public-private partnerships, we work across government to tackle challenges to the safety, stability, and well-being of our nation."

In this discussion, we will focus on other initiatives and research by the U.S.-based non-profit MITRE Corporation that benefit the cybersecurity community, specifically:

ATT&CK® (**A**dversarial **T**actics, **T**echniques, and **C**ommon **K**nowledge) Framework

CAR (**C**yber **A**nalytics **R**epository) Knowledge Base

ENGAGE (not an acronym)

D3FEND (**D**etection, **D**enial, and **D**isruption **F**ramework **E**mpowering **N**etwork **D**efense)

AEP (**A**TT&CK **E**mulation **P**lans)

# Basic Terminology

Let's take a moment to go over some common terms you'll encounter when dealing with frameworks and threat intelligence.

**APT** stands for **Advanced Persistent Threat**. This term refers to a team, group, or even a nation-state that conducts prolonged attacks against organizations or countries. The word "advanced" might be misleading, suggesting that these groups possess some kind of super-weapon like a zero-day exploit. However, this is not the case. As we'll discuss later, the techniques used by APT groups are often quite common and can be detected with the proper measures in place. 

An advanced persistent threat (APT) is a stealthy threat actor, typically a nation state or state-sponsored group, which gains unauthorized access to a computer network and remains undetected for an extended period.

TTP stands for **Tactics, Techniques, and Procedures**. Here's what each term means:

**Tactic**: The goal or objective of the adversary.

**Technique**: The method the adversary uses to achieve the goal or objective.

**Procedure**: The way the technique is carried out.

# ATT&CK® Framework

The [ATT&CK®](https://attack.mitre.org/) framework is a comprehensive knowledge base of adversary tactics and techniques that is globally accessible and based on real-world observations. It was created by MITRE in 2013 to document common TTPs (**Tactics, Techniques, and Procedures**) used by APT (**Advanced Persistent Threat**) groups targeting enterprise Windows networks. This initiative began with an internal project known as FMX (Fort Meade Experiment), where security professionals emulated adversarial TTPs on a network and collected data from the attacks. This data formed the foundation of the ATT&CK® framework.

Over the years, the framework has expanded significantly. Originally focused on Windows, it now includes other platforms like macOS and Linux. The framework is continually enriched by contributions from security researchers and threat intelligence reports. It's a valuable tool for both blue teamers (defensive security) and red teamers (offensive security).

For more detailed information, visit the [ATT&CK®](https://attack.mitre.org/) website.

Please reference [this](https://www.techtarget.com/searchsecurity/definition/MITRE-ATTCK-framework) for more information about MITRE ATT&CK.

Finally, the same data can be accessed through the **MITRE ATT&CK® Navigator**. *This tool is designed to facilitate basic navigation and annotation of ATT&CK® matrices, similar to what users might already be doing in tools like Excel. The Navigator is created to be straightforward and adaptable, allowing you to visualize various aspects such as defensive coverage, red/blue team planning, the frequency of detected techniques, and more*.

You can access the Navigator view when exploring a group or tool page by clicking the ATT&CK® Navigator Layers button.
![image](https://github.com/user-attachments/assets/40527db0-50c9-4dca-9e75-89d5cbc18da2)

You can visit [its repository](https://github.com/mitre-attack/attack-navigator/) for more about **MITRE ATT&CK® Navigator**

Apart from MITRE ATT&CK® Navigator, here is more about [ATT&CK Data & Tools](https://attack.mitre.org/resources/attack-data-and-tools/), including **Python Utilities** provided by ATT&CK.

Learn more about **use case of MITRE ATT&CK** from its [CTI Training](https://attack.mitre.org/resources/learn-more-about-attack/training/cti/), including advanced topics such as **how to map intelligence generated from narrative reporting about an incident to ATT&CK**, so that to users can leverage threat intelligence and threat-informed defense.

# CAR Knowledge Base

[Cyber Analytics Repository](https://car.mitre.org/)

The official definition of CAR is *"The MITRE Cyber Analytics Repository (CAR) is a knowledge base of analytics developed by MITRE based on the MITRE ATT&CK® adversary model. CAR defines a data model that is leveraged in its pseudocode representations but also includes implementations directly targeted at specific tools (e.g., Splunk, EQL) in its analytics. With respect to coverage, CAR is focused on providing a set of validated and well-explained analytics, in particular with regards to their operating theory and rationale."*

Rather than continuing to explain what CAR (Cyber Analytics Repository) is, let's jump right in. With the knowledge we've gained from the previous section, we should now be ready to understand the information that CAR provides.

Let's start by examining [CAR-2013-10-001](https://car.mitre.org/analytics/CAR-2013-10-001/): User Login Activity Monitoring.

When you visit the page, you'll find a brief description of the analytics along with references to ATT&CK, including the related **technique, sub-technique**, and **tactic**.

![image](https://github.com/user-attachments/assets/6446635d-deb4-44eb-8117-9da73f2cb59b)

We are also given pseudocode and a query to search for this specific analytic in Splunk. Pseudocode is a straightforward, human-readable description of a set of instructions or algorithms that a program or system will execute.

![image](https://github.com/user-attachments/assets/51590591-7f96-4797-affe-d9dafdf381d1)

To take full advantage of CAR, we can view the [Full Analytic List](https://car.mitre.org/analytics/) or the [CAR ATT&CK® Navigator layer](https://mitre-attack.github.io/attack-navigator/#layerURL=https://raw.githubusercontent.com/mitre-attack/car/master/docs/coverage/car_analytic_coverage_04_05_2022.json) to view all the analytics.

![image](https://github.com/user-attachments/assets/0fb7d64b-e47a-4ac5-b568-69be4ed93f72)

In the Full Analytic List view, you can quickly identify which implementations are available for each analytic and see the applicable OS platform at a glance.

![image](https://github.com/user-attachments/assets/b56e516b-d3e6-4eba-94d4-b27d20df318f)

Let's look at another analytic to see a different implementation, [CAR-2014-11-004: Remote PowerShell Sessions](https://car.mitre.org/analytics/CAR-2014-11-004/).

Under Implementations, a pseudocode is provided and an EQL version of the pseudocode. EQL (pronounced as 'equal'), and it's an acronym for Event Query Language. EQL can be utilized to query, parse, and organize Sysmon event data. You can read more about this [here](https://eql.readthedocs.io/en/latest/). 
![image](https://github.com/user-attachments/assets/77534e9f-cb3c-409f-9821-fdc867796e57)

To summarize, CAR is a great place for finding analytics that takes us further than the Mitigation and Detection summaries in the ATT&CK® framework. This tool is not a replacement for ATT&CK® but an added resource.

# MITRE ENGAGE

Per the website, "**MITRE Engage** *is a framework for planning and discussing adversary engagement operations that empowers you to engage your adversaries and achieve your cybersecurity goals*."

MITRE Engage is considered an **Adversary Engagement Approach**. This is accomplished by the implementation of **Cyber Denial** and **Cyber Deception**. 

With **Cyber Denial** we prevent the adversary's ability to conduct their operations and with **Cyber Deception** we intentionally plant artifacts to mislead the adversary. 

The Engage website provides a [starter kit](https://engage.mitre.org/starter-kit/) to get you 'started' with the Adversary Engagement Approach. The starter kit is a collection of whitepapers and PDFs explaining various checklists, methodologies, and processes to get you started. 

As with MITRE ATT&CK, Engage has its own matrix. Below is a visual of the **Engage Matrix**(Source: https://engage.mitre.org).

![image](https://github.com/user-attachments/assets/2b06a389-dfd8-43a2-aee9-62185455edeb)

Let's quickly explain each of these categories based on the information on the Engage website.
- **Prepare** the set of operational actions that will lead to your desired outcome (input)
- **Expose** adversaries when they trigger your deployed deception activities 
- **Affect** adversaries by performing actions that will have a negative impact on their operations
- **Elicit** information by observing the adversary and learn more about their modus operandi (TTPs)
- **Understand** the outcomes of the operational actions (output) 

Refer to the [Engage Handbook](https://engage.mitre.org/wp-content/uploads/2022/04/EngageHandbook-v1.0.pdf) to learn more. 

You can interact with the [Engage Matrix Explorer](https://engage.mitre.org/matrix/). We can filter by information from [MITRE ATT&CK](https://attack.mitre.org/). 

Note that by default the matrix focuses on Operate, which entails Expose, Affect, and Elicit. 

![image](https://github.com/user-attachments/assets/dc917659-638d-4faa-a1f2-bc435ab3f33e)

You can click on **Prepare** or **Understand** if you wish to focus solely on that part of the matrix.
https://github.com/user-attachments/assets/d0facb8b-509c-4e4a-b564-f6bf5bbcd7e7

# MITRE D3FEND
[D3FEND](https://d3fend.mitre.org/)

What is this MITRE resource? Per the [D3FEND](https://d3fend.mitre.org/) website, this resource is "*A knowledge graph of cybersecurity countermeasures*."

D3FEND is still in beta and is funded by the Cybersecurity Directorate of the NSA. 

**D3FEND** stands for **D**etection, **D**enial, and **D**isruption **F**ramework **E**mpowering **N**etwork **D**efense. 

At the time of this writing, there are 408 artifacts in the D3FEND matrix. See the below image.

![image](https://github.com/user-attachments/assets/87a45525-086a-4aff-8a97-0bbacefd05b4)

As you can see, you're provided with information on what is the technique (**definition**), how the technique works (**how it works**), things to think about when implementing the technique (**considerations**), and how to utilize the technique (**example**).

Note, as with other MITRE resources, you can filter based on the ATT&CK matrix. 

Since this resource is in beta and will change significantly in future releases, we won't spend that much time on D3FEND. 

The objective of this task is to make you aware of this MITRE resource and hopefully you'll keep an eye on it as it matures in the future. 

# ATT&CK® Emulation Plans

If these tools provided to us by MITRE are not enough, under **MITRE ENGENUITY**, we have **CTID**, the **Adversary Emulation Library**, and **ATT&CK® Emulation Plans**.

## CTID

MITRE formed an organization named The [Center of Threat-Informed Defense](https://mitre-engenuity.org/cybersecurity/center-for-threat-informed-defense/) **(CTID)**. This organization consists of various companies and vendors from around the globe. Their objective is to conduct research on cyber threats and their TTPs and share this research to improve cyber defense for all. 

Some of the companies and vendors who are participants of CTID:

- AttackIQ (founder)
- Verizon
- Microsoft (founder)
- Red Canary (founder)
- Splunk
Per the website, "*Together with Participant organizations, we cultivate solutions for a safer world and advance threat-informed defense with open-source software, methodologies, and frameworks. By expanding upon the MITRE ATT&CK knowledge base, our work expands the global understanding of cyber adversaries and their tradecraft with the public release of data sets critical to better understanding adversarial behavior and their movements*."

**Adversary Emulation Library & ATT&CK® Emulations Plans**

The [Adversary Emulation Library](https://medium.com/mitre-engenuity/introducing-the-all-new-adversary-emulation-plan-library-234b1d543f6b) is a public library making adversary emulation plans a free resource for blue/red teamers. The library and the emulations are a contribution from CTID. There are several[ATT&CK® Emulation Plans](https://github.com/center-for-threat-informed-defense/adversary_emulation_library) currently available: [APT3](https://attack.mitre.org/resources/adversary-emulation-plans/), [APT29](https://github.com/center-for-threat-informed-defense/adversary_emulation_library/tree/master/apt29), and [FIN6](https://github.com/center-for-threat-informed-defense/adversary_emulation_library/tree/master/fin6). The emulation plans are a step-by-step guide on how to mimic the specific threat group. If any of the C-Suite were to ask, "how would we fare if APT29 hits us?" This can easily be answered by referring to the results of the execution of the emulation plan. 

# ATT&CK® and Threat Intelligence

**Threat Intelligence (TI)** or **Cyber Threat Intelligence (CTI)** is the information, or TTPs, attributed to the adversary. By using threat intelligence, as defenders, we can make better decisions regarding the defensive strategy. Large corporations might have an in-house team whose primary objective is to gather threat intelligence for other teams within the organization, aside from using threat intel already readily available. Some of this threat intel can be open source or through a subscription with a vendor, such as [CrowdStrike](https://www.crowdstrike.com/en-us/). In contrast, many defenders wear multiple hats (roles) within some organizations, and they need to take time from their other tasks to focus on threat intelligence. To cater to the latter, we'll work on a scenario of using ATT&CK® for threat intelligence. The goal of threat intelligence is to make the information actionable. 


# Conclusion

we explored tools/resources that MITRE has provided to the security community. The room's goal was to expose you to these resources and give you a foundational knowledge of their uses. Many vendors of security products and security teams across the globe consider these contributions from MITRE invaluable in the day-to-day efforts to thwart evil. The more information we have as defenders, the better we are equipped to fight back. Some of you might be looking to transition to become a SOC analyst, detection engineer, cyber threat analyst, etc. these tools/resources are a must to know.

As mentioned before, though, this is not only for defenders. As red teamers, these tools/resources are useful as well. Your objective is to mimic the adversary and attempt to bypass all the controls in place within the environment. With these resources, as the red teamer, you can effectively mimic a true adversary and communicate your findings in a common language that both sides can understand. In a nutshell, this is known as **purple teaming**.  
