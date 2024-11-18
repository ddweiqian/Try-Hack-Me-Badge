
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

