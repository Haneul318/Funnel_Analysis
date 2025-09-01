# 🛍️ E-commerce User Funnel Analysis  
**SQL (PostgreSQL) + Tableau + Data Analytics**



## 📌 Project Overview
This project focuses on analyzing **user funnel performance** for an e-commerce platform.  
Using a dataset containing user actions across multiple funnel stages, we identified **conversion rates**, **drop-off rates**, and insights into **user behavior patterns**.  
The analysis includes **data cleaning**, **SQL queries** using **PostgreSQL (via DBeaver)**, and **interactive visualizations** created with **Tableau Public**.


---

## 📂 Dataset  
**Dataset Name:** User Funnels  Dataset  
**File:** `user_data.csv`  
**Size:** ~ 453 KB  

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



## 📊 SQL Query (DBeaver Screenshot)

The funnel metrics were calculated using SQL on **PostgreSQL** and executed via **DBeaver**.


![SQL Query](https://github.com/Haneul318/Funnel_Analysis/blob/main/Funnel-analysis/Data/processed.csv/dbeaver.png)


---



## 📈 Tableau Funnel Visualization

The Tableau dashboard visualizes:
- Users at each stage
- Cumulative conversion rate
- Step conversion rate
- Drop-off rate (darker colors = higher drop-offs)

![Funnel Dashboard](https://github.com/Haneul318/Funnel_Analysis/blob/main/Funnel-analysis/tableau/funnel%20analysis.png?raw=true)

> **Interactive Dashboard:** [🔗 View on Tableau Public](https://public.tableau.com/app/profile/haneul.kim8784/viz/Funnel_Analysis_17560160847610/Dashboard1?publish=yes)

---



## 🔍 Key Insights
| Stage        | Users | Cumulative Conversion | Step Conversion | Drop-off |
|-------------|-------|------------------------|-----------------|----------|
| Homepage    | 10,000 | 100%   | —   | —   |
| Product Page| 5,000  | 50%    | **50%** | **50%** |
| Cart        | 1,500  | 15%    | **30%** | **70%** |
| Checkout    | 450    | 4.5%   | **30%** | **70%** |
| Purchase    | 225    | 2.25%  | **50%** | **50%** |

### **Findings**
- **50% of users** drop off before visiting the **product page**.
- The **highest drop-off** occurs between **Product Page → Cart (70%)**.
- Another **70% drop-off** happens at **Cart → Checkout**.
- Of the **450 users** reaching checkout, only **225 completed purchases** (**50% step conversion**).

---

## 💡 Recommendations
| Area                | Observation | Recommendation |
|--------------------|------------|---------------|
**Product Page → Cart** | 70% drop-off | Improve product descriptions, optimize add-to-cart UX, highlight promotions |
**Cart → Checkout**    | 70% drop-off | Enable guest checkout, clarify pricing, improve payment flows |
**Checkout → Purchase**| 50% drop-off | Provide more payment methods, enhance security trust signals |

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



## 🚀 Future Improvements
- Use a **larger, event-level dataset** for deeper insights.
- Add **cohort analysis** for retention trends.
- Automate SQL → Tableau pipelines.
- Build a **real-time dashboard** using Tableau or Power BI.



---
**Author:** Sky  
📧 Contact: [E-mail](haneulkim1214@gmail.com)  
🔗 LinkedIn: [LinkedIn Profile](https://www.linkedin.com/in/haneul-kim-5a7572371/)







