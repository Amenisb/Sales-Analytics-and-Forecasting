# End-to-End BI Solution: Operations, Purchasing, Inventory, Treasury & Revenue Forecasting

> Business Intelligence project delivered for a real client at **Murex Business Solutions**, from data warehouse design to the delivery of dashboards and a forecasting model, all validated by the client.

**Stack:** SQL Server · Talend Data Integration · Power BI · DAX · Python (Anaconda) · XGBoost · Scrum

---

## 1. Context and Objective

This project answers a **real client need**. The client, a company in the automotive sector, kept its data in a transactional SQL Server database and had no consolidated view of its performance. Requirements (KPIs, dashboards, revenue forecasting) were gathered directly from the client during scoping meetings.

The goal was to build an **end-to-end decision-support solution**:
- design a **data warehouse**;
- feed **data marts** through ETL processes;
- build interactive **Power BI dashboards** for each business area;
- **forecast future revenue** using Machine Learning.

## 2. Solution Architecture

```
Source database (SQL Server)      Excel / flat files
           \                           /
            └──────►  Talend (ETL)  ◄──┘
                          │
                          ▼
           Data warehouse (SQL Server)
           Kimball approach, star schema
                          │
         ┌────────┬───────┼────────┬────────────┐
         ▼        ▼       ▼        ▼            ▼
    Operations Purchasing Inventory Treasury  Revenue forecast
                          │                   (Python / XGBoost)
                          ▼
                   Power BI (DAX)
```


## 3. Modules and Key Performance Indicators (KPIs)

**Operations**
- Revenue: parts sales, labor, commissions on new vehicle sales
- Gross margin by activity
- Repair time

**Purchasing**
- Purchasing revenue trend
- Profit margin
- Purchase price trend by item
- Subcontracting tracked by month and by subcontractor
- Top suppliers

**Inventory**
- Stock trend and stock value (by month, by item)
- Weighted average cost (WAC)
- Inventory turnover rate by item

**Treasury**
- Daily cash balance trend
- Cash inflows and outflows by payment method
- Control of transfers, deposits and exchanges
- Tracking of unpaid cheques

## 4. Screenshots

### Home
![Home](images/00-accueil.png)

### Operations
![Operations](images/01-exploitation.png)

### Purchasing
![Purchasing](images/02-achats.png)

### Inventory
![Inventory](images/03-stocks.png)

### Treasury
![Treasury](images/04-tresorerie.png)

### 2023 Revenue Simulation (forecast)
![Revenue forecast](images/05-prediction-ca.png)

## 5. Machine Learning: Revenue Forecasting

- **Approach:** CRISP-DM (data preparation, modeling, evaluation, deployment)
- **Models compared:** SVR and **XGBoost**
- **Metrics:** RMSE and MAE. XGBoost produced lower errors than SVR in every run, so it was selected.
- **Validation:** tested on 2023 data, with predictions stored in the data warehouse.
- **Deployment:** Power BI dashboard showing the monthly trend of forecast revenue, with a KPI for annual revenue.
- **Client feedback:** the predicted values were very close to the revenue actually achieved each month.

## 6. Skills Demonstrated

- Dimensional modeling (fact tables, dimensions, star schema)
- ETL with Talend (extraction, cleaning, loading)
- SQL Server
- DAX measures and Power BI dashboard design
- Applied Machine Learning (XGBoost, SVR) with Python
- Agile project management (Scrum)

## 7. Repository Structure

```
├── README.md
├── report/
│   └── (optional)
├── images/
│   └── (dashboard screenshots)
├── powerbi/
│   └── dashboards.pbix   (anonymized version)
├── etl/
│   └── (screenshots of Talend jobs)
└── ml/
    └── (Python forecasting notebook)
```

> The source data belongs to the client and is **not** published in this repository.

## 8. Author

**Ameni Sbei**, Business Intelligence

[LinkedIn](#) · [Email](#sbeiameni@gmail.com)
