# 🚀 RavenStack SaaS Executive Insights Dashboard

## 📊 Project Overview
This project addresses a critical business crisis for **RavenStack**, a B2B SaaS company facing a **70.4% churn rate**. As a Data Analyst, I built an end-to-end Power BI solution to identify why customers are leaving and how revenue is trending over time.

### 🎯 Business Goals:
* Identify the root causes of customer churn.
* Monitor **Monthly Recurring Revenue (MRR)** and **Growth Trends**.
* Evaluate Support Desk efficiency and its impact on retention.

---

## 🖼️ Dashboard Preview
![Final Dashboard](images/image1.png)
*Figure 1: Executive Dashboard featuring Dark Mode UI, MRR trends, and industry churn analysis.*

---

## 🛠️ Data Architecture & Modeling
The project utilizes a **Star Schema** to ensure high performance and accurate filtering across multiple dimensions. I performed extensive ETL in Power Query to resolve **Many-to-Many** relationship conflicts and ensure data integrity.

### The Data Model:
* **Fact Tables:** `Subscriptions`, `Churn_Events`, `Support_Tickets`.
* **Dimension Tables:** `Accounts`, `Calendar_Table` (Custom DAX).

![Data Model View](images/image2.png)
*Figure 2: The Star Schema showing 1:N relationships and filter flow.*

---

## 🧠 Advanced DAX Implementation
I developed several custom measures to provide the business with "Magic Numbers" that standard reporting couldn't capture:

| Metric | DAX Formula | Purpose |
| :--- | :--- | :--- |
| **Total MRR** | `SUM(ravenstack_subscriptions[mrr_amount])` | Tracks core monthly revenue. |
| **Churn Rate %** | `DIVIDE([Churned Accounts], [Total Customers], 0)` | Monitors customer attrition rate. |
| **MoM Growth** | `CALCULATE([MRR], DATEADD('Calendar'[Date], -1, MONTH))` | Compares current vs. previous month. |
| **Avg Resolution** | `AVERAGEX(Tickets, DATEDIFF([Open], [Closed], HOUR))` | Measures support desk efficiency. |

---

## 💡 Key Business Insights
After analyzing the data, three major findings were presented to the board:

1.  **The "Feature" Gap:** The **70.4% churn rate** is critical. The Treemap analysis confirms **"Features"** as the #1 reason for cancellation.
2.  **Industry Risk:** The **DevTools** and **EdTech** sectors are experiencing the highest volume of attrition.
3.  **Support Bottleneck:** Average ticket resolution time is **35.9 hours**. Combined with the feature complaints, this indicates high customer friction.

![Executive Summary](images/image4.png)
*Figure 3: Smart Narrative and Executive Summary highlighting core KPIs.*

---

## 🧪 Interactive Features
* **Detail Tooltips:** Hovering over the "Churn by Industry" bar chart reveals specific company names, industries, and their specific reason codes.
* **Custom UI:** Designed a high-contrast **Dark Mode** interface for executive-level presentation.
* **Dynamic Slicers:** Full interactivity allowing the user to filter by **Plan Tier** and **Date Range**.

![Tooltip Detail](images/image3.png)
*Figure 4: Detailed tooltip view showing granular account-level data.*

---

## 🚀 How to Use
1. Clone this repository.
2. Open the `.pbix` file in **Power BI Desktop**.
3. Use the **Date Slider** or **Tier Plan** slicer to explore the data.

---

### 📝 Project Conclusion
To stabilize RavenStack's revenue, the data suggests a pivot toward improving core product features and reducing support response times in the DevTools sector.
