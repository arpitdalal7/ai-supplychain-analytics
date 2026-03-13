
# 🚀 AI-Powered Supply Chain Analytics

An **end-to-end automated analytics pipeline** that collects vendor data, processes it, and generates supply chain insights using AI.

🔗 **Repository:** [https://github.com/arpitdalal7/ai-supplychain-analytics](https://github.com/arpitdalal7/ai-supplychain-analytics)

---

# 📌 Project Summary

Built an automated data pipeline for a fictional FMCG company **AtliQ Mart** to monitor supply chain performance.

The system automatically:

* Collects vendor CSV files from email
* Processes and stores data in a cloud database
* Uses AI tools to analyze supply chain metrics
* Generates insights for operational decisions

💡 The project demonstrates **data engineering, automation, and analytics skills** in a real-world scenario.

---

# ⚡ Key Impact

* ⏱ Reduced analysis time **45 min → 2 min**
* 🔄 Built **100% automated data pipeline**
* 📊 Tracked **15 supply chain KPIs**
* 🤖 Used AI tools to accelerate analysis
* 📉 Identified fulfillment issues in non-metro regions

---

# 🏗️ Architecture

Pipeline Workflow:

```
Vendor Email (CSV)
        ↓
n8n Automation
        ↓
PostgreSQL Database (Supabase)
        ↓
AI Analysis (Quadratic)
        ↓
Business Insights & KPI Dashboards
```

---

# 🛠️ Tech Stack

| Category        | Tools                |
| --------------- | -------------------- |
| Automation      | n8n                  |
| Database        | PostgreSQL, Supabase |
| Data Analysis   | Python, SQL          |
| AI Analytics    | Quadratic            |
| Version Control | Git                  |

---

# 📊 Key Supply Chain Metrics

The project tracks **15 performance metrics**, including:

### Delivery Performance

* On-Time Delivery %
* In-Full Delivery %
* **OTIF (On-Time-In-Full)**

### Operational Metrics

* Order Cycle Time
* Delivery Delay
* Perfect Order Rate

### Risk Metrics

* Backorder Rate
* Lead Time Variability
* Demand Variability

---

# 🎯 Key Insight

Analysis revealed **non-metro cities have significantly lower fulfillment performance**.

| Metric     | Metro    | Non-Metro |
| ---------- | -------- | --------- |
| In-Full %  | 92%      | 78%       |
| Cycle Time | 4.2 days | 5.8 days  |
| Backorders | Low      | High      |

📌 Indicates potential **inventory allocation issues in smaller cities**.

---

# 🤖 AI-Powered Analysis

AI prompts were used to answer business questions such as:

* Which product categories have the highest fulfillment issues?
* Which customers consistently miss OTIF targets?
* Where does lead-time variability impact service levels?

The AI tool generates **Python and SQL queries automatically**.

---

# 📂 Project Structure

```
AI-Supply-Chain-Analysis

workflows/
   n8n_email_to_database.json

database/
   schema_creation.sql

quadratic/
   supply_chain_analysis.grid

documentation/
   Presentation.pptx
```

---

# 🎓 Skills Demonstrated

### Data Engineering

* Workflow automation
* ETL pipeline development
* Database schema design

### Data Analytics

* KPI calculation
* SQL querying
* Python data analysis

### Business Analytics

* Supply chain performance analysis
* Operational insights
* Data-driven recommendations

---

# 👤 Author

**Arpit Dalal**


🔗 GitHub
[https://github.com/arpitdalal7](https://github.com/arpitdalal7)

🔗 LinkedIn
[https://www.linkedin.com/in/arpitdalal9/](https://www.linkedin.com/in/arpitdalal9/)

---

⭐ If you found this project useful, consider **starring the repository on GitHub**.

---

✅ If you'd like, I can also show you **3 small changes that can make this project look like a “Senior Data Analyst / Data Engineer level project” to recruiters**, which dramatically increases interview chances.
