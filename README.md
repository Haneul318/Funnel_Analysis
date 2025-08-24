# 🛍️ E-commerce User Funnel Analysis  
**SQL (PostgreSQL) + Tableau + Data Analytics**

## 📌 Project Overview
This project focuses on analyzing **user funnel performance** for an e-commerce platform.  
Using a dataset containing user actions across multiple funnel stages, we identified **conversion rates**, **drop-off rates**, and insights into **user behavior patterns**.  
The analysis includes **data cleaning**, **SQL queries** using **PostgreSQL (via DBeaver)**, and **interactive visualizations** created with **Tableau**.

---

## 📂 Dataset  
**Dataset Name:** User Funnels Dataset  
**File:** `user_data.csv`  
**Size:** ~453 KB  

| Column       | Description |
|-------------|------------|
| `user_id`   | Unique identifier for each user |
| `stage`     | Funnel stage the user reached (e.g., Homepage, Product Page, Cart, Checkout, Purchase) |
| `conversion`| Binary indicator: 1 if the user converted, 0 otherwise |

> **Source:** [Kaggle](https://www.kaggle.com/datasets/amirmotefaker/user-funnels-dataset/data) 


---

## 🛠️ Tools & Technologies  
| Tool / Tech      | Usage |
|------------------|-------|
| **PostgreSQL**   | SQL queries for data extraction and transformation |
| **DBeaver**      | PostgreSQL connection, query execution, and data export |
| **Tableau**      | Visualization of funnel stages, conversion rates, and drop-offs |
| **Excel**  | Quick exploratory checks and formatting |
| **GitHub**       | Hosting project documentation and code |

---

## 🔍 Limitations

While this project demonstrates a full end-to-end funnel analysis workflow, there are several **limitations** to consider:

1. **Limited Dataset Size**  
   - The analyzed dataset contained only **3 aggregated rows** summarizing user counts by stage.  
   - Because of this, advanced statistical modeling and deeper segmentation analysis were not feasible.

2. **Lack of Granular User-Level Data**  
   - Ideally, a complete funnel dataset would include **raw user-level event data** (e.g., `user_id`, `timestamp`, `session_id`, etc.).
   - Without granular behavioral data, we could not analyze session patterns, time-to-conversion, or multi-touch attribution.

3. **Funnel Dataset Availability**  
   - High-quality user funnel datasets are rarely publicly available due to **data privacy regulations** and **company confidentiality**.
   - This project used a simulated dataset intended for educational purposes, which may not reflect a real-world business scenario.

4. **Simplified Metrics**  
   - Step conversion rates and drop-off rates were calculated using simple formulas based on aggregated data.
   - In a production environment, we would validate these metrics with event-level tracking and robust A/B testing frameworks.

---

**Future Work**:  
To improve the quality and reliability of the analysis, future iterations could:
- Use a **larger, event-level dataset** with millions of user actions.
- Incorporate **cohort analysis**, **session duration**, and **multi-touch conversion attribution**.
- Connect directly to a **real-time analytics warehouse** for more scalable dashboards.

---
