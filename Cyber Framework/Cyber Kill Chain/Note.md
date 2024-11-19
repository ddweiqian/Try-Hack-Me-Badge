# Introduction
![image](https://github.com/user-attachments/assets/23b2720a-ffb2-4edd-b4e3-51288206f1d1)

The term **kill chain** is a military concept related to the structure of an attack. It consists of target identification, decision and order to attack the target, and finally the target destruction.

Thanks to Lockheed Martin, a global security and aerospace company, that established the Cyber Kill Chain® framework for the cybersecurity industry in 2011 based on the military concept. The framework defines the steps used by adversaries or malicious actors in cyberspace. To succeed, an adversary needs to go through all phases of the Kill Chain. We will go through the attack phases and help you better understand adversaries and their techniques used in the attack to defend yourself.

So, why is it important to understand how Cyber Kill Chain works? 

The Cyber Kill Chain will help you understand and protect against ransomware attacks, security breaches as well as Advanced Persistent Threats (APTs). You can use the Cyber Kill Chain to assess your network and system security by identifying missing security controls and closing certain security gaps based on your company's infrastructure.

By understanding the Kill Chain as a SOC Analyst, Security Researcher, Threat Hunter, or Incident Responder, you will be able to recognize the intrusion attempts and understand the intruder's goals and objectives. 

We will be exploring the following attack phases:

- Reconnaissance
- Weaponization
- Delivery
- Exploitation
- Installation
- Command & Control
- Actions on Objectives 

# Reconnaissance

![image](https://github.com/user-attachments/assets/5426e71b-7ea9-4e6f-b783-726deecbc821)

To learn what reconnaissance is from the attacker's perspective, first, let's define the term reconnaissance. 

**Reconnaissance** is discovering and collecting information on the system and the victim. The reconnaissance phase is the planning phase for the adversaries.

**OSINT** (Open-Source Intelligence) also falls under reconnaissance. OSINT is the first step an attacker needs to complete to carry out the further phases of an attack. The attacker needs to study the victim by collecting every available piece of information on the company and its employees, such as the company's size, email addresses, phone numbers from publicly available resources to determine the best target for the attack. 

You can also find out more about OSINT from this Varonis article, ["What is OSINT?"](https://www.varonis.com/blog/what-is-osint)

Let's look at it from the attacker's perspective, who initially doesn't know what company he wants to attack. 

Here is the scenario: A malicious attacker who names himself "Megatron" decides to conduct a very sophisticated attack that he has been planning out for years; he has been studying and researching different tools and techniques that could help him get to the last phase of the Cyber Kill Chain. But first, he needs to start from the Reconnaissance phase.

In order to operate in this phase, the attacker would need to conduct OSINT.  Let's have a look at Email harvesting.


Email harvesting is the process of obtaining email addressesfrom public, paid, or free services. An attacker can use email-address harvesting for a **phishing attack** (a type of social-engineering attack used to steal sensitive data, including login credentials and credit card numbers). The attacker will have a big arsenal of tools available for reconnaissance purposes. Here are some of them:

- [theHarvester](https://github.com/laramies/theHarvester) - other than gathering emails, this tool is also capable of gathering names, subdomains, IPs, and URLs using multiple public data sources 
- [Hunter.io](https://hunter.io/) - this is  an email hunting tool that will let you obtain contact information associated with the domain
- [OSINT Framework](https://osintframework.com/) - OSINT Framework provides the collection of OSINT tools based on various categories

An attacker would also use social media websites such as LinkedIn, Facebook, Twitter, and Instagram to collect information on a specific victim he would want to attack or the company. The information found on social media can be beneficial for an attacker to conduct a phishing attack.

# Weaponization

![image](https://github.com/user-attachments/assets/638f7632-b889-41f9-9543-d009c93c431d)

After a successful reconnaissance stage, "Megatron" would work on crafting a "weapon of destruction". He would prefer not to interact with the victim directly and, instead, he will create a "weaponizer" that, according to Lockheed Martin, combines **malware** and **exploit** into a deliverable **payload**. Most attackers usually use automated tools to generate the malware or refer to the [DarkWeb](https://www.kaspersky.com/resource-center/threats/deep-web) to purchase the malware. More sophisticated actors or nation-sponsored APT (Advanced Persistent Threat Groups) would write their custom malware to make the malware sample unique and evade detection on the target.

Let's first define some terminology before we analyze the Weaponization phase.

**Malware** is a program or software that is designed to damage, disrupt, or gain unauthorized access to a computer.

An **exploit** is a program or a code that takes advantage of the vulnerability or flaw in the application or system.

A **payload** is a malicious code that the attacker runs on the system.

Continuing with our adversary, "Megatron" chooses...

"Megatron" chooses to buy an already written payload from someone else in the DarkWeb, so that he can spend more time on the other phases. 

In the Weaponization phase, the attacker would:

- Create an infected Microsoft Office document containing a malicious macro or VBA (Visual Basic for Applications) scripts. If you want to learn about macro and VBA, please refer to the article ["Intro to Macros and VBA For Script Kiddies" by TrustedSec](https://www.trustedsec.com/blog/intro-to-macros-and-vba-for-script-kiddies).
- An attacker can create a malicious payload or a very sophisticated worm, implant it on the USB drives, and then distribute them in public. An example of the virus. 
- An attacker would choose Command and Control (C2) techniques for executing the commands on the victim's machine or deliver more payloads. You can read more about the C2 techniques on [MITRE ATT&CK](https://attack.mitre.org/tactics/TA0011/).
- An attacker would select a **backdoor** implant (the way to access the computer system, which includes bypassing the security mechanisms).
