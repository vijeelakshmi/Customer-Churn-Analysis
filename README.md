# 📊 Customer Churn Analysis Dashboard – Power BI

## 📌 Project Overview

The **Customer Churn Analysis Dashboard** is an interactive business intelligence project developed using Microsoft Power BI. The main objective is to analyze customer behavior, identify churn patterns, understand customer segments, and measure revenue associated with customer churn.

This dashboard helps businesses understand why customers leave and identify opportunities to improve customer retention.

## 🎯 Project Objectives

- Analyze customer churn rate and retention rate.
- Identify customer segments with the highest churn.
- Understand the impact of contract types on customer churn.
- Analyze customer payment methods and service preferences.
- Calculate revenue lost due to customer churn.
- Identify high-risk and medium-risk customers.
- Estimate potential revenue at risk.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Microsoft Power BI | Dashboard development |
| Power Query | Data cleaning and transformation |
| DAX | Measures and calculations |
| CSV | Dataset |
| Microsoft Excel | Data inspection |

## 📂 Project Structure

```text
Customer-Churn-Analysis/
│
├── Dataset/
│   └── customer_churn_power_bi.csv
│
├── Dashboard/
│   └── Customer_Churn_Dashboard.pbix
│
├─
│
└── README.md
```

## 📁 Dataset Description

The project uses a synthetic customer churn dataset containing:

- **Total Records:** 7,043 customers
- **Total Columns:** 23
- **File Format:** CSV

### Important Dataset Columns

| Column | Description |
|---|---|
| CustomerID | Unique customer identifier |
| Gender | Customer gender |
| SeniorCitizen | Senior citizen indicator |
| Partner | Partner status |
| Dependents | Dependents status |
| State | Customer state |
| TenureMonths | Customer tenure in months |
| PhoneService | Phone service subscription |
| InternetService | Internet service type |
| OnlineSecurity | Online security subscription |
| TechSupport | Technical support subscription |
| Contract | Contract type |
| PaperlessBilling | Paperless billing status |
| PaymentMethod | Customer payment method |
| MonthlyCharges | Monthly customer charges |
| TotalCharges | Historical total charges |
| Churn | Customer churn status |
| ChurnReason | Reason associated with churn |

## 📊 Dashboard Features

### 1. Key Performance Indicators (KPIs)

- Total Customers
- Churned Customers
- Active Customers
- Churn Rate
- Monthly Revenue
- Average Monthly Charges
- Average Customer Lifetime Value
- Revenue Lost Due to Churn
- Potential Revenue at Risk

### 2. Customer Churn Analysis

- Churn Trend Over Time (requires a suitable dated dataset)
- Churn by Contract Type
- Churn by Gender
- Churn by Internet Service
- Churn by Payment Method

### 3. Customer Segmentation

- Churn Rate by Customer Segment
- Churn by Customer Tenure
- Customer Risk Analysis
- Customer Distribution by State

### 4. Revenue Analysis

- Total Revenue
- Revenue Lost Due to Churn
- Monthly Revenue at Risk
- Annualized Revenue at Risk
- Average Customer Lifetime Value

### 5. Churn Reasons

- High Monthly Charges
- Competitor Offers
- Poor Customer Support
- Service Quality
- Contract Expired

## 📐 Important DAX Measures

### Total Customers

```DAX
Total Customers =
COUNTROWS(Customers)
```

### Churned Customers

```DAX
Churned Customers =
CALCULATE(
    COUNTROWS(Customers),
    Customers[Churn] = "Yes"
)
```

### Churn Rate

```DAX
Churn Rate =
DIVIDE(
    [Churned Customers],
    [Total Customers],
    0
)
```

### Retention Rate

```DAX
Retention Rate =
1 - [Churn Rate]
```

### Revenue Lost Due to Churn

```DAX
Revenue Lost Due to Churn =
CALCULATE(
    SUM(Customers[TotalCharges]),
    Customers[Churn] = "Yes"
)
```

### Average Customer Lifetime Value

```DAX
Avg Customer Lifetime Value =
AVERAGE(Customers[TotalCharges])
```

### Potential Revenue at Risk

```DAX
Potential Revenue at Risk =
CALCULATE(
    SUM(Customers[MonthlyCharges]),
    Customers[Churn] = "No",
    Customers[Customer Risk] IN {
        "High Risk",
        "Medium Risk"
    }
)
```

## 🎨 Dashboard Design

The dashboard uses a modern purple-themed design with:

- Interactive KPI cards
- Donut charts
- Bar charts
- Treemaps
- Revenue indicators
- Customer segmentation visuals
- Interactive slicers and filters

## 💡 Business Insights

This project helps answer important business questions:

1. Which contract type has the highest churn rate?
2. Which payment method is associated with higher churn?
3. Which internet service customers are more likely to leave?
4. How does customer tenure relate to churn?
5. How much historical revenue is associated with churned customers?
6. Which customer segments have higher churn risk?
7. How much recurring revenue is associated with active high-risk customers?

## 🚀 How to Run the Project

1. Download or clone this repository.
2. Download the customer churn CSV dataset.
3. Open Microsoft Power BI Desktop.
4. Select **Get Data → Text/CSV**.
5. Import the dataset.
6. Open Power Query and perform data cleaning.
7. Create the required DAX measures.
8. Open the `.pbix` dashboard file.
9. Explore the dashboard using interactive filters.

## 📚 Skills Demonstrated

- Data Cleaning
- Data Transformation
- Data Visualization
- Data Modeling
- DAX Calculations
- Business Intelligence
- Customer Segmentation
- KPI Development
- Business Analysis
- Dashboard Design

## ⚠️ Data Disclaimer

This project uses a synthetic dataset generated for educational and portfolio purposes. It does not contain actual customer information.

The dataset does not include historical churn dates, so a genuine monthly churn trend cannot be calculated from the current data. Customer risk categories are rule-based classifications, not machine-learning predictions.

## 👨‍💻 Project Category

**Data Analytics | Business Intelligence | Power BI | Customer Churn Analysis**

---

⭐ If you find this project useful, consider giving this repository a star!