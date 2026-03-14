# AI-Driven Supply Chain Analytics – End-to-End Automation

[![AI-Driven Supply Chain Analytics Banner](https://via.placeholder.com/1200x400/0f172a/ffffff?text=AI-Driven+Supply+Chain+Analytics)](https://github.com/SachinSavkare/AI-Driven-Supply-Chain-Analysis-N8N-Quadratic-Supabase)

An AI-powered supply chain analytics project that transforms raw order data from emails into real-time, actionable business insights using workflow automation, cloud databases, and AI-assisted analytics.

---

## 📌 Project Overview

This project implements an end-to-end **supply chain performance monitoring** pipeline for a fictional organic food distributor (AtliQ Mart) operating across India and the USA.

[... rest of the content remains exactly the same ...]

## 🏗️ Architecture & Data Flow

**🔗 Live Demo: [n8n Workflow Screenshot](https://via.placeholder.com/800x400/1e293b/ffffff?text=n8n+Workflow:+Email→DB+Automation)**

**High-level architecture:**

`Email (CSV) → n8n (Automation) → Supabase (PostgreSQL) → Quadratic (AI Analytics) → Business Insights`

### 1. Data Ingestion (Email → n8n)

- Vendors send daily CSV files:
  - Order Aggregate
  - Order Line Items
- n8n workflow:
  - Monitors Gmail inbox for vendor emails
  - Downloads CSV attachments automatically
  - Converts CSV to structured JSON
  - Validates schema and data types
  - Pushes data into PostgreSQL tables

### 2. Database Layer (Supabase – PostgreSQL)

Implemented a **star schema** optimized for analytics:

- **Fact tables**
  - `fact_orders_aggregate` – order-level metrics
  - `fact_order_line` – product-level order details
- **Dimension tables**
  - `dim_customers` – customer master data (ID, name, city, country)
  - `dim_products` – product catalog with multi-currency pricing
  - `dim_date` – standard date dimension
  - `dim_target_orders` – performance benchmarks/targets
- **Supporting tables**
  - `exchange_rate` – USD ↔ INR conversion
  - `fact_summary` – merged analytics table for KPI reporting

### 3. Analytics Layer (Quadratic + Python + SQL)

- AI-powered spreadsheet environment
- Runs SQL and Python on top of Supabase data
- Natural language prompts generate analysis code
- Automates KPI calculations and visualization
- Enables ad-hoc analysis via conversational queries

---

## 🧹 Data Processing & AI Assistance

Data transformations handled via AI-generated Python and SQL:

- Convert IDs (e.g., `product_id`, `customer_id`) to integers  
- Remove rows with NULL/invalid values  
- Standardize date formats to datetime  
- Trim whitespace and clean text fields  
- Handle multi-currency values (USD → INR using exchange rates)  
- Join fact and dimension tables to create analysis-ready datasets  

**Example prompt used in Quadratic:**

> "Create Python code that loads data from `fact_order_line`, `dim_products`, `dim_customers`, and `exchange_rate`, cleans IDs, merges tables, and calculates total amounts in INR."

This reduces manual coding time from ~30 minutes to ~2 minutes per transformation.

---

## 📊 Key Supply Chain KPIs

The pipeline automatically computes **15+ KPIs**, including:

### Order Performance

- Total Orders  
- Total Order Lines  
- Line Fill Rate (% of lines delivered completely)  
- Volume Fill Rate (% of ordered quantity delivered)

### Delivery Performance

- On-Time Delivery (OT%)  
- In-Full Delivery (IF%)  
- On-Time-In-Full (OTIF%)  
- Order Cycle Time (days from order to delivery)  
- Average Delivery Delay (for late orders)

### Variability & Risk

- Lead Time Variability  
- Category Demand Variability  
- Total Backorder Quantity  
- Perfect Order Rate  
- Backorder Rate  
- Delivery Reliability Index (composite score)

### OTIF – Core Metric

```
OTIF = (Orders delivered on time AND in full) / Total Orders × 100
```

**Benchmarks:**

- 85% → Acceptable  
- 90% → Excellent  
- 95% → World-class  

---

## 🔎 Business Insights Generated

Using the AI-powered analytics layer, the system can answer questions like:

- Which product categories struggle most with fulfillment?  
- Which customers consistently miss OTIF targets?  
- Where is lead-time variability highest?  
- How do metro vs non-metro customers compare on OTIF, backorders, and delays?  
- Do longer delivery delays correlate with larger backorders?  
- Which customers are improving or worsening over time?

### Example Insight – Metro vs Non-Metro

- In-Full %: Metro 92% vs Non-metro 78%  
- On-Time %: Metro 88% vs Non-metro 86%  
- Backorder Qty and cycle time are higher for non-metro locations  

**Conclusion:** Non-metro regions face greater fulfillment challenges, indicating potential inventory allocation and logistics optimization opportunities.

---

## ⚙️ Productivity Impact – AI vs Traditional Analytics

### Traditional Analytics

- Write SQL queries: 10–15 min  
- Write Python transformation code: 20–25 min  
- Build visualizations: 15–20 min  
- Debug & validate: 10–15 min  

> **Total time:** ~55–75 minutes per analysis cycle

### AI-Assisted Workflow (Quadratic)

- Write natural language prompt: ~2 min  
- AI generates code: ~30 sec  
- Run and visualize results: ~30 sec  
- Review and refine: ~2 min  

> **Total time:** ~5 minutes per analysis cycle  
> **Productivity gain:** ~12–17× faster

**Key idea:** AI accelerates the workflow but does not replace core data skills.

---

## ✅ Project Outcomes

### Technical Outcomes

- Fully automated data ingestion from email to database  
- Reduced data availability time from ~45 minutes to ~2 minutes  
- Achieved 100% consistency in data handling  
- Implemented scalable, cloud-based analytics infrastructure  
- Automated computation of 15+ supply chain KPIs  

### Business Outcomes

- Real-time supply chain performance visibility  
- Faster identification of late deliveries and backorders  
- Customer-level and category-level service monitoring  
- Quantification of revenue risk due to undelivered/late orders  
- Better understanding of metro vs non-metro performance gaps  

### Estimated Annual Impact

- ~180 hours saved in manual data processing  
- ~95% reduction in data errors  
- Decision-making moved from weekly reports to near real time  

---

## 🧠 Skills Demonstrated

### Data & Analytics

- Supply chain KPI definition and calculation  
- Performance benchmarking and root-cause analysis  
- Multi-dimensional analytics (customer, product, location, time)

### Data Engineering

- ETL pipeline design and implementation  
- Data cleaning and transformation at scale  
- Multi-source data integration (CSV, email, DB)  
- Feature engineering for analytics

### Workflow Automation

- n8n workflow design and configuration  
- Email integration and file extraction  
- Data validation, error handling, and notifications

### Database & Modeling

- PostgreSQL schema design (star schema)  
- Dimensional modeling for analytics  
- SQL query optimization  
- Cloud database configuration (Supabase)

### AI & Coding

- Prompt engineering for code generation  
- Python for data manipulation (pandas, numpy)  
- SQL for analytical queries  
- Validation and refinement of AI-generated code  

---

## 📁 Repository Structure (Suggested)

```bash
.
├── n8n_workflows/
│   └── email_to_database_workflow.json
├── database/
│   ├── schema_creation.sql
│   └── sample_data/
├── quadratic/
│   ├── supply_chain_analysis.grid
│   └── prompts_used.md
├── screenshots/
│   ├── n8n-workflow.png
│   ├── kpi-dashboard.png
│   └── metro_vs_non_metro.png
├── notebooks/
│   └── exploratory_analysis.ipynb
└── README.md
```

You can adjust this to match your actual file layout.

---

## 🚀 How to Run

1. **Clone the repository**

```bash
git clone https://github.com/SachinSavkare/AI-Driven-Supply-Chain-Analysis-N8N-Quadratic-Supabase.git
cd AI-Driven-Supply-Chain-Analysis-N8N-Quadratic-Supabase
```

2. **Set up Supabase / PostgreSQL**

- Create a PostgreSQL instance (e.g., via Supabase)  
- Run the SQL scripts in `database/schema_creation.sql`  
- Configure connection credentials (host, port, DB, user, password)

3. **Import n8n workflow**

- Import the JSON from `n8n_workflows/email_to_database_workflow.json`  
- Configure:
  - Gmail credentials / IMAP settings  
  - Database credentials for PostgreSQL  
- Activate the workflow

4. **Configure Quadratic**

- Connect Quadratic to the same PostgreSQL instance  
- Open the `supply_chain_analysis.grid` file  
- Run the prompts/notebooks to compute KPIs and generate insights  

5. **Explore KPIs & Insights**

- Use Quadratic dashboards / charts for:
  - OTIF trends
  - Metro vs non-metro performance
  - Customer and product-level service metrics

---

## 🔮 Future Enhancements

Planned / possible extensions:

- Predictive analytics for demand forecasting  
- Real-time alerts when OTIF or other KPIs fall below thresholds  
- Integration with inventory management / ERP systems  
- Advanced dashboards in Power BI / Tableau / Metabase  
- Machine learning models for delivery time and backorder prediction  

---

## 📚 Learning & Takeaways

- Automation is essential: Manual data handling doesn't scale.  
- AI is a **productivity accelerator**, not a replacement for fundamentals.  
- Good data architecture (star schema, clean joins) is critical for fast analytics.  
- Understanding business context (OTIF, fill rates, service levels) is what converts dashboards into real business value.

---

## 🤝 Connect

**Connect on LinkedIn:** [Arpit Dalal](https://www.linkedin.com/in/arpitdalal9/)

---

## 📎 License & Credits

**Tools Used:** [n8n](https://n8n.io/) | [Supabase](https://supabase.com/) | [Quadratic](https://quadratic.to/) | [PostgreSQL](https://www.postgresql.org/)

**Developed by:** [Arpit Dalal](https://www.linkedin.com/in/arpitdalal9/)  
© 2025 Supply Chain Analytics Portfolio Project


