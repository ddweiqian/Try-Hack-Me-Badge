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



