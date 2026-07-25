# Sales Analysis Dashboard (Microsoft Fabric + Power BI)

An end-to-end Sales Analytics project built using **Microsoft Fabric** and **Power BI**. The project demonstrates the complete data engineering and analytics lifecycle, including data ingestion, transformation, modeling, dashboard development, security implementation, and publishing.

---

## Dashboard Preview

<img width="1896" height="828" alt="Sales Dashboard_app" src="https://github.com/user-attachments/assets/04430c92-cd72-4dd4-ab3a-28245b6ce3d3" />
<img width="1837" height="789" alt="Pipeline" src="https://github.com/user-attachments/assets/df5e1177-db3d-4862-86d1-19999ed49114" />
<img width="1824" height="831" alt="LakeHouse" src="https://github.com/user-attachments/assets/8ae5061c-9d56-4c0f-8781-f03dce9e4bc1" />
<img width="1834" height="824" alt="Warehouse" src="https://github.com/user-attachments/assets/899a0c2d-8598-4c69-9d62-f46e8ec2e40d" />

---

## Project Overview

The dashboard provides insights into:

* Sales Revenue
* Orders
* Product Categories
* Regional Performance
* Customer Performance
* Monthly Sales Trends

The solution was built on top of a **Fabric Semantic Model** and optimized for fast querying and near real-time analytics.

---

## Architecture

### Data Ingestion

* Raw sales data is ingested from an **HTTP source** using a **Fabric Data Pipeline**.

### Medallion Architecture

The project follows the **Bronze → Silver → Gold** pattern.

#### Bronze Layer

* Stores raw data exactly as received from the source.

#### Silver Layer

* Data is cleaned, validated, and transformed using **PySpark**.
* Processed data is stored in **Lakehouse** and exposed through **SQL Endpoints**.

#### Gold Layer

* Business-ready data is created.
* Includes **1 Fact table** and **3 Dimension tables**.
* Final tables are stored in the **Warehouse** for reporting and analytics.

---

## Automation

The entire pipeline—from ingestion to Gold layer creation—is automated using **Fabric Pipelines** and scheduled to run **daily at 6:00 AM**.

---

## Data Validation

Data quality checks and validation were performed in the **Warehouse** using **T-SQL** before reporting.

---

## Data Modeling

A star schema was implemented with:

* `fact_sales`
* `dim_customer`
* `dim_product`
* `dim_region`

Relationships were configured as **1:* (one-to-many)** with single-direction filtering.

---

## Reporting

* Connected Power BI Desktop to the Fabric Semantic Model using **DirectLake mode**.
* Built an interactive **Sales Analysis Dashboard**.
* Published the report to **Microsoft Fabric**.

---

## Security

Implemented **Static Row-Level Security (RLS)** to control data access for different users and improve data security.

---

## Publishing

The dashboard was published through a **Fabric App** for business stakeholders to access and analyze the reports efficiently.

---

## Challenge Faced

### Issue

Month names in visuals were sorting alphabetically instead of chronological order.

### Solution

Configured the `month_name` column to **Sort by Column → `month_number`** in the Fabric Semantic Model. After saving the model, all visuals displayed months in the correct calendar order.

---

## Technologies Used

* Microsoft Fabric
* Power BI
* Fabric Data Pipelines
* Lakehouse
* Warehouse
* PySpark
* T-SQL
* DirectLake
* Row-Level Security (RLS)

---

## Dataset

Source Dataset:
https://raw.githubusercontent.com/the-mansi-goel/FABRIC/refs/heads/main/sales_data.csv

---

## Power BI Dashboard

Sales Dashboard:
https://app.fabric.microsoft.com/links/S0PWlOvT_e?ctid=68925209-7378-4959-87b9-88ea918ae4e0&pbi_source=linkShare

---

## Fabric App

Sales App:
https://app.fabric.microsoft.com/groups/me/apps/98ece5cf-1bef-41db-a3b0-2e776e171b30/reports/72ebbf50-18d7-4ce1-a29b-e0f4d9877fdf/a580ea342c666e8813a5?ctid=68925209-7378-4959-87b9-88ea918ae4e0&experience=fabric-developer

---

## Key Highlights

* End-to-end Microsoft Fabric project
* Automated data pipeline with daily scheduling
* Medallion architecture implementation
* PySpark-based data transformation
* Warehouse-based star schema modeling
* DirectLake reporting for high performance
* Row-Level Security implementation
* Production-style dashboard publishing
