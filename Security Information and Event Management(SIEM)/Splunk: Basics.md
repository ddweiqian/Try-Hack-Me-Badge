# Splunk Components

Splunk is one of the leading SIEM solutions in the market that provides the ability to collect, analyze and correlate the network and machine logs in real-time

Splunk has three main components, namely Forwarder, Indexer, and Search Head. These components are explained below:

![image](https://github.com/user-attachments/assets/2f44733d-63f9-4918-85b4-1e7fde8c6894)

## Splunk Forwarder

Splunk Forwarder is a lightweight agent installed on the endpoint intended to be monitored, and its main task is to collect the data and send it to the Splunk instance. It does not affect the endpoint's performance as it takes very few resources to process. Some of the key data sources are:

- Web server generating web traffic.
-bWindows machine generating Windows Event Logs, PowerShell, and Sysmon data.
- Linux host generating host-centric logs.
- Database generating DB connection requests, responses, and errors.
- Splunk Forwarder

![image](https://github.com/user-attachments/assets/bdc1c0c3-6906-429a-b643-13103d3354c4)

## Splunk Indexer
Splunk Indexer plays the main role in processing the data it receives from forwarders. It takes the data, normalizes it into field-value pairs, determines the datatype of the data, and stores them as events. Processed data is easy to search and analyze.

![image](https://github.com/user-attachments/assets/3ae637f3-62cb-4b79-970d-dac3d5735428)
## Search Head

Splunk Search Head is the place within the Search & Reporting App where users can search the indexed logs as shown below. When the user searches for a term or uses a Search language known as Splunk Search Processing Language, the request is sent to the indexer and the relevant events are returned in the form of field-value pairs.

![image](https://github.com/user-attachments/assets/a011a224-4082-42a4-8d95-e13339633e94)

Search Head also provides the ability to transform the results into presentable tables, visualizations like pie-chart, bar-chart and column-chart, as shown below:

![image](https://github.com/user-attachments/assets/1ac354fc-2443-4a7d-bf06-be926725c3ac)
