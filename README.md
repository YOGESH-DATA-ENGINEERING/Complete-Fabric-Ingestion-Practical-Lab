# 🚀 Microsoft Fabric Ingestion Practical Lab – Complete Roadmap (All Methods)

This repository contains **hands-on practical labs** covering **ALL data ingestion methods in Microsoft Fabric** — batch, streaming, low-code, and enterprise-grade patterns.

---

## 🎯 Objectives

- Understand **when and why** to use each ingestion method in Fabric
- Gain **hands-on experience** with real-time and batch ingestion
- Build a **production-oriented ingestion mindset**
- Prepare for **DP-700 (Fabric Data Engineer Associate)**

---

## 🧰 Tools & Services Used

- Microsoft Fabric
- Eventstream
- KQL Database (Real-Time Analytics)
- Lakehouse (OneLake / Delta tables)
- Data Pipelines
- Copy Job
- Dataflow Gen2
- Spark Notebooks
- Sample datasets (Bike telemetry, CSV, SQL tables)

---

# ⭐ SECTION 1 — Real-Time / Streaming Ingestion Labs

## 🔹 Practical 1: Eventstream → KQL Database (Real-Time Ingestion)

### 📌 Objective
Ingest **real-time streaming data** into a **KQL Database** using **Eventstream** and query it using KQL.

---

### 🛠 Steps

1. Go to **Real-Time**
2. Click **Add Data**
3. Connect Sample Scenario **Stock Market**
4. Give **Source Name** , **Eventstream** and click connect. 
5. Go to Workspace -> Eventstream - You can see preview data. 
6. Give destination in pipeline , provide KQL tabe name and click publish. 
7. Go to KQL database - KQL Queryset  - write a query 

---

### 🔍 What to Observe

- Live records appear in **Preview data**
- Schema auto-created in KQL Database
- Continuous ingestion without manual triggers

---

### 🧪 Validation Query (KQL)
### Use "take" to view a sample number of records in the table and check the data.
```kql
StockEventhouse
| take 10

```

### See how many records are in the table.
```kql
StockEventhouse
| count
```

### This query returns the number of ingestions per hour in the given table.
```kql
StockEventhouse
| summarize IngestionCount = count() by bin(ingestion_time(), 1h)
```

### 🏗 Architecture Flow

Event Source → Eventstream → KQL Database → Real-Time Analytics

<img width="885" height="207" alt="image" src="https://github.com/user-attachments/assets/ba80acb7-6adf-4d9c-9ec6-a9a53250bbd4" />

### 📸 Screenshots

All screenshots for this practical are available here:  
👉 [View Screenshots](https://github.com/YOGESH-DATA-ENGINEERING/Complete-Fabric-Ingestion-Practical-Lab/tree/main/Practical%201%20-%20Eventstream%20KQL%20Database%20(Real-Time%20Ingestion)/screenshots)

---

## 🔹 Practical 2: Eventstream → Lakehouse (Streaming to Delta)

### 🛠 Steps
1. Use Same Eventstream
2. Add Destination - Lakeshouse  
3. give table name - **stream_stocks**
4. Run - Publish stream.
5. Go to Lakehouse  -> Check Delta table is generated 
6. Go to **sql endpoint** -  write a query

```sql
select * from stream_stocks
```

### 📸 Screenshots

All screenshots for this practical are available here:  
👉 [View Screenshots](https://github.com/YOGESH-DATA-ENGINEERING/Complete-Fabric-Ingestion-Practical-Lab/tree/main/Practical%202%20-%20Eventstream-Lakehouse(streaming%20to%20Delta)/Screenshots)


---
# ⭐ SECTION 2 — Batch / ETL / ELT Ingestion Labs
## 🔹 Practical 3: Copy Data → Lakehouse (pipeline)

### 🛠 Steps
1. Go to Workspace - Lakehouse
2. Add New item - **pipeline** 
3. **Copy Data** - add to canvas. 
4. In lakehouse upload csv in **Files**/new_folder 
5. source - Lakehouse
6. root folder - Files, give file path , brows - select uploaded csv file. ,
7. File Format - Deliitted Text
8. validate and run pipeline.

### 📸 Screenshots

All screenshots for this practical are available here:  
👉 [View Screenshots](https://github.com/YOGESH-DATA-ENGINEERING/Complete-Fabric-Ingestion-Practical-Lab/tree/main/Practical%203%20-%20Copy%20Data%20-%20Lakehouse/Screenshots)

---

## 🔹 Practical 4: Copy Data → Warehouse (pipeline)

### 🛠 Steps
1. Go to Workspace - create new **warehouse**
2. **Copy Data** - add to canvas. 
4. source - Lakehouse table
5. destination - warehouse
6. validate and run pipeline.

### 📸 Screenshots
All screenshots for this practical are available here:  
👉[View Screenshots](https://github.com/YOGESH-DATA-ENGINEERING/Complete-Fabric-Ingestion-Practical-Lab/tree/main/Practical%204%20-%20copy%20data%20(Lakehouse%20to%20Warehouse)/Screenshots)

---
## 🔹 Practical 5: Dataflow Gen2 → Lakehouse

### 🛠 Steps
1. Go to Workspace - **Lakehouse**
2. Get Data - New Dataflow Gen2 - Dataflow1
3. Link to file: Selected
4. File path or URL: https://raw.githubusercontent.com/MicrosoftLearning/dp-data/main/orders.csv
5. Connection: Create new connection
6. Connection name: Specify a unique name
7. data gateway: (none)
8. Authentication kind: Anonymous
9. next + create
10. Add column - custom column - MonthNo, Data type - Whole Number | formula : =Date.Month([OrderDate])
11. Add Destination -
12. Open Dataflow - view Diagram 
13. Add Dataflow to pipeline and run pipeline


### 📸 Screenshots

All screenshots for **Practical 5 – Dataflow Gen2 to Lakehouse** are available here:  
👉 [View Screenshots](https://github.com/YOGESH-DATA-ENGINEERING/Complete-Fabric-Ingestion-Practical-Lab/tree/main/Practical%205%20-%20Dataflow%20Gen%202%20%20to%20Lakehouse/Screenshots)

> 📌 Screenshots captured during real hands-on execution of Dataflow Gen2 loading data into a Lakehouse table.

---
### 🧑‍💻 Author
Yogesh Salve
Fabric Data Engineer | SQL | Streaming | Analytics

### 📌 This repository is part of my Microsoft Fabric hands-on learning and DP-700 preparation journey.

### ⭐ If you find this useful Please ⭐ star the repo and feel free to fork or contribute!

## Happy Learning 🚀
