# Introduction
![image](https://github.com/user-attachments/assets/6014a865-31ea-4498-b244-c42fb545a516)

Understanding the behaviours, objectives and methodologies of a cyber threat is a vital step to establishing a strong cybersecurity defence (known as a cybersecurity posture).

 UKC (Unified Kill Chain) framework is used to help understand how cyber attacks occur.

 # What is a "Kill Chain"

 ![image](https://github.com/user-attachments/assets/cb02b12c-e8cb-4f78-8ba3-b8d88ee51096)

 Originating from the military, a “Kill Chain” is a term used to explain the various stages of an attack. In the realm of cybersecurity, a “Kill Chain” is used to describe the methodology/path attackers such as hackers or APTs use to approach and intrude a target.

For example, an attacker scanning, exploiting a web vulnerability, and escalating privileges will be a “Kill Chain”. We will come to explain these stages in much further detail later in this room.

The objective is to understand an attacker's “Kill Chain” so that defensive measures can be put in place to either pre-emptively protect a system or disrupt an attacker's attempt.

# What is "Threat Modelling"

Threat modelling, in a cybersecurity context, is a series of steps to ultimately improve the security of a system. Threat modelling is about identifying risk and essentially boils down to:

1. Identifying what systems and applications need to be secured and what function they serve in the environment. For example, is the system critical to normal operations, and is a system holding sensitive information like payment info or addresses?
2. Assessing what vulnerabilities and weaknesses these systems and applications may have and how they could be potentially exploited
3. Creating a plan of action to secure these systems and applications from the vulnerabilities highlighted
4. Putting in policies to prevent these vulnerabilities from occurring again where possible (for example, implementing a software development life cycle (SDLC) for an application or training employees on phishing awareness).

![image](https://github.com/user-attachments/assets/ceeee802-3a31-4a4b-8119-5f7116716c38)

Threat modelling is an important procedure in reducing the risk within a system or application, as it creates a high-level overview of an organisation's IT assets (an asset in IT is a piece of software or hardware) and the procedures to resolve vulnerabilities.

The UKC can encourage threat modelling as the UKC framework helps identify potential attack surfaces and how these systems may be exploited.

STRIDE, DREAD and CVSS (to name a few) are all frameworks specifically used in threat modelling.

**STRIDE** (**S**poofing identity, **T**ampering with data, **R**epudiation threats, **I**nformation disclosure, **D**enial of Service and **E**levation of privileges) and PASTA (Process for Attack Simulation and Threat Analysis) infosec never tasted so good!. Let's detail STRIDE below. STRIDE, authored by two Microsoft security researchers in 1999 is still very relevant today. STRIDE includes six main principles, which I have detailed in the table below:

![image](https://github.com/user-attachments/assets/ebfacab8-02cb-4664-8983-f8a13e632d39)

# Introducing the Unified Kill Chain

![image](https://github.com/user-attachments/assets/0cfab372-fc3f-46a2-b924-daec0eb512c3)

To continue from the previous task, Paul Pols' [Unified Kill Chain](https://www.unifiedkillchain.com/assets/The-Unified-Kill-Chain.pdf), published in 2017, aims to complement (**not compete** with) other cybersecurity kill chain frameworks, such as Lockheed Martin’s and MITRE’s ATT&CK.

The UKC states that there are 18 phases to an attack: Everything from reconnaissance to data exfiltration and understanding an attacker's motive. These phases have been grouped together in this room into a few areas of focus for brevity, which will be detailed in the remaining tasks.

Some large benefits of the UKC over traditional cybersecurity kill chain frameworks include the fact that it is modern and extremely detailed (**reminder**: it has 18 phases officially, whereas other frameworks may have a small handful)

![image](https://github.com/user-attachments/assets/b4c54f33-e379-4056-8270-3bee2f454af2)

![image](https://github.com/user-attachments/assets/c1d2809a-5102-45b9-ac03-f771ed0304fe)

# Phase: In (Initial Foothold)

![image](https://github.com/user-attachments/assets/41b3a8f7-e5d4-49b8-8ad1-2fa710714df6)

﻿The main focus of this series of phases is for an attacker to gain access to a system or networked environment.

An attacker will employ numerous tactics to investigate the system for potential vulnerabilities that can be exploited to gain a foothold in the system. For example, a common tactic is the use of reconnaissance against a system to discover potential attack vectors (such as applications and services).

![image](https://github.com/user-attachments/assets/c28b85ea-fd7b-4596-92fb-ee969961a81b)

This series of phases also accommodates for an attacker creating a form of persistence (such as files or a process that allows the attacker to connect to the machine at any time). Finally, the UKC accounts for the fact that attackers will often use a combination of the tactics listed above.

We will explore the different phases of this section of the UKC in the headings below:

**Reconnaissance** ([MITRE Tactic TA0043](https://attack.mitre.org/tactics/TA0043/))

This phase of the UKC describes techniques that an adversary employs to gather information relating to their target. This can be achieved through means of passive and active reconnaissance. The information gathered during this phase is used all throughout the later stages of the UKC (such as the initial foothold).

Information gathered from this phase can include:

- Discovering what systems and services are running on the target, this is beneficial information in the weaponisation and exploitation phases of this section. 
- Finding contact lists or lists of employees that can be impersonated or used in either a social engineering or phishing attack.
- Looking for potential credentials that may be of use in later stages,  such as pivoting or initial access.
- Understanding the network topology and other networked systems can be used to pivot too. 

**Weaponization** ([MITRE Tactic TA0001)

This phase of the UKC describes the adversary setting up the necessary infrastructure to perform the attack. For example, this could be setting up a command and control server, or a system capable of catching reverse shells and delivering payloads to the system.

**Social Engineering** ([MITRE Tactic TA0001](https://attack.mitre.org/tactics/TA0001/)

This phase of the UKC describes techniques that an adversary can employ to manipulate employees to perform actions that will aid in the adversaries attack. For example, a social engineering attack could include:

- Getting a user to open a malicious attachment.
- Impersonating a web page and having the user enter their credentials.
- Calling or visiting the target and impersonating a user (for example, requesting a password reset) or being able to gain access to areas of a site that the attacker would not previously be -capable of (for example, impersonating a utility engineer).

**Exploitation** ([MITRE Tactic TA0002](https://attack.mitre.org/tactics/TA0002/))

This phase of the UKC describes how an attacker takes advantage of weaknesses or vulnerabilities present in a system. The UKC defines "Exploitation" as abuse of vulnerabilities to perform code execution. For example:

- Uploading and executing a reverse shell to a web application.
- Interfering with an automated script on the system to execute code.
- Abusing a web application vulnerability to execute code on the system it is running on.

**Persistence** ([MITRE Tactic TA0003](https://attack.mitre.org/tactics/TA0003/))

This phase of the UKC is rather short and simple. Specifically, this phase of the UKC describes the techniques an adversary uses to maintain access to a system they have gained an initial foothold on. For example:

- Creating a service on the target system that will allow the attacker to regain access.
- Adding the target system to a Command & Control server where commands can be executed remotely at any time.
- Leaving other forms of backdoors that execute when a certain action occurs on the system (i.e. a reverse shell will execute when a system administrator logs in).

**Defence Evasion** ([MITRE Tactic TA0005](https://attack.mitre.org/tactics/TA0005/))

The "Defence Evasion" section of the UKC is one of the more valuable phases of the UKC. This phase specifically is used to understand the techniques an adversary uses to evade defensive measures put in place in the system or network. For example, this could be:

- Web application firewalls.
- Network firewalls.
- Anti-virus systems on the target machine.
- Intrusion detection systems.

This phase is valuable when analysing an attack as it helps form a response and better yet - gives the defensive team information on how they can improve their defence systems in the future.

**Command & Control** ([MITRE Tactic TA0011](https://attack.mitre.org/tactics/TA0011/))

The "Command & Control" phase of the UKC combines the efforts an adversary made during the "Weaponization" stage of the UKC to establish communications between the adversary and target system.

An adversary can establish command and control of a target system to achieve its action on objectives. For example, the adversary can:

- Execute commands.
- Steal data, credentials and other information.
- Use the controlled server to pivot to other systems on the network.

**Pivoting** ([MITRE Tactic TA0008](https://attack.mitre.org/tactics/TA0008/))

"Pivoting" is the technique an adversary uses to reach other systems within a network that are not otherwise accessible (for example, they are not exposed to the internet). There are often many systems in a network that are not directly reachable and often contain valuable data or have weaker security.

For example, an adversary can gain access to a web server that is publically accessible to attack other systems that are within the same network (but are not accessible via the internet).
