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

# Navigating Splunk

### ﻿Splunk Bar

When you access Splunk, you will see the default home screen identical to the screenshot below.

![image](https://github.com/user-attachments/assets/2333f424-d6e4-4652-aafc-fd5d4d3ed4ca)


Let's look at each section, or panel, that makes up the home screen. The top panel is the **Splunk Bar** (below image). 

![image](https://github.com/user-attachments/assets/a413e16f-b9df-414e-902d-c97fe04f111c)

In the Splunk Bar, you can see system-level messages (**Messages**), configure the Splunk instance (**Settings**), review the progress of jobs (**Activity**), miscellaneous information such as tutorials (**Help**), and a search feature (**Find**). 

The ability to switch between installed Splunk apps instead of using the **Apps panel** can be achieved from the Splunk Bar, like in the image below.

![image](https://github.com/user-attachments/assets/69de0949-90e5-499d-aa28-9f357d479fbc)

## Apps Panel

Next is the **Apps Panel**.  In this panel, you can see the apps installed for the Splunk instance. 

The default app for every Splunk installation is **Search & Reporting**. 

![image](https://github.com/user-attachments/assets/d33591cf-cf92-4e66-8b7f-8ecc5df08817)

## Explore Splunk

The next section is **Explore Splunk**. This panel contains quick links to add data to the Splunk instance, add new Splunk apps, and access the Splunk documentation. 

![image](https://github.com/user-attachments/assets/6d0e4fcc-8857-4a38-b41f-33ad5d93f9dc)

## Splunk Dashboard

The last section is the **Home Dashboard**. By default, no dashboards are displayed. You can choose from a range of dashboards readily available within your Splunk instance. You can select a dashboard from the dropdown menu or by visiting the **dashboards listing page**.

https://github.com/user-attachments/assets/534b97ee-5e3f-4101-b291-04b622dda643

You can also create dashboards and add them to the Home Dashboard. 

Please review the Splunk documentation on [Navigating Splunk here](https://docs.splunk.com/Documentation/Splunk/8.1.2/SearchTutorial/NavigatingSplunk).

# Adding Data

Splunk can ingest any data. As per the Splunk documentation, when data is added to Splunk, the data is processed and transformed into a series of individual events. 

The data sources can be event logs, website logs, firewall logs, etc.

Data sources are grouped into categories. Below is a chart listing from the Splunk documentation detailing each data source category.

![image](https://github.com/user-attachments/assets/55f44f90-b59f-4706-b4f9-88815cdd03a7)

In this room, we're going to focus on **VPN logs**. When we click on the** Add Data link** (from the Splunk home screen), we're presented with the following screen. 

![image](https://github.com/user-attachments/assets/52aa12cf-4500-49ce-a898-c80f6226528c)


We will use the Upload Option to upload the data from our local machine. Download the attached log file and upload it on Splunk.

As shown above, it has a total of 5 steps to successfully upload the data.

1. **Select Source** -> Where we select the Log source.
2. **Select Source Type** -> Select what type of logs are being ingested.
3. **Input Settings** ->Select the index where these logs will be dumped and hostName to be associated with the logs.
4. **Review** -> Review all the gif
5. **Done** -> Final step, where the data is uploaded successfully and ready to be analyzed.

https://github.com/user-attachments/assets/5e4b17e3-cdc0-4c8d-b4bf-e73f8b4ebaaa

As you can see, there are A LOT more logs we can add to the Splunk instance, and Splunk supports various source types.

Download the attached log file "VPN_logs" and upload this file into the Splunk instance with the right source type.

**Note**: In case you are using the AttackBox, the file is available in the **/root/Rooms/SplunkBasic/ directory**.
