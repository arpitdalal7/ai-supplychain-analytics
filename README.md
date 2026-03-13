```markdown
<div align="center">
  <img src="https://user-images.githubusercontent.com/123456789/27987654-8b3d2f8a-64e5-11e7-9c8e-2a8c8b8c8b8c.png" width="100" alt="AI Supply Chain Analytics">
  <h1>AI Supply Chain Analytics</h1>
</div>

<p align="center">
  <img alt="License" src="https://img.shields.io/badge/License-MIT-yellow.svg">
  <img alt="Python" src="https://img.shields.io/badge/Python-3.8+-blue.svg">
  <img alt="n8n" src="https://img.shields.io/badge/n8n-Automation-orange.svg">
  <img alt="Supabase" src="https://img.shields.io/badge/Supabase-DB-purple.svg">
  <img alt="Quadratic" src="https://img.shields.io/badge/Quadratic-AI-green.svg">
</p>

<div align="center">
  <strong>
    <a href="#overview">Overview</a>
    | <a href="#features">Features</a>
    | <a href="#tech-stack">Tech Stack</a>
    | <a href="#quick-start">Quick Start</a>
    | <a href="#usage">Usage</a>
    | <a href="#structure">Structure</a>
    | <a href="#contributing">Contributing</a>
    | <a href="#license">License</a>
    | <a href="#contact">Contact</a>
  </strong>
</div>

---

## Overview {#overview}

**AI Supply Chain Analytics** is an automated pipeline that transforms raw order data into actionable supply chain insights using modern AI tools.

**What it does:**
```
Email (CSV) → n8n Automation → Supabase DB → Quadratic AI → Business Insights
```

**Business Value:**
- ✅ **15+ Supply Chain KPIs** (OTIF, Fill Rates, Cycle Time)
- ✅ **Zero manual data entry** - fully automated
- ✅ **10-15x faster analysis** using AI prompts
- ✅ **Real-time monitoring** of delivery performance

---

## Features {#features}

### 🚀 Key Capabilities
- **Automated Data Collection** - Email → Database in 2 minutes
- **AI Data Cleaning** - Natural language prompts generate Python code
- **Supply Chain KPIs** - OTIF%, On-Time, In-Full, Backorders, Cycle Time
- **Business Insights** - Customer gaps, product issues, demand patterns
- **Multi-currency** - USD ↔ INR conversion for global operations

### 📊 Calculated Metrics
| KPI | Purpose |
|-----|---------|
| **OTIF%** | On-Time + In-Full (most important) |
| **Line Fill Rate** | Perfect line fulfillment |
| **Volume Fill Rate** | Total quantity delivered |
| **Cycle Time** | Order to delivery speed |
| **Backorder Qty** | Unfulfilled demand |

---

## Tech Stack {#tech-stack}

```
Automation: n8n + Gmail API
Database: Supabase (PostgreSQL)
Analytics: Quadratic (AI Spreadsheet)
Data: Python + pandas + SQL
```

**No complex DevOps required** - all tools have free tiers!

---

## Quick Start {#quick-start}

### 1. Clone & Setup
```bash
git clone https://github.com/arpitdalal7/ai-supplychain-analytics.git
cd ai-supplychain-analytics
```

### 2. Database (Supabase)
1. Create free account: [supabase.com](https://supabase.com)
2. Run `database/schema.sql`
3. Note connection string

### 3. n8n Workflow
1. Start n8n: `npx n8n`
2. Import `workflows/email_to_database.json`
3. Add Gmail + Supabase credentials

### 4. Load Sample Data
```bash
python scripts/load_sample_data.py
```

### 5. Analyze with Quadratic
1. Open [quadratichq.com](https://quadratichq.com)
2. Connect Supabase database
3. Import `quadratic/supply_chain_analysis.grid`
4. Run AI prompts!

---

## Usage {#usage}

### Step-by-Step Analysis

**1. Calculate KPIs:**
```
"Create KPIs: Total Orders, OTIF%, Line Fill Rate, Volume Fill Rate, Cycle Time"
```

**2. Top Customers:**
```
"Show top 5 customers by order value with OTIF%, city, customer name"
```

**3. Problem Areas:**
```
"Find product categories with highest backorders and lowest in_full%"
```

**4. Metro vs Non-Metro:**
```
"Compare Metro vs Non-Metro: in_full%, on_time%, cycle_time, backorders"
```

---

## Project Structure {#structure}

```
ai-supplychain-analytics/
├── data/                 # Sample CSV files
├── database/             # Schema & seed data
│   └── schema.sql
├── workflows/            # n8n automation
│   └── email_to_db.json
├── quadratic/            # AI analysis workbook
│   └── analysis.grid
├── scripts/              # Python utilities
│   └── load_data.py
├── docs/                 # Documentation
└── README.md
```

---

## Screenshots

### n8n Workflow
![Workflow](docs/screenshots/n8n-workflow.png)

### Data Cleaning (AI Prompt)
![Data Cleaning](docs/screenshots/data-cleaning.png)

### KPI Dashboard
![KPIs](docs/screenshots/kpi-dashboard.png)

### Business Insights
![Insights](docs/screenshots/business-questions.png)

---

## Contributing {#contributing}

1. **Fork** the repository
2. **Create** feature branch: `git checkout -b feature/amazing-feature`
3. **Commit** changes: `git commit -m 'Add: amazing feature'`
4. **Push** to branch: `git push origin feature/amazing-feature`
5. **Open Pull Request**

**Guidelines:**
- Write clear commit messages
- Add comments to complex code
- Update documentation
- Test before submitting

---

## License {#license}

This project is licensed under the [MIT License](LICENSE).

```
MIT License - Free to use, modify, and distribute
Copyright (c) 2026 Arpit Dalal
```

---

## Acknowledgments {#acknowledgments}

**Special thanks to:**

<div align="center">
  <a href="https://www.youtube.com/c/codebasics">
    <img src="https://img.shields.io/badge/Codebasics-YouTube-red?style=for-the-badge&logo=youtube" alt="Codebasics">
  </a>
</div>

**Codebasics YouTube Channel** - Project mentoring, tutorials, and supply chain analytics challenges.

---

## Contact {#contact}

**Arpit Dalal**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/arpitdalal9/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black?style=for-the-badge&logo=github)](https://github.com/arpitdalal7)

**Repository:** [arpitdalal7/ai-supplychain-analytics](https://github.com/arpitdalal7/ai-supplychain-analytics)

<div align="center">
  <br>
  ⭐ **Star this repo if you found it helpful!**
  <br><br>
  <img src="https://user-images.githubusercontent.com/123456789/27987654-8b3d2f8a-64e5-11e7-9c8e-2a8c8b8c8b8c.png" width="200">
</div>
```

**Ready to copy-paste directly into GitHub!** 

This simplified version includes:
✅ **Clickable table of contents** at top
✅ **All essential sections** in compact format
✅ **Professional badges** and styling
✅ **Clear quick-start** instructions
✅ **Image placeholders** ready for screenshots
✅ **MIT License** included
✅ **Codebasics credits**
✅ **Perfect for recruiters** - shows skills + results

Just add your screenshot images to `docs/screenshots/` folder and update the image paths
