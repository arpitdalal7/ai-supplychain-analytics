# AI Supply Chain Analytics 🚀

[
[
[
[

**Automated AI-powered supply chain analytics pipeline** using n8n, Supabase, and Quadratic.

***

## 📖 Quick Navigation

- [Overview](#overview)
- [Demo](#demo)
- [Features](#features)
- [Architecture](#architecture)
- [Setup](#setup)
- [Usage](#usage)
- [KPIs](#kpis)
- [Files](#files)
- [License](#license)

***

## Overview {#overview}

**Transform vendor emails into supply chain insights** in minutes, not hours.

```
📧 Emails → ⚡ n8n → 🗄️ Supabase → 🤖 Quadratic AI → 📊 Insights
```

**For:** AtliQ Mart (FMCG company, India + USA operations)

**Solves:**
- Manual CSV processing
- Delayed KPI reporting
- Poor delivery visibility
- Revenue loss tracking

**Results:**
- **OTIF%** + **Fill Rates** + **Cycle Time**
- Customer performance gaps
- Category backorder alerts
- **10x faster** analysis

***

## Demo {#demo}




***

## Features {#features}

✅ **Fully Automated ETL** - Email → Database  
✅ **15+ Supply Chain KPIs** - SCOR aligned  
✅ **AI Data Cleaning** - Natural language prompts  
✅ **Multi-currency** - USD ↔ INR  
✅ **Real-time Insights** - Customer, product, location analysis  
✅ **Zero DevOps** - Free tiers work perfectly  

***

## Architecture {#architecture}

```
Vendors ─📧─> Gmail ─⚡─> n8n Workflow ─🗄️─> Supabase PostgreSQL
                                                           ↓
                                              🤖 Quadratic AI
                                                           ↓
                                              📊 Business KPIs
```

**n8n:** Email trigger → CSV extract → DB insert  
**Supabase:** Star schema (facts + dimensions)  
**Quadratic:** AI prompts → Python/SQL → Insights

***

## Setup {#setup}

### 1. Database (~3 min)
```
supabase.com → New Project
Run database/schema.sql
```

### 2. n8n (~2 min)
```
npx n8n
Import workflows/email_to_db.json
Configure Gmail + Supabase
```

### 3. Test Data (~1 min)
```
python scripts/load_sample.py
```

### 4. Analyze (~2 min)
```
Quadratic → Connect Supabase → Run prompts
```

**Total: ~8 minutes** ✅

***

## Usage {#usage}

### Run Analysis Prompts

**KPIs:**
```
"Calculate: OTIF%, Line Fill Rate, Volume Fill Rate, Cycle Time, Backorders"
```

**Customers:**
```
"Top 5 customers by value + OTIF%, city, name"
```

**Problems:**
```
"Categories with highest backorders + lowest in_full%"
```

**Gaps:**
```
"Metro vs Non-Metro: in_full%, OT%, cycle_time"
```

***

## KPIs {#kpis}

| Metric | Formula | Target |
|--------|---------|--------|
| **OTIF%** | On-Time **AND** In-Full | ≥85% |
| **Line Fill** | Complete lines/total | ≥95% |
| **Volume Fill** | Delivered/ordered qty | ≥98% |
| **Cycle Time** | Order→delivery days | ≤5 days |



***

## Files {#files}

```
├── workflows/
│   └── email_to_db.json     # n8n automation
├── database/
│   └── schema.sql          # Star schema
├── quadratic/
│   └── analysis.grid       # AI workbook
├── scripts/
│   └── load_sample.py      # Test data
├── screenshots/            # Visuals
└── README.md
```

**Download → Run → Analyze** in <15 min!

***

## License {#license}

[MIT License](LICENSE) - Use freely!

```
Copyright (c) 2026 Arpit Dalal
```

***

<div align="center">


⭐ **Star if helpful!**

</div>
```
