```markdown
<div align="center">
<img src="https://github.com/arpitdalal7/ai-supplychain-analytics/raw/main/banner.png" alt="AI Supply Chain Analytics" width="100%"/>
</div>

# 📦 AI-Driven Supply Chain Analytics
[![GitHub stars](https://img.shields.io/github/stars/arpitdalal7/ai-supplychain-analytics?style=social)](https://github.com/arpitdalal7/ai-supplychain-analytics)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Follow-blue?style=social&logo=linkedin)](https://linkedin.com/in/arpitdalal9)

**Automated pipeline** transforming vendor emails into real-time supply chain intelligence using **n8n**, **Supabase**, and **Quadratic AI**.

---

## 📚 Quick Navigation

| Section | Description |
|---------|-------------|
| [🚀 Overview](#overview) | Project purpose & business problem |
| [🛠️ Architecture](#architecture) | Email → AI Insights pipeline |
| [⚡ n8n Workflow](#n8n-workflow) | [Workflow Screenshot](screenshots/workflow.png) |
| [🧹 Data Cleaning](#data-cleaning) | [AI Prompt Example](screenshots/data-cleaning.png) |
| [📊 KPIs](#kpis) | 15 SCOR-aligned metrics |
| [💡 Insights](#insights) | [Business Questions](screenshots/business-questions.png) |
| [🚀 Setup](#setup) | 15-min local deployment |
| [📁 Files](#files) | Download & run instantly |

---

## 🚀 Overview {#overview}

**AtliQ Mart** (FMCG company) needed **supply chain visibility** across India + USA operations.

**Challenges:**
- Manual CSV processing from vendor emails
- No real-time OTIF tracking
- Poor demand forecasting
- Inventory shortages

**Solution:** Fully automated pipeline delivering:
```
📧 Emails → ⚡ n8n → 🗄️ Supabase → 🤖 Quadratic AI → 📊 Insights
```

**Results:**
- **OTIF%** monitoring (85%+ target)
- Backorder alerts by category
- Metro vs Non-Metro gaps
- **12x faster** analysis

---

## 🛠️ Architecture {#architecture}

```
📧 Vendor CSVs (Daily)
    ↓ Gmail Trigger
⚡ n8n (Extract → Clean → Load)
    ↓ PostgreSQL
🗄️ Supabase (Star Schema)
    ↓ SQL Queries
🤖 Quadratic (AI Prompts → KPIs)
    ↓ Visuals + Insights
📊 Executive Dashboard
```

**3 Tools. 15 Minutes Setup. Zero Manual Work.**

---

## ⚡ n8n Workflow {#n8n-workflow}

![n8n Workflow](https://github.com/arpitdalal7/ai-supplychain-analytics/raw/main/screenshots/workflow.png)

**Automation Steps:**
1. **Gmail** monitors vendor emails
2. **Extract** Order Aggregate + Line Items CSVs
3. **Parse** CSV → JSON
4. **Insert** into `fact_aggregate` + `fact_order_line`

**Runs automatically** - new data available in **2 minutes**.

---

## 🧹 Data Cleaning {#data-cleaning}

**Quadratic AI Prompt → Instant Python Code:**

```
"Load fact_order_line + dim_products + customers + exchange_rate
Clean IDs, dates, nulls
Merge tables
Calculate backorder_qty, cycle_time, OTIF flags
Create fact_summary"
```

![Data Cleaning Prompt](https://github.com/arpitdalal7/ai-supplychain-analytics/raw/main/screenshots/data-cleaning.png)

**Generated Columns:**
```
backorder_qty = order_qty - delivery_qty
in_full% = (delivery_qty/order_qty) × 100
on_time_flag = 1 if on_time else 0
```

---

## 📊 Supply Chain KPIs {#kpis}

**15 SCOR-aligned metrics** calculated automatically:

| KPI | Formula | Target |
|-----|---------|--------|
| **OTIF%** | On-Time **+** In-Full | **85%+** |
| **Line Fill Rate** | Complete lines/total | **95%+** |
| **Volume Fill Rate** | Delivered qty/ordered | **98%+** |
| **Cycle Time** | Order→Delivery (days) | **<5 days** |

![KPI Dashboard](https://github.com/arpitdalal7/ai-supplychain-analytics/raw/main/screenshots/kpis.png)

---

## 💡 Business Insights {#insights}

**AI Prompts → Instant Answers:**

```
"Top 5 customers by value + OTIF% + city"
"Categories with highest backorders"
"Metro vs Non-Metro service gaps"
"Revenue loss from undelivered orders"
```

![Business Analysis](https://github.com/arpitdalal7/ai-supplychain-analytics/raw/main/screenshots/business-questions.png)

**Key Findings:**
```
❌ Non-metro: 14% lower In-Full rate
❌ Beverages: Max backorders
⚠️ 2 customers missing OTIF targets
💰 ₹12.5M revenue at risk
```

---

## 🚀 15-Min Setup {#setup}

### Database
```
supabase.com → New Project (Free)
→ Run database/schema.sql
```

### n8n
```
npx n8n
→ Import workflows/email_to_db.json
→ Add Gmail + Supabase credentials
```

### Sample Data
```
python scripts/load_sample_data.py
```

### Analyze
```
Quadratic → Connect Supabase
→ Import analysis.grid
→ Run prompts → Get insights!
```

---

## 📁 Key Files {#files}

```
├── workflows/email_to_db.json     # n8n automation
├── database/schema.sql           # Star schema
├── quadratic/analysis.grid       # AI workbook
├── scripts/load_sample_data.py   # Sample loader
└── screenshots/                  # Visual demos
```

**Download → Run → Analyze Instantly!**

---

## 🎯 Key Takeaways {#takeaways}

```
✅ Zero manual data entry
✅ 12x faster analysis (AI prompts)
✅ Real-time OTIF monitoring
✅ Metro/Non-Metro gap analysis
✅ Revenue loss quantification
✅ Actionable recommendations
```

---

## 🙌 Credits

**Mentorship & Project Structure:**

[![Codebasics](https://img.shields.io/badge/Codebasics-YouTube-red?style=for-the-badge&logo=youtube)](https://youtube.com/c/codebasics)

**Tools:**
[n8n](https://n8n.io) | [Supabase](https://supabase.com) | [Quadratic](https://quadratic.to)

---

## 📄 License

[![MIT License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**MIT** - Use freely for commercial/personal projects.

---

<div align="center">

**👨‍💼 Arpit Dalal**  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=for-the-badge&logo=linkedin)](https://linkedin.com/in/arpitdalal9)  
[![GitHub](https://img.shields.io/badge/GitHub-Star-black?style=for-the-badge&logo=github)](https://github.com/arpitdalal7/ai-supplychain-analytics)

⭐ **Star if helpful!** 🚀

</div>
```
