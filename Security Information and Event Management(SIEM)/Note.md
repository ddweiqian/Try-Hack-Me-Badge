
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

