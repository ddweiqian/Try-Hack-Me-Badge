# Incident Handling Scenario

A US-based company **CyberT** has been monitoring the VPN logs of the employees, and the SOC team detected some anomalies in the VPN activities. Our task as SOC Analysts is to examine the VPN logs for January 2022 and identify the anomalies. Some of the key points to note before the investigation are:

- All VPN logs are being ingested into the index **vpn_connections**.
- The index contains the VPN logs for January 2022.
- A user **Johny Brown** was terminated on 1st January 2022.
- We observed failed connection attempts against some users that need to be investigated.
- 
![image](https://github.com/user-attachments/assets/49ba4ad2-644c-4fa8-bd3e-15080e4b6722)

# ElasticStack Overview

## Elastic stack

Elastic stack is the collection of different open source components linked together to help users take the data from any source and in any format and perform a search, analyze and visualize the data in real-time.

![image](https://github.com/user-attachments/assets/cafa9595-bf4b-47b1-8599-80d8b19f413d)

Let's explore each component briefly and see how they work together.

## Elasticsearch

Elasticsearch is a full-text search and analytics engine used to store JSON-formated documents. Elasticsearch is an important component used to store, analyze, perform correlation on the data, etc. Elasticsearch supports RESTFul API to interact with the data.

## Logstash

Logstash is a data processing engine used to take the data from different sources, apply the filter on it or normalize it, and then send it to the destination which could be Kibana or a listening port. A logstash configuration file is divided into three parts, as shown below.

The **input** part is where the user defines the source from which the data is being ingested. Logstash supports many input plugins as shown in the [reference](https://www.elastic.co/guide/en/logstash/8.1/input-plugins.html)

The **filter** part is where the user specifies the filter options to normalize the log ingested above. Logstash supports many filter plugins as shown in the [reference documentation](https://www.elastic.co/guide/en/logstash/8.1/filter-plugins.html)

The **Output** part is where the user wants the filtered data to send. It can be a listening port, Kibana Interface, elasticsearch database, a file, etc. Logstash supports many Output plugins as shown in the [reference documentation](https://www.elastic.co/guide/en/logstash/8.1/output-plugins.html)

## Beats

Beats is a host-based agent known as Data-shippers that is used to ship/transfer data from the endpoints to elasticsearch. Each beat is a single-purpose agent that sends specific data to the elasticsearch. All available beats are shown below.

![image](https://github.com/user-attachments/assets/303eccf9-a6af-4140-a040-81b8fa6bf911)

## Kibana

Kibana is a web-based data visualization that works with elasticsearch to analyze, investigate and visualize the data stream in real-time. It allows the users to create multiple visualizations and dashboards for better visibility—more on Kibana in the following tasks.

![image](https://github.com/user-attachments/assets/db1766f3-a3f7-4058-89eb-e03ca04c8d23)

- Beats is a set of different data shipping agents used to collect data from multiple agents. Like Winlogbeat is used to collect windows event logs, Packetbeat collects network traffic flows.
- Logstash collects data from beats, ports or files, etc., parses/normalizes it into field value pairs, and stores them into elasticsearch.
- Elasticsearch acts as a database used to search and analyze the data.
- Kibana is responsible for displaying and visualizing the data stored in elasticsearch. The data stored in elasticseach can easily be shaped into different visualizations, time charts, infographics, etc., using Kibana.

### Kibana Overview
As we already covered a brief intro of Kibana. In this room, we will explore different Kibana features while investigating the VPN logs. Kibana is an integral component of Elastic stack that is used to display, visualize and search logs. Some of the important tabs we will cover here are:

- Discover tab
- Visualization
- Dashboard

[![Getting to know Kibana video](https://img.youtube.com/vi/l2b04Sz8vTw/hqdefault.jpg)](https://www.youtube.com/watch?v=l2b04Sz8vTw)

### Discover Tab
Kibana Discover tab is a place where analyst spends most of their time. This tab shows the ingested logs (also known as documents), the search bar, normalized fields, etc. Here analysts can perform the following tasks:

- Search for the logs
- Investigate anomalies
- Apply filter based on
  - search term
  - Time period

#### Discover Tab Overview

Discover tab within the Kibana interface contains the logs being ingested manually or in real-time, the time-chart, normalized fields, etc. Analysts use this tab mostly to search/investigate the logs using the search bar and filter options.

![image](https://github.com/user-attachments/assets/5b4a367b-82c7-4f72-848e-35e1832e8423)

Some key information available in a dashboard interface are

1. **Logs (document):** Each log here is also known as a single document containing information about the event. It shows the fields and values found in that document.
2. **Fields pane:** Left panel of the interface shows the list of the fields parsed from the logs. We can click on any field to add the field to the filter or remove it from the search.
3. **Index Pattern:** Let the user select the index pattern from the available list.
4. **Search bar:** A place where the user adds search queries / applies filters to narrow down the results.
5. **Time Filter:** We can narrow down results based on the time duration. This tab has many options to select from to filter/limit the logs.
6. **Time Interval:** This chart shows the event counts over time.
7. **TOP Bar:** This bar contains various options to save the search, open the saved searches, share or save the search, etc.

Each important element found in the Discover tab is briefly explained below:

#### Element 1: Time Filter

The time filter allows us to apply a log filter based on the time. It has many options to choose from.

![image](https://github.com/user-attachments/assets/cda35f2f-41c0-43d9-9c52-85f70f90cb0d)

#### Element 2: Quick Select
The Quick Select tab is another useful tab within the Kibana interface that provides multiple options to select from. The Refresh, Every option at the end will allow us to choose the time to refresh the logs continuously. If 5 seconds is set, the logs will refresh every 5 seconds automatically.

![image](https://github.com/user-attachments/assets/a43434d7-ec9f-42f8-af7c-6aeff642a033)

#### Element 3: Timeline

The timeline pane provides an overview of the number of events that occurred for the time/date, as shown below. We can select the bar only to show the logs in that specified period. The count at the top left displays the number of documents/events it found in the selected time.

![image](https://github.com/user-attachments/assets/ebee32dc-2f9f-4f3d-8519-360eafe68cd8)

This bar is also helpful in identifying the spike in the logs. We got an unusual spike on 11th January 2022, which is worth investigating.

#### Element 4： Index Pattern

Kibana, by default, requires an index pattern to access the data stored/being ingested in the elasticsearch. Index pattern tells Kibana which elasticsearch data we want to explore. Each Index pattern corresponds to certain defined properties of the fields. A single index pattern can point to multiple indices.

Each log source has a different log structure; therefore, when logs are ingested in the elasticsearch, they are first normalized into corresponding fields and values by creating a dedicated index pattern for the data source.

For example, the index pattern with the name **vpn_connections** that contains the VPN logs is shown below:

![image](https://github.com/user-attachments/assets/31dca0ee-77e6-4a9a-8ca9-f2ba44ed66f2)

#### Element 5：Left Panel - Fields

The left panel of the Kibana interface shows the list of the normalized fields it finds in the available documents/logs. Click on any field, and it will show the top 5 values and the percentage of the occurrence.

We can use these values to apply filters to them. Clicking on the + button will add a filter to show the logs containing this value, and the - button will apply the filter on this value to show the results that do not have this value.

![image](https://github.com/user-attachments/assets/6e3a88c6-94c0-4102-b8b8-35f2b3b4a915)

#### Element 6: Add Filter Option

**Add filter** option under the search bar allows us to apply a filter on the fields as shown below.

[![Filtering data in Kibana video](https://img.youtube.com/vi/I8NtctS33F0/hqdefault.jpg)](https://www.youtube.com/watch?v=I8NtctS33F0)

#### Element 7:Create Table

By default, the documents are shown in raw form. We can click on any document and select important fields to create a table showing only those fields. This method reduces the noise and makes it more presentable and meaningful.

[![How to Create a Data Table with Kibana Lens](https://img.youtube.com/vi/NRDue0dVBQI/hqdefault.jpg)](https://www.youtube.com/watch?v=NRDue0dVBQI)

Don't forget to save the table format once it is created. It will then show the same fields every time a user logs into the dashboard.

## KQL Overview 

KQL (Kibana Query Language) is a search query language used to search the ingested logs/documents in the elasticsearch. Apart from the KQL language, Kibana also supports Lucene Query Language. We can disable the KQL query as shown below.

![image](https://github.com/user-attachments/assets/de74ff07-2400-475e-b1b1-55e806266b26)

In this task, we will be exploring KQL syntax. With KQL, we can search for the logs in two different ways.

- Free text search
- Field-based search

### Free text Search

Free text search allows users to search for the logs based on the text-only. That means a simple search of the term **security** will return all the documents that contain this term, irrespective of the field.

Let us look at the index, which includes the VPN logs. One of the fields **Source_Country** has the list of countries from where the VPN connections originated, as shown below.

![image](https://github.com/user-attachments/assets/a9a5689f-03a5-497e-a6d3-39a4d6faa668)

Let's search for the text **United States** in the search bar to return all the logs that contain this term regardless of the place or the field. This search returned 2304 hits, as shown below

![image](https://github.com/user-attachments/assets/1b7ab135-330b-49b8-90e9-08dac26b6801)

What if we only search for the term **United** Will it return any result?

![image](https://github.com/user-attachments/assets/54b1b222-e2a7-4f0e-8420-6a5632479426)

It didn't return any result because KQL looks for the whole term/word in the documents.

### WILD CARD

KQL allows the wild card * to match parts of the term/word. Let's find out how to use this wild card in the search query.

KQL allows the wild card * to match parts of the term/word. Let's find out how to use this wild card in the search query.

Search Query: **United***

![image](https://github.com/user-attachments/assets/502d8b63-3124-4698-bbd0-56a7f21b7aa2)

We have used the wildcard with the term **United** to return all the results containing the term United and any other term. If we had logs with the term **United Nations**. It would also have returned those as a result of this wildcard.

## Logical Operators (AND | OR | NOT)

KQL also allows users to utilize the logical operators in the search query. Let us see the examples below.

1. **OR Operator**

We will use the **OR** operator to show logs that contain either the **United States** or **England**.

**Search Query:** **"United States"    OR     "England"**

![image](https://github.com/user-attachments/assets/e27c299d-4986-4319-99ed-7bcd7c8b6d95)

2- AND Operator

Here, we will use **AND** Operator to create a search that will return the logs that contain the terms **"UNITED STATES"** AND **"Virginia."**

**Search Query:** **"United States" AND "Virginia"**

![image](https://github.com/user-attachments/assets/63e5c445-28f9-4d2f-99ee-326132a730b6)

3. **NOT Operator**

Similarly, we can use **NOT** Operator to remove the particular term from the search results. This search query will show the logs from **the United States**, including all states but ignoring Florida.

**Search Query:** **"United States" AND NOT ("Florida")**

![image](https://github.com/user-attachments/assets/f5200396-a761-449c-b796-28d4a26930c2)

### Field-based search

In the Field-based search, we will provide the field name and the value we are looking for in the logs. This search has a special syntax as **FIELD : VALUE**. It uses a colon **:** as a separator between the field and the value. Let's look at a few examples.

**Search Query:** **Source_ip : 238.163.231.224    AND     UserName : Suleman**

**Explanation:** We are telling Kibana to display all the documents in which the field **Source_ip** contains the value **19.112.190.54** and **UserName** as **Suleman** as shown below.

https://github.com/user-attachments/assets/47384c61-1357-4c09-b520-e8e9e3a37799

As we click on the search bar, we will be presented with all the available fields that we can use in our search query. To explore the other options of KQL, look at this [official reference](https://www.elastic.co/guide/en/kibana/7.17/kuery-query.html)

## Creating Visualization

### Create Visualization
The visualization tab allows us to visualize the data in different forms like Table, Pie charts, Bar charts, etc. This visualization task will use multiple options this tab provides to create some simple presentable visualizations.

There are a few ways to navigate to the visualization tab. One way is to click on any field in the discover tab and click on the visualization as shown below.

[![How to Create a Data Table with Kibana Lens](https://img.youtube.com/vi/NRDue0dVBQI/hqdefault.jpg)](https://www.youtube.com/watch?v=NRDue0dVBQI)

We can create multiple visualizations by selecting options like tables, pie charts, etc.

### Correlation Option

Often, we require creating correlations between multiple fields. Dragging the required field in the middle will create a correlation tab in the visualization tab. Here we selected the Source_Country as the second field to show a correlation among the client Source_IP.

![image](https://github.com/user-attachments/assets/fca51e86-69b0-4ac3-9373-d8710f03cffd)

We can also create a table to show the values of the selected fields as columns, as shown below.

![image](https://github.com/user-attachments/assets/e40741b8-c385-47a7-997f-32ac7735c8da)

The most important step in creating these visualizations is to save them. Click on the **save Option** on the right side and fill in the descriptive values below. We can add these visualizations to the already existing dashboard, or we can create a new one as well.

![image](https://github.com/user-attachments/assets/22888400-91b7-4ca9-889a-d3694f79a350)

Steps to take after creating Visualizations:

- Create a visualization and Click on the Save button at the top right corner.
- Add the title and description to the visualization.
- We can add the visualization to any existing Dashboard or a new dashboard.
- Click Save and add to the library when it's done.

### Failed Connection Attempts

We will utilize the knowledge gained above to create a table to display the user and the IP address involved in failed attempts.

https://github.com/user-attachments/assets/05f1e000-974b-46ee-bec6-80366140055f

## Creating Dashboards

Dashboards provide good visibility on the logs collection. A user can create multiple dashboards to fulfil a specific need.

In this task, we can combine different saved searches and visualizations to create a custom dashboard for VPN logs visibility.

### Creating Custom Dashboard

By now, we have saved a few searches from the Discover tab and created some visualizations, and saved them. It's time to explore the dashboard tab and create a custom dashboard. The steps to create a dashboard are:

- Go to the Dashboard tab and click on the **Create dashboard**.

![image](https://github.com/user-attachments/assets/72588fe0-d8a9-4b0f-8dc8-3b1cb105c892)

- Click on Add from Library.
- Click on the visualizations and saved searches. It will be added to the dashboard.
- Once the items are added, adjust them accordingly, as shown below.
- Don't forget to save the dashboard after completing it.



https://github.com/user-attachments/assets/3ca13f85-3471-426e-aa3f-582bb8830f8f



