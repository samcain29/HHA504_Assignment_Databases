# HHA504 Assignment: Working with Managed Databases in Azure and GCP

## Table of Contents
- [1. Azure MySQL Setup](#1-azure-mysql-setup)
- [2. GCP MySQL Setup](#2-gcp-mysql-setup)
- [3. Exploring BigQuery](#3-exploring-bigquery)
- [4. Monitoring Databases](#4-monitoring-databases)
- [5. Reflections](#5-reflections)

---

## 1. Azure MySQL Setup

### Step 1: Creating an Azure Database for MySQL
- Logged into the [Azure Portal](https://portal.azure.com).
- Navigated to **Azure Database for MySQL Flexible Server** and created a new instance with the following configuration:
  - Server name: `my-sql-db`
  - Resource group: `DefaultResourceGroup-EUS2`
  - Location: `East US 2`
  - Pricing tier: `Burstable`
  - Compute size: `Standard_B1ms (1 vCore, 2 GiB memory, 640 max iops)`
  - Storage: `20 GiB`

**Screenshot of Azure MySQL setup:**
![image](https://github.com/user-attachments/assets/6f02d7c0-1d31-4ae0-8c83-018b3a10bd17)

### Step 2: Starting the MySQL Database
- Started the MySQL instance from the Azure portal and documented the connection details.

**Connection Details:**
- Hostname: `my-sql-db.mysql.database.azure.com`
- Username: `mysqladmin`
  
**Screenshot of Azure DB Connection Details:**
![image](https://github.com/user-attachments/assets/98d64674-6864-4e3d-a558-0be1cbfd6656)

---

## 2. GCP MySQL Setup

### Step 1: Creating a Cloud SQL MySQL Instance in GCP
- Accessed the [Google Cloud Console](https://console.cloud.google.com) and created a Cloud SQL instance with MySQL:
  - Instance ID: `my-cloud-sql-instance`
  - Region: `us-central1 (Iowa)`
  - Machine type: `db-perf-optimized-N-8`
  - Storage: `SSD , 250 GB`

**Screenshot of GCP MySQL setup:**
![image](https://github.com/user-attachments/assets/ae2133ef-9d97-4788-ac26-b4c7c1024dab)

### Step 2: Starting the Cloud SQL Instance
- Started the Cloud SQL instance and noted the connection details.

**Connection Details:**
- Instance connection name: `cain-samantha-hha504:us-central1:my-cloud-sql-instance`
- Public IP: `34.121.216.128`
  
**Screenshot of GCP Cloud Instance Connection Details:**
![image](https://github.com/user-attachments/assets/d95a4c6f-da1c-49b0-af69-b41f6c5423bc)

---

## 3. Exploring BigQuery

### Step 1: Creating a BigQuery Dataset
- Navigated to **BigQuery** in the Google Cloud Console.
- Created a dataset called `my_dataset` in the project `cain-samantha-hha504`.

**Screenshot of BigQuery Dataset Creation:**
![image](https://github.com/user-attachments/assets/03f3ec3e-ce5d-4e22-bfd1-d54e091a0556)

### Step 2: Loading Data into BigQuery
- Uploaded a CSV file to BigQuery and created a table `my_table`.

**Screenshot of Data Upload:**
![image](https://github.com/user-attachments/assets/e3a01b0d-5f3c-410c-876f-0c22ace31e2f)

### Step 3: Running a SQL Query in BigQuery
- Ran the following query to retrieve specific data:
  ```sql
  SELECT * FROM `cain-samanta-hha504.my_dateset.my_table`
  LIMIT 100;

**Screenshot of Running Query:**
![image](https://github.com/user-attachments/assets/288b6d60-0c8a-4d27-8db2-c36eab504921)

---

## 4. Monitoring Databases
### Azure MySQL Monitoring
- Used the Azure portal to monitor the MySQL instance. Key metrics tracked:
  - Cost: $0.37
  - CPU Usage: 0
  - Memory Usage: 21.7000%
  - Query Performance (Sum): 66.12k

- Screenshot of Azure Cost Analysis:
![image](https://github.com/user-attachments/assets/a6f56dc8-0972-464a-a8c2-aa1a7ed5c98d)

- Screenshot of Azure Metrics:
![image](https://github.com/user-attachments/assets/8ed0ae85-d9dc-4afc-b653-ac2188f73c48)

### GCP MySQL Monitoring
- Monitored Cloud SQL MySQL instance in GCP. Key metrics tracked:
  - Cost: $30.63
  - CPU Utilization: 8 vCPUs
  - Memory Utilization: 64 GB

**Screenshots of GCP Monitoring:**
![image](https://github.com/user-attachments/assets/b318f352-4157-4012-b2ac-0a683e408213)
![image](https://github.com/user-attachments/assets/020c7c16-7e05-49c7-bb64-d763ae8b2e17)


### BigQuery Monitoring
- Tracked BigQuery usage for queries and storage:
  - Cost: N/A
  - Storage Cost: N/A
  - Bytes processed: 0

**Screenshots of BigQuery Monitoring:**
![image](https://github.com/user-attachments/assets/87d6c6aa-a78a-4b2b-93e6-77592d7efe30)
![image](https://github.com/user-attachments/assets/c8413c68-ef58-49a8-a684-e2fe1040aec7)

---

## 5. Reflections
- Key Differences Between Azure and GCP
  - Database Setup:
      - Azure provides a streamlined process for creating a MySQL database, with a clear set of basic configurations.
      - GCP’s Cloud SQL setup requires slightly more attention to instance and zone selection but offers more flexibility in terms of machine types.
  - Monitoring Tools:
      - Azure offers detailed performance metrics through its portal, especially for CPU and memory usage, and allows easy configuration of alerts. You also have the option to view multiple metrics at the same time.
      - GCP's monitoring interface for Cloud SQL is comprehensive and allows for deeper insights into database performance. However, you have to view different metrics one my one.
  - Cost and Billing:
      - I was unable to access the BigQuery cost breakdowns for query execution and storage because the Reports section said that costs can take over 24 hours to becom available.
      - Both Azure and GCP platforms offer useful budgeting tools to monitor costs, though GCP’s BigQuery cost is based more on usage of data than on the instance itself as GCP's costs are significantly higher than Azure's.
  - Ease of Use:
      - Azure’s GUI feels slightly more user-friendly for basic database operations, while GCP offers more advanced customization options and better integration with other cloud services.
  - Final Thoughts:
      - Both Azure and GCP have their strengths in terms of managed database services. Azure's MySQL offering is easier to set up for beginners, while GCP provides more flexibility and is particularly strong with its BigQuery service for large-scale data analysis. Monitoring and cost tracking on both platforms are robust, though GCP’s billing for BigQuery queries provides a more granular breakdown.
