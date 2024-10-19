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
![Azure MySQL Setup](screenshots/Azure_Database.png)

### Step 2: Starting the MySQL Database
- Started the MySQL instance from the Azure portal and documented the connection details.

**Connection Details:**
- Hostname: `my-sql-db.mysql.database.azure.com`
- Username: `mysqladmin`
  
**Screenshot of Azure DB Connection Details:**
![Azure DB Connection Details](screenshots/Azure_DB_Connection_Details.png)

---

## 2. GCP MySQL Setup

### Step 1: Creating a Cloud SQL MySQL Instance in GCP
- Accessed the [Google Cloud Console](https://console.cloud.google.com) and created a Cloud SQL instance with MySQL:
  - Instance ID: `my-cloud-sql-instance`
  - Region: `us-central1 (Iowa)`
  - Machine type: `db-perf-optimized-N-8`
  - Storage: `SSD , 250 GB`

**Screenshot of GCP MySQL setup:**
![GCP MySQL Setup](screenshots/GCP_Cloud_Instance.png)

### Step 2: Starting the Cloud SQL Instance
- Started the Cloud SQL instance and noted the connection details.

**Connection Details:**
- Instance connection name: `cain-samantha-hha504:us-central1:my-cloud-sql-instance`
- Public IP: `34.121.216.128`
  
**Screenshot of GCP Cloud Instance Connection Details:**
![GCP Cloud Instance Connection Details](screenshots/GCP_Cloud_Instance_Connection_Details.png)

---

## 3. Exploring BigQuery

### Step 1: Creating a BigQuery Dataset
- Navigated to **BigQuery** in the Google Cloud Console.
- Created a dataset called `myquery` in the project `cain-samantha-hha504`.

**Screenshot of BigQuery Dataset Creation:**
![BigQuery Dataset Creation](screenshots/GCP_BigQuery.png)

### Step 2: Loading Data into BigQuery
- Uploaded a CSV file to BigQuery and created a table `your_table_name`.

**Screenshot of Data Upload:**
![BigQuery Data Upload](path)

### Step 3: Running a SQL Query in BigQuery
- Ran the following query to retrieve specific data:
  ```sql
  SELECT * FROM `project_id.dataset_id.table_name`
  LIMIT 100;

---

## 4. Monitoring Databases
### Azure MySQL Monitoring
- Used the Azure portal to monitor the MySQL instance. Key metrics tracked:
  - CPU Usage: value
  - Memory Usage: value
  - Query Performance: value
- Screenshot of Azure Monitoring:

### GCP MySQL Monitoring
- Monitored Cloud SQL MySQL instance in GCP. Key metrics tracked:
  - CPU Utilization: value
  - Memory Utilization: value
  - Disk I/O: value
- Screenshot of GCP Monitoring:

### BigQuery Monitoring
- Tracked BigQuery usage for queries and storage:
  - Query Cost: query_cost
  - Storage Cost: storage_cost
- Screenshot of BigQuery Monitoring:

---

## 5. Reflections
- Key Differences Between Azure and GCP
  - Database Setup:
      - Azure provides a streamlined process for creating a MySQL database, with a clear set of basic configurations.
      - GCP’s Cloud SQL setup requires slightly more attention to instance and zone selection but offers more flexibility in terms of machine types.
  - Monitoring Tools:
      -Azure offers detailed performance metrics through its portal, especially for CPU and memory usage, and allows easy configuration of alerts.
      - GCP's monitoring interface for Cloud SQL is comprehensive and integrates well with Stackdriver Monitoring, allowing deeper insights into database performance.
  - Cost and Billing:
      - BigQuery provides clear cost breakdowns for query execution and storage. Query cost monitoring was intuitive, with a clear view of bytes processed.
      - Both platforms offer useful budgeting tools to monitor costs, though GCP’s BigQuery cost is based more on usage of data than on the instance itself.
  - Ease of Use:
      - Azure’s GUI feels slightly more user-friendly for basic database operations, while GCP offers more advanced customization options and better integration with other cloud services.
  - Final Thoughts:
      - Both Azure and GCP have their strengths in terms of managed database services. Azure's MySQL offering is easier to set up for beginners, while GCP provides more flexibility and is particularly strong with its BigQuery service for large-scale data analysis. Monitoring and cost tracking on both platforms are robust, though GCP’s billing for BigQuery queries provides a more granular breakdown.
