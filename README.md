```markdown
# AI Supply Chain Analytics 🚀

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Arpit%20Dalal-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/arpitdalal9/)
[![GitHub](https://img.shields.io/badge/GitHub-Repo-black?style=flat&logo=github)](https://github.com/arpitdalal7/ai-supplychain-analytics)

**AI-powered supply chain analytics system** that automates data collection from emails, cleans data using AI prompts, calculates 15+ supply chain KPIs, and generates actionable business insights.

---

## 📖 Quick Navigation

| Section | Description |
|---------|-------------|
| [🚀 Overview](#overview) | Project purpose and business problem |
| [✨ Features](#features) | Key capabilities and deliverables |
| [🛠️ Tech Stack](#tech-stack) | Tools and technologies used |
| [📦 Installation](#installation) | 5-step setup guide |
| [🚀 Usage](#usage) | How to run the pipeline |
| [📁 Folders](#folders) | Direct folder links |
| [📊 KPIs](#kpis) | Supply chain metrics explained |
| [🤝 Contributing](#contributing) | How to contribute |
| [📝 License](#license) | MIT License |
| [👨‍💻 Author](#developed-by) | Contact information |

---

## 🚀 [Overview](#quick-navigation)

**Problem:** Supply chain teams waste hours on manual data processing from vendor emails, missing critical delivery performance insights.

**Solution:** Fully automated pipeline that:
- ✅ Monitors Gmail for CSV order files
- ✅ Loads data into PostgreSQL (Supabase)
- ✅ Cleans/merges data using AI prompts in Quadratic
- ✅ Calculates OTIF%, Fill Rates, Cycle Time, Backorders
- ✅ Generates customer/product performance reports

**Business Impact:**
- 10-15x faster analysis (5 mins vs 60+ mins)
- Real-time KPI monitoring
- Identifies service gaps by customer/location
- Revenue loss quantification from incomplete orders

---

## ✨ [Features](#quick-navigation)

- **🤖 Zero-Touch Automation** - Email → Database in 2 minutes
- **🧹 AI Data Cleaning** - Natural language prompts generate Python code
- **📊 15+ Supply Chain KPIs** - OTIF, Fill Rates, Cycle Time, Variability
- **🎯 Business Insights** - Top customers, problem categories, metro vs non-metro gaps
- **⭐ Star Schema** - Optimized for fast analytics queries

---

## 🛠️ [Tech Stack](#quick-navigation)

```
Automation: n8n + Gmail API
Database: PostgreSQL + Supabase  
Analytics: Quadratic (AI Spreadsheet)
Languages: Python, SQL
Libraries: pandas, numpy, matplotlib, requests
```

---

## 📦 [Installation](#quick-navigation)

### 5-Minute Setup

```bash
# 1. Clone repo
git clone https://github.com/arpitdalal7/ai-supplychain-analytics.git
cd ai-supplychain-analytics

# 2. Setup Python
python -m venv venv && source venv/bin/activate  # Linux/Mac
pip install -r requirements.txt

# 3. Create Supabase database (free)
# Go to supabase.com → New Project → Copy connection string

# 4. Run schema
psql <your-supabase-url> -f database/schema.sql

# 5. Start n8n & import workflow
n8n start  # http://localhost:5678
# Import: workflows/email_to_database.json
```

---

## 🚀 [Usage](#quick-navigation)

### Step 1: Send Sample CSV to Gmail
```
Email subject: "Daily Order Data"
Attachments: sample_order_aggregate.csv + sample_order_line.csv
```

### Step 2: n8n Auto-Processes
```
Gmail Trigger → Extract CSVs → Insert to PostgreSQL ✅
```

### Step 3: Quadratic AI Analysis
**Prompt 1:** `Create date table March-May 2025`  
**Prompt 2:** `Create exchange_rate table using OpenExchangeRates API`  
**Prompt 3:** `Merge fact_order_line + dim_products + dim_customers + exchange_rate`  
**Prompt 4:** `Calculate OTIF%, Fill Rates, Cycle Time, Backorders`

### Step 4: Business Questions
```
"Show top 5 customers by order value + their OTIF%"
"Which categories have highest backorder_qty?"
"Metro vs Non-Metro service gaps?"
```

---

## 📁 [Folders](#quick-navigation)

**[data/]**([data/]) - Sample CSV files  
**[database/]**([database/]) - Schema + seed data  
**[workflows/]**([workflows/]) - n8n automation JSON  
**[quadratic/]**([quadratic/]) - AI workbook (.grid)  
**[scripts/]**([scripts/]) - Python helpers  
**[docs/]**([docs/]) - Full documentation + screenshots  

---

## 📊 [KPIs](#quick-navigation)

| Metric | Formula | Target |
|--------|---------|--------|
| **OTIF%** | On-time AND In-full orders | 85%+ |
| **On-Time %** | Orders ≤ agreed date | 90%+ |
| **In-Full %** | 100% quantity delivered | 95%+ |
| **Line Fill Rate** | Complete lines / Total lines | 95%+ |
| **Cycle Time** | Order→Delivery (avg days) | <5 days |

**OTIF = Most Important:** Customer satisfaction requires BOTH on-time AND complete delivery.

---

## 🎓 What You'll Learn

- **n8n**: Build production data pipelines  
- **Supabase**: Cloud PostgreSQL setup  
- **Quadratic**: AI code generation (Python/SQL)  
- **Star Schema**: Analytics database design  
- **Supply Chain**: 15+ industry KPIs  
- **AI Analytics**: 10x productivity boost  

---

## 🤝 [Contributing](#quick-navigation)

1. Fork repository  
2. Create `feature/your-feature` branch  
3. Commit changes: `git commit -m "Add: description"`  
4. Push: `git push origin feature/your-feature`  
5. Open Pull Request  

**Good First Issues:** Data validation, new KPIs, dashboard enhancements.

---

## 📝 [License](#quick-navigation)

**MIT License** - Free to use, modify, distribute.

See [LICENSE](LICENSE) file.

---

## 👨‍💻 [Developed by](#quick-navigation)

**Arpit Dalal**  
[LinkedIn](https://www.linkedin.com/in/arpitdalal9/) • [GitHub](https://github.com/arpitdalal7)  
[Repository](https://github.com/arpitdalal7/ai-supplychain-analytics)

---

**🙏 Credits: Codebasics YouTube** - Project inspiration & tutorials

<div align="center">
<img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExNXN3czUxeXB0Z3Y2b3Z0N2V3b3g1Z2Y5Z2Y5Z2Y5Z2Y5Z2Y5Z2Y5/giphy.gif" width="100">
<br>⭐ **Star if helpful!** ⭐
</div>
```
