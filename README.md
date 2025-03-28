## My Project in Shopee
### 1. Tracking Service
**Introduction**

![image](https://github.com/user-attachments/assets/ef1839aa-7554-4ec7-ad01-17d864c9e4d6)


The Python Django FMS (Fulfillment Management System) integrates the core functionalities of SPX (Shopee Xpress). As the business continues to grow and the team expands, FMS has the following drawbacks: 

1). The functionalities of various modules are tightly coupled, making maintenance difficult. 

2). The Python Django system has performance bottlenecks that cannot accommodate the increasing volume of data. 

3). There is a lack of mechanisms to ensure data consistency. 

Therefore, there is a need to refactor FMS, which will be done in two steps. 

Step 1: Migrating the FMS Python service to the FO (FleetOrder) Golang service, with the new service including shipment and tracking functionalities. 

Step 2: Focusing on further decoupling by separating the tracking feature from FO to create an independent Track Service, along with a series of optimizations to improve service performance and data consistency.

![image](https://github.com/user-attachments/assets/598eed68-bb0c-46b3-9e3a-072fcd455804)


**Tech Doc**

https://docs.google.com/document/d/1VnE-k1Ih_Q93cclslOHPG4FlXxqkLSBm7DVg8hGxrvo/edit?usp=sharing

### 2. ShopeeHDMS
**Introduction**

ShopeeHDMS is a heterogeneous database migration service for Shopee. Compared to other industry-standard data migration tools, this tool is designed to be simple, user-friendly, high-performance, configurable, and monitorable, while ensuring data consistency and better adapting to Shopee's business characteristics.

![image](https://github.com/user-attachments/assets/185e1c1a-d7ec-4b17-a20e-142894f762d6)


**Main Features**

- Full Data Synchronization: historical data migration
- Full Data Checking: validation of historical data migration
- Increment Data Synchronization: increment data migration
- Increment Data Checking: validation of increment data migration
- Data Fixing: datafixing of inconsistent data
- Management System: a migration task management system
- Configuration Center: a configuration center for ShopeeHDMS

![longshot20241120170535](https://github.com/user-attachments/assets/90292c68-1e49-4b37-b446-6a9c8446863f)

**Tech Doc**

https://docs.google.com/document/d/1MBEodQZo_Z0H1qFIYwDY7tYaXwT1KrO-LZkYbzjPlYE/edit?usp=sharing

### 3. SPXComparator
**Introduction**

![image](https://github.com/user-attachments/assets/da1cda67-05eb-49e6-8239-48c99f6abb01)


SPXComparator is a traffic replay and comparing system for SPX (Shopee Xpress).

**Main Features**

1). Configurable Traffic Matching Rules
- Determine which service's traffic to receive, which service to send traffic to, and the proportion of traffic to be sent.
-  Query the plugin matcher based on the configured source::destService::url.

2). Traffic Comparison Plugin
-  The default plugin provides general comparison functionality.
-  Custom plugin development is supported for tailored comparison features.

3). Traffic Forwarding and Comparison
-  Live traffic is copied to destService.
-  Results are returned to the plugin for comparison.
-  Supports real-time playback and delayed playback.

4). Support for Result Storage and Reporting
-  Comparison results are stored in the database.
-  Comparison results are reported to Prometheus and displayed on Grafana dashboards.

5). Traffic Protection
-  The livetest service does not support write operations.
-  The livetest service cannot request services or interfaces outside of the whitelist.
-  Supports Kafka consumption rate limiting and consumption dropping.


**Tech Doc**

https://docs.google.com/document/d/1YK8laLG8_MmE_hEaF6EgW5SXFotJ6_rNaLMRbYCNSW8/edit?usp=sharing




