
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

# Log Sources and Log Ingestion

Every network device generates logs whenever activities occur, such as a user visiting a website, connecting to SSH, or logging into their workstation. Below, we'll discuss some common devices found in a network environment:

## Windows Machine

Windows logs every event, which can be accessed via the Event Viewer utility. Each log activity is assigned a unique ID, simplifying the analyst's task of examining and tracking them. To view events, simply type **Event Viewer** in the search bar, and it will open the tool where various logs are stored and can be reviewed. These logs from all Windows endpoints are then sent to the SIEM solution for enhanced monitoring and visibility.

[![Overview of Event Viewer in Windows Server]((https://img.youtube.com/vi/KXrwAmoJ_2I&t=146s/hqdefault.jpg)])](https://www.youtube.com/watch?v=KXrwAmoJ_2I&t=146s)

## Linux Workstation

Linux OS stores all the related logs, such as events, errors, warnings, etc. Which are then ingested into SIEM for continuous monitoring. Some of the common locations where Linux store logs are:

- **/var/log/httpd** : Contains HTTP Request  / Response and error logs.
- **/var/log/cron** : Events related to cron jobs are stored in this location.
- **/var/log/auth.log and /var/log/secure** : Stores authentication related logs.
- **/var/log/kern** : This file stores kernel related events.

  Here is a sample of a cron log:

![image](https://github.com/user-attachments/assets/0144fb00-f3c3-4034-9735-e785cbe897cb)

## Web Server

It is important to keep an eye on all the requests/responses coming in and out of the webserver for any potential web attack attempt. In Linux, common locations to write all apache related logs are **/var/log/apache** or **/var/log/httpd**

Here is an example of Apache Logs:

![image](https://github.com/user-attachments/assets/c6133336-7561-4a69-8825-4004c36cd9b3)

## Log IngestionShows Log Ingestion in SIEM

![image](https://github.com/user-attachments/assets/8cf4add3-2f62-46ea-b8f3-732f452c8b72)

All these logs provide a wealth of information and can help in identifying security issues. Each SIEM solution has its own way of ingesting the logs. Some common methods used by these SIEM solutions are explained below:

1) **Agent / Forwarder:** These SIEM solutions provide a lightweight tool called an agent (forwarder by Splunk) that gets installed in the Endpoint. It is configured to capture all the important logs and send them to the SIEM server.

2) **Syslog:** Syslog is a widely used protocol to collect data from various systems like web servers, databases, etc., are sent real-time data to the centralized destination.

3) **Manual Upload:** Some SIEM solutions, like Splunk, ELK, etc., allow users to ingest offline data for quick analysis. Once the data is ingested, it is normalized and made available for analysis.

4) **Port-Forwarding:** SIEM solutions can also be configured to listen on a certain port, and then the endpoints forward the data to the SIEM instance on the listening port.

![image](https://github.com/user-attachments/assets/d1061b8c-eff4-40b6-b47b-a0054c9072da)

# Why SIEM?

SIEM is used to provide correlation on the collected data to detect threats. Once a threat is detected, or a certain threshold is crossed, an alert is raised. This alert enables the analysts to take suitable actions based on the investigation. SIEM plays an important role in the Cyber Security domain and helps detect and protect against the latest threats in a timely manner. It provides good visibility of what's happening within the network infrastructure.

## SIEM Capabilities
SIEM is one major component of a Security Operations Center (SOC) ecosystem, as illustrated below. SIEM starts by collecting logs and examining if any event/flow has matched the condition set in the rule or crossed a certain threshold

Some of the common capabilities of SIEM are:

- Correlation between events from different log sources.
- Provide visibility on both Host-centric and Network-centric activities.
- Allow analysts to investigate the latest threats and timely responses.
- Hunt for threats that are not detected by the rules in place.

![image](https://github.com/user-attachments/assets/6eb8ff50-f9b2-416b-b8ce-b1b58ebae86d)

## SOC Analyst Responsibilities

SOC Analysts utilize SIEM solutions in order to have better visibility of what is happening within the network. Some of their responsibilities include:

- Monitoring and Investigating.
- Identifying False positives.
- Tuning Rules which are causing the noise or False positives.
- Reporting and Compliance.
- Identifying blind spots in the network visibility and covering them.

# Analysing Logs and Alerts

SIEM tool gets all the security-related logs ingested through agents, port forwarding, etc. Once the logs are ingested, SIEM looks for unwanted behavior or suspicious pattern within the logs with the help of the conditions set in the rules by the analysts. If the condition is met, a rule gets triggered, and the incident is investigated.

## Dashboard

Dashboards are the most important components of any SIEM. SIEM presents the data for analysis after being normalized and ingested. The summary of these analyses is presented in the form of actionable insights with the help of multiple dashboards. Each SIEM solution comes with some default dashboards and provides an option for custom Dashboard creation. Some of the information that can be found in a dashboard are:

- Alert Highlights
- System Notification
- Health Alert
- List of Failed Login Attempts
- Events Ingested Count
- Rules triggered
- Top Domains Visited
- An example of a Default dashboard in Qradar SIEM is shown below:

![image](https://github.com/user-attachments/assets/9c4910d2-3445-4113-a4bc-0936a27ef322)

## Correlation Rules

Correlation rules play an important role in the timely detection of threats allowing analysts to take action on time. Correlation rules are pretty much logical expressions set to be triggered. A few examples of correlation rules are:

- If a User gets 5 failed Login Attempts in 10 seconds - Raise an alert for **Multiple Failed Login Attempts**
- If login is successful after multiple failed login attempts - Raise an alert for **Successful Login After multiple Login Attempts**
- A rule is set to alert every time a user plugs in a USB (Useful if USB is restricted as per the company policy)
- If outbound traffic is > 25 MB - Raise an alert to potential Data exfiltration Attempt (Usually, it depends on the company policy)

## How a correlation rule is created

To explain how the rule works, consider the following Eventlog use cases:

**Use-Case 1**:

Adversaries tend to remove the logs during the post-exploitation phase to remove their tracks. A unique Event ID **104** is logged every time a user tries to remove or clear event logs. To create a rule based on this activity, we can set the condition as follows:

**Rule**: If the Log source is WinEventLog **AND** EventID is **104** - Trigger an **alert Event Log Cleared**

**Use-Case 2**: Adversaries use commands like **whoami** after the exploitation/privilege escalation phase. The following Fields will be helpful to include in the rule.

- Log source: Identify the log source capturing the event logs
- Event ID: which Event ID is associated with Process Execution activity? In this case, event id 4688 will be helpful.
- NewProcessName: which process name will be helpful to include in the rule?

**Rule**: If Log Source is WinEventLog **AND** EventCode is **4688**, and NewProcessName contains **whoami**, then Trigger an ALERT **WHOAMI command Execution DETECTED**

In the previous task, the importance of field-value pairs was discussed. Correlation rules keep an eye on the values of certain fields to get triggered. That is the reason why it is important to have normalized logs ingested.

## Alert Investigation

When monitoring SIEM, analysts spend most of their time on dashboards as it displays various key details about the network in a very summarized way. Once an alert is triggered, the events/flows associated with the alert are examined, and the rule is checked to see which conditions are met. Based on the investigation, the analyst determines if it's a True or False positive. Some of the actions that are performed after the analysis are:

- Alert is False Alarm. It may require tuning the rule to avoid similar False positives from occurring again.
- Alert is True Positive. Perform further investigation.
- Contact the asset owner to inquire about the activity.
- Suspicious activity is confirmed. Isolate the infected host.
- Block the suspicious IP.
