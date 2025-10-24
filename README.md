# 🚀 End-to-End Data Warehouse Analytics with Microsoft Fabric

---

## 🌟 Project Overview

This project showcases a complete, end-to-end **Data Warehouse Analytics** solution built entirely within **Microsoft Fabric**. It demonstrates the seamless integration of key Fabric components—**Pipelines**, **T-SQL**, **Notebooks**, **OneLake**, and the **Data Warehouse**—to ingest, transform, curate, and visualize data, culminating in a dynamic **Power BI** reporting layer.

### 🎯 Key Objectives

* Establish a scalable data ingestion and transformation workflow using Fabric **Pipelines** and **T-SQL**.
* Leverage **OneLake** as the single, unified data foundation.
* Utilize the Fabric **Data Warehouse** for high-performance querying and data modeling.
* Curate raw data into an optimized dimensional model (Star Schema).
* Provide interactive, actionable business insights via **Power BI**.

---

## ⚙️ Architecture and Components

The solution follows a classic Medallion architecture (Bronze, Silver, Gold zones) powered by the Microsoft Fabric ecosystem.

| Component | Technology | Role in Project |
| :--- | :--- | :--- |
| **Data Ingestion** | **Data Pipelines** | Orchestrates the data movement from the source system into OneLake (Bronze Zone). |
| **ETL/Transformation** | **T-SQL** | Reads raw data, performs cleansing, standardization, and transforms it to the Silver Zone. |
| **Data Storage** | **OneLake** | The unified logical data lake where all data (raw and curated) permanently resides. |
| **Data Modeling** | **Data Warehouse** & **T-SQL** | Creates the final dimensional model (Fact/Dimension tables) in the Gold Zone, optimized for reporting. |
| **Visualization** | **Power BI** | Connects to the Gold Zone tables in the Data Warehouse to deliver interactive reports. |
| **Source System** | ***Azure Blob Storage - World Wide Importers Dataset** | The initial source of data for the project. |

### 🗺️ Data Flow Diagram

<img width="638" height="364" alt="image" src="https://github.com/user-attachments/assets/c8d8832c-94e0-4308-8380-462e623da314" />

---

## 🛠️ Implementation Details (The Data Journey)

### 1. Ingestion (Raw Data)
A **Data Pipeline** is configured to connect to the `Azure Blob Storage` and perform a batch load of raw data. This data is written directly to the **Lakehouse** within **OneLake** as Delta tables in the **`silver`** zone.

### 2. Curation & Modeling (Data Warehouse & SQL)
The **Fabric Data Warehouse** reads the raw data from the `silver` zone tables in OneLake. **SQL** commands are executed to:
* Apply business logic and aggregations.
* Create **Fact** tables (e.g., `FactSales`).
* Create **Dimension** tables (e.g., `DimCustomer`, `DimDate`).
* This final, curated data set forms the **`gold`** zone.

### 3. Reporting (Power BI)
**Power BI Desktop** connects directly to the final `gold` tables within the Fabric Data Warehouse. The following visualizations and reports were created:
* `Sales Performance Dashboard`
* `Customer Segmentation Report`
* `Net Profit by country, state prvoince, and city`

<img width="1492" height="850" alt="image" src="https://github.com/user-attachments/assets/37d177f9-e572-45fc-8e62-ad4e7cbf6443" />


## 💻 Setup and Prerequisites

To replicate or explore this project, you will need:

1.  A **Microsoft Fabric** environment (trial or paid capacity).
2.  A Fabric **Workspace** with permissions to create Pipelines, Notebooks, and a Data Warehouse.

## 💡 Next Steps and Potential Enhancements

* **Real-time Analytics:** Implement **Data Activator** to monitor key metrics in the Data Warehouse and trigger automated alerts or actions.
* **Predictive Modeling:** Introduce an **ML Model** (using Fabric's ML features) into the Notebook stage for tasks like sales forecasting or customer churn prediction.
* **CI/CD:** Utilize **Git Integration** within Fabric for version control and automated deployment of all assets.
