# Introduction

An incident from a security perspective is "Any event or action, that has a negative consequence on the security of a user/computer or an organization is considered a security incident." Below are a few of the events that would negatively affect the environment when they occurred:

- Crashing the system
- Execution of an unwanted program
- Access to sensitive information from an unauthorized user
- A Website being defaced by the attacker
- The use of USB devices when there is a restriction in usage is against the company's policy

# Incident Handling - Life Cycle

**Incident Handling Life Cycle**

![image](https://github.com/user-attachments/assets/4dcf12f4-b36d-4310-9732-ad907619a561)

As an Incident Handler / SOC Analyst, we would aim to know the attackers' tactics, techniques, and procedures. Then we can stop/defend/prevent against the attack in a better way. The Incident Handling process is divided into four different phases. Let's briefly go through each phase before jumping into the incident, which we will be going through in this exercise.


1. **Preparation**

The preparation phase covers the readiness of an organization against an attack. That means documenting the requirements, defining the policies, incorporating the security controls to monitor like EDR / SIEM / IDS / IPS, etc. It also includes hiring/training the staff.

2. **Detection and Analysis**

The detection phase covers everything related to detecting an incident and the analysis process of the incident. This phase covers getting alerts from the security controls like SIEM/EDR investigating the alert to find the root cause. This phase also covers hunting for the unknown threat within the organization.

3. **Containment, Eradication, and Recovery**

This phase covers the actions needed to prevent the incident from spreading and securing the network. It involves steps taken to avoid an attack from spreading into the network, isolating the infected host, clearing the network from the infection traces, and gaining control back from the attack.

4. **Post-Incident Activity / Lessons Learnt**
This phase includes identifying the loopholes in the organization's security posture, which led to an intrusion, and improving so that the attack does not happen next time. The steps involve identifying weaknesses that led to the attack, adding detection rules so that similar breach does not happen again, and most importantly, training the staff if required.

# Incident Handling: Scenario

In this exercise, we will investigate a cyber attack in which the attacker defaced an organization's website. This organization has Splunk as a SIEM solution setup. Our task as a Security Analysis would be to investigate this cyber attack and map the attacker's activities into all 7 of the Cyber Kill Chain Phases. It is important to note that we don't need to follow the sequence of the cyber kill chain during the Investigation. One finding in one phase will lead to another finding that may have mapped into some other phase.

## Cyber Kill Chain

![image](https://github.com/user-attachments/assets/56e4feb8-4fea-40aa-91c1-854d3174882b)

We will follow the Cyber kill Chain Model and map the attacker's activity in each phase during this Investigation. When required, we will also utilize Open Source Intelligence (OSINT) and other findings to fill the gaps in the kill chain. It is not necessary to follow this sequence of the phases while investigating.

- Reconnaissance
- Weaponization
- Delivery
- Exploitation
- Installation
- Command & Control
- Actions on Objectives

## Splunk

During our investigation, we will be using **Splunk** as our SIEM solution. Logs are being ingested from webserver/firewall/Suricata/Sysmon etc. In the data summary tab, we can explore the log sources showing visibility into both network-centric and host-centric activities. To get the complete picture of the hosts and log sources being monitored in an organization, please click on the **Data summary** and navigate the available tabs to get the information.

https://github.com/user-attachments/assets/dbe92fe6-7230-4fc4-8617-2e86510910cd

### Interesting log Sources
Some of the interesting log sources that will help us in our Investigation are:

![image](https://github.com/user-attachments/assets/eb29807e-7f98-4251-9702-370897094884)

