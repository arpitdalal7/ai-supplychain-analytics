```markdown
<div align="center">
  
  <img src="https://github.com/arpitdalal7/ai-supplychain-analytics/raw/main/assets/logo.png" alt="AI Supply Chain Analytics" width="120"/>
  
  <h1>AI-Driven Supply Chain Analytics</h1>
  
  <p><b>Automated Pipeline</b> | <b>15+ SCOR KPIs</b> | <b>Real-Time Insights</b></p>
  
</div>

<p align="center">
  <a href="#overview"><img src="https://img.shields.io/badge/Overview-📋-blue?style=for-the-badge" alt="Overview"></a>
  <a href="#architecture"><img src="https://img.shields.io/badge/Architecture-🏗️-green?style=for-the-badge" alt="Architecture"></a>
  <a href="#automation"><img src="https://img.shields.io/badge/n8n-⚡-orange?style=for-the-badge" alt="n8n"></a>
  <a href="#kpis"><img src="https://img.shields.io/badge/KPIs-📊-purple?style=for-the-badge" alt="KPIs"></a>
  <a href="#insights"><img src="https://img.shields.io/badge/Insights-💡-pink?style=for-the-badge" alt="Insights"></a>
  <a href="#setup"><img src="https://img.shields.io/badge/Setup-🚀-yellow?style=for-the-badge" alt="Setup"></a>
  <a href="#files"><img src="https://img.shields.io/badge/Files-📁-gray?style=for-the-badge" alt="Files"></a>
</p>

---

## 📋 Overview {#overview}

**Transform raw order emails into supply chain intelligence** using AI-powered automation.

**The Problem:** Manual CSV processing, delayed insights, poor delivery visibility

**The Solution:** 
```
Emails → n8n → Supabase → Quadratic AI → Actionable KPIs
```

**Results:**
- **OTIF%** tracking (On-Time + In-Full)
- **Backorder alerts** by category
- **Customer performance** gaps
- **Metro vs Non-Metro** analysis
- **10x faster** analysis with AI prompts

**Business:** AtliQ Mart (FMCG) - 3 locations (India + USA)

---

## 🏗️ Architecture {#architecture}

```
📧 Vendor Emails (CSV)
     ↓
⚡ n8n Automation (Extract + Clean)
     ↓
🗄️ Supabase PostgreSQL (Star Schema)
     ↓
🤖 Quadratic AI (Analysis + KPIs)
     ↓
📊 Business Insights + Dashboards
```

**Key Components:**
- **n8n** - Email monitoring & ETL
- **Supabase** - Cloud PostgreSQL
- **Quadratic** - AI spreadsheet analytics

---

## ⚡ Automation Workflow (n8n) {#automation}

![n8n Workflow](https://github.com/arpitdalal7/ai-supplychain-analytics/raw/main/screenshots/workflow.png)

**Daily Automation:**
1. **Gmail Trigger** ← Monitors vendor emails
2. **CSV Extract** ← Downloads Order Aggregate + Line Items
3. **Data Clean** ← JSON conversion + validation
4. **DB Insert** ← fact_aggregate + fact_order_line tables

**Zero manual work** - runs 24/7!

---

## 🧹 Data Processing {#datacleaning}

### AI-Powered Cleaning (Quadratic)

![Data Cleaning](https://github.com/arpitdalal7/ai-supplychain-analytics/raw/main/screenshots/data-cleaning.png)

**Single Prompt → Complete Pipeline:**

```
"Load fact_order_line + dim_products + dim_customers + exchange_rate
Clean IDs, dates, nulls
Merge tables
Calculate: backorder_qty, cycle_time, in_full%, OTIF flags
Create fact_summary table"
```

**Generated Features:**
- `backorder_qty = order_qty - delivery_qty`
- `order_cycle_time_days`
- `delivery_delay_days`
- `in_full_percent`
- `on_time_flag`

---

## 📊 Supply Chain KPIs {#kpis}

**15 SCOR-aligned metrics** calculated automatically:

| KPI | Formula | Target |
|-----|---------|--------|
| **OTIF%** | On-Time **AND** In-Full | >85% |
| **Line Fill Rate** | Complete lines / Total lines | >95% |
| **Volume Fill Rate** | Delivered qty / Ordered qty | >98% |
| **Cycle Time** | Order → Delivery (days) | <5 days |
| **Backorder Qty** | ∑(order_qty - delivery_qty) | Minimize |

![KPI Dashboard](https://github.com/arpitdalal7/ai-supplychain-analytics/raw/main/screenshots/kpis.png)

---

## 💡 Business Insights {#insights}

### AI Prompts → Actionable Answers

**Prompt 1: Top Customers**
```
"Top 5 customers by order value + OTIF%, city, name"
```

**Prompt 2: Problem Categories**
```
"5 categories with highest backorders + lowest in_full%"
```

**Prompt 3: Service Gaps**
```
"Metro vs Non-Metro: in_full%, OT%, cycle_time, backorders"
```

**Prompt 4: Revenue Impact**
```
"Revenue loss = backorder_qty × unit_price (INR)"
```

![Business Questions](https://github.com/arpitdalal7/ai-supplychain-analytics/raw/main/screenshots/business-questions.png)

**Key Findings:**
- **Non-metro cities** have 14% lower In-Full rates
- **Beverages** category has highest backorders
- **2 customers** consistently miss OTIF targets
- **₹12.5M revenue loss** from undelivered orders

---

## 🚀 Quick Setup {#setup}

### 1. Database (5 min)
```
supabase.com → New Project → Copy Connection String
database/schema.sql → Run in SQL Editor
```

### 2. n8n (3 min)
```
npx n8n → Import workflows/email_to_db.json
Add Gmail + Supabase credentials → Activate
```

### 3. Sample Data (1 min)
```
python scripts/load_sample_data.py
```

### 4. Analyze (2 min)
```
Quadratic → Connect Supabase → Import analysis.grid
Run AI prompts → Get insights instantly!
```

**Total Setup: <15 minutes** 🎉

---

## 📁 Repository Files {#files}

```
ai-supplychain-analytics/
├── workflows/
│   └── email_to_db.json          # n8n automation
├── database/
│   └── schema.sql               # Star schema
├── quadratic/
│   └── analysis.grid            # AI workbook
├── scripts/
│   └── load_sample_data.py      # Data loader
├── docs/
│   └── screenshots/             # Visuals
└── README.md
```

**Download & Run Today!** 👆

---

## 📈 How AI Boosted Productivity {#ai-boost}

**Traditional Analysis:** 4-6 hours  
**AI Pipeline:** 15-20 minutes  

**Speed Gains:**
```
Manual SQL:     45min → AI Prompt:  2min
Data Cleaning:  60min → AI Code:    3min
Charts:         30min → Auto-Gen:   1min
KPIs:           90min → One Prompt: 4min
```

**Result:** **12-17x faster** analytics!

---

## 🎯 Recommendations {#recommendations}

1. **Fix Non-Metro Fulfillment** - 14% In-Full gap vs Metro
2. **Prioritize Beverages** - Highest backorder category
3. **Alert on Demand Surges** - Weeks with >30% swings
4. **Track 2 Key Customers** - Missing OTIF targets consistently
5. **Weekly Lead Time Review** - Variability >3 days = risk

---

## 🙌 Credits

**Huge thanks to:**

[![Codebasics](https://img.shields.io/badge/Codebasics-YouTube-red?style=for-the-badge&logo=youtube)](https://www.youtube.com/c/codebasics)

**Codebasics** - Project structure, prompts, and supply chain challenges

**Tools:**
- [n8n](https://n8n.io) - Automation
- [Supabase](https://supabase.com) - Database  
- [Quadratic](https://quadratic.to) - AI Analytics

---

## 📄 License

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**MIT License** - Free to use, modify, distribute.

---

<div align="center">

**⭐ Star if helpful!**  
**👨‍💼 Arpit Dalal** | [LinkedIn](https://linkedin.com/in/arpitdalal9)  
**📂 Repo:** [ai-supplychain-analytics](https://github.com/arpitdalal7/ai-supplychain-analytics)

</div>
```
