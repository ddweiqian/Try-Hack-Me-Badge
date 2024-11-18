
# What is SIEM
A SIEM (**Security Information and Event Management**) system is a tool that gathers data from multiple endpoints and network devices within a network. It then centralizes and correlates this data for analysis.

# Network Visibility through SIEM

Before delving into the significance of SIEM, it’s essential to comprehend why having enhanced visibility over all network activities is crucial. The diagram below illustrates a basic network setup, including multiple Linux/Windows endpoints, a data server, and a website. Each component interacts with others or accesses the internet via a router.

![image](https://github.com/user-attachments/assets/922d7aa2-1241-41ec-b79e-f04e2df6fc66)

As we know, each network component can generate various logs through different log sources. For instance, using Sysmon alongside Windows Event logs can improve visibility into Windows endpoints. Network log sources can be categorized into two main types:

## Host-Centric Log Sources
These capture events occurring within or related to the host. Examples of host-centric log sources include Windows Event logs, Sysmon, and Osquery. Some examples of host-centric logs are:

- A user accessing a file

- A user attempting to authenticate

- A process execution activity

- A process adding, editing, or deleting a registry key or value

- PowerShell execution*

## Network-Centric Log Sources
These logs are generated when hosts communicate with each other or access the internet. Some network-based protocols include SSH, VPN, HTTP/S, and FTP. Examples of network-centric logs are:

- SSH connections

- Files being accessed via FTP

- Web traffic

- Users accessing company resources through VPN

- Network file sharing activity

## The Importance of SIEM
Now that we've discussed different types of logs, let's explore why SIEM is crucial. With numerous devices generating hundreds of events per second, examining logs on each device individually during an incident can be extremely laborious. Here’s where a SIEM solution proves advantageous. It collects logs from various sources in real-time, correlates events, enables log searches, investigates incidents, and provides rapid responses. Key features of SIEM include:
![image](https://github.com/user-attachments/assets/48a36442-761a-4bb7-9bf0-59d5b2bfb528)

- Real-time log ingestion

- Alerts for abnormal activities

- 24/7 monitoring and visibility

- Early threat detection and protection

- Data insights and visualization

- Ability to investigate past incidents
