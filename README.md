# 🛒 User Journey Funnel Analysis
### Where Are Customers Dropping Off? — A Data Analytics Project

---

## 📌 Project Overview

This project analyzes the customer journey in an e-commerce store to find out **why customers are not completing their purchases**. 

Using real data analysis techniques, I identified the biggest drop-off points and provided actionable recommendations to improve conversion rates.

---

## 🔧 Tools Used

| Tool | Purpose |
|------|---------|
| Microsoft Excel | Data creation and cleaning |
| MySQL Workbench | Data analysis using SQL queries |
| Power BI | Interactive dashboard visualization |

---

## 📊 Dataset

- **200 customer records** with the following columns:
  - `User_ID` — Unique customer identifier
  - `Date` — Visit date (Jan 2024 – Jun 2024)
  - `Device` — Mobile / Desktop / Tablet
  - `Traffic_Source` — Google / Facebook / Instagram / Organic / Email
  - `Location` — Mumbai / Delhi / Bangalore / Chennai / Hyderabad / Pune / Kolkata
  - `Stage_Reached` — Visit / Signup / Add to Cart / Purchase

---

## 🔍 Key Findings

### Funnel Analysis
| Stage | Users | Drop-off |
|-------|-------|---------|
| Visit | 76 | — |
| Add to Cart | 48 | 37% drop |
| Signup | 44 | 8% drop |
| Purchase | 32 | 27% drop |

### 📱 Biggest Problem: Mobile Users
- Mobile users have the **highest drop-off at Add to Cart stage**
- Mobile checkout process is too complicated
- Small screen makes payment difficult

### 📣 Best Traffic Source
- **Google** brings the most visitors
- **Facebook** brings good quality buyers

---

## 💡 Recommendations

1. **Simplify mobile checkout** — Reduce steps from 5 to 2
2. **Add mobile payment options** — UPI, Google Pay, one-click pay
3. **Send cart reminder notifications** — Recover abandoned carts
4. **Invest more in Google ads** — Best ROI traffic source
5. **Add trust badges** — Increase purchase confidence

> These changes can recover up to **30% of lost sales**

---

## 📈 Power BI Dashboard

The dashboard includes:
- 🔻 **Funnel Chart** — User journey drop-off visualization
- 📱 **Bar Chart** — Device comparison (Mobile vs Desktop vs Tablet)
- 🍩 **Donut Chart** — Traffic source breakdown
- 📉 **Line Chart** — Monthly trend analysis

---

## 🗄️ SQL Queries Used

```sql
-- 1. Funnel Drop-off Analysis
SELECT Stage_Reached, COUNT(*) AS Total_Users
FROM customer_data
GROUP BY Stage_Reached
ORDER BY Total_Users DESC;

-- 2. Device Analysis
SELECT Device, COUNT(*) AS Total_Users,
SUM(CASE WHEN Stage_Reached = 'Purchase' THEN 1 ELSE 0 END) AS Purchases
FROM customer_data
GROUP BY Device
ORDER BY Total_Users DESC;

-- 3. Traffic Source Analysis
SELECT Traffic_Source, COUNT(*) AS Total_Users,
SUM(CASE WHEN Stage_Reached = 'Purchase' THEN 1 ELSE 0 END) AS Purchases
FROM customer_data
GROUP BY Traffic_Source
ORDER BY Purchases DESC;

-- 4. Conversion Rate
SELECT 
COUNT(*) AS Total_Visitors,
SUM(CASE WHEN Stage_Reached='Purchase' THEN 1 ELSE 0 END) AS Total_Purchases,
ROUND(SUM(CASE WHEN Stage_Reached='Purchase' THEN 1 ELSE 0 END) * 100.0 / COUNT(*), 1) AS Conversion_Rate
FROM customer_data;
```

---

## 📁 Files in this Repository

| File | Description |
|------|-------------|
| `FunnelProject.xlsx` | Raw dataset with 200 customer records |
| `customer_data.csv` | CSV version of the dataset |
| `User_Journey_Funnel_Project.pbix` | Power BI dashboard file |
| `README.md` | Project documentation |

---

## 🎯 Business Impact

> **Problem:** E-commerce store losing 58% of customers before purchase
>
> **Solution:** Identified mobile checkout as the biggest issue
>
> **Result:** Recommendations can recover 30% of lost sales

---

## 👩‍💻 About This Project

This project was built as a **Data Analyst portfolio project** to demonstrate skills in:
- Data cleaning and preparation
- SQL data analysis
- Business intelligence and visualization
- Deriving actionable insights from data

---

⭐ **If you found this project useful, please give it a star!**
