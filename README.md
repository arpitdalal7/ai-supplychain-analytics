# AI-Driven Supply Chain Analytics

End-to-end automated supply chain analytics pipeline using n8n, Supabase (PostgreSQL), and Quadratic AI.

---

## 📌 Table of Contents

- [Project Overview](#project-overview)
- [Objectives](#objectives)
- [Key Features](#key-features)
- [Architecture](#architecture)
- [Project Structure and Tools](#project-structure-and-tools)
- [Business Question Prompts](#business-question-prompts)
- [Insights and Visual Analysis](#insights-and-visual-analysis)
- [Core Formulas and KPIs](#core-formulas-and-kpis)
- [Final Recommendations](#final-recommendations)
- [Installation](#installation)
- [Usage](#usage)
- [Skills Demonstrated](#skills-demonstrated)
- [Contributing](#contributing)
- [License and Credits](#license-and-credits)
- [Author](#author)

---

## Project Overview

This project demonstrates how AI tools like **Quadratic** and **n8n** can automate and analyze complex supply chain operations for a fictional FMCG company – **AtliQ Mart**.

Using:

- Email-based data ingestion  
- **PostgreSQL** (via **Supabase**) for storage  
- An **AI-powered spreadsheet interface** (Quadratic)

the project performs deep analytics on:

- Fulfillment performance  
- Order cycle time  
- Delivery reliability  
- Demand variability and patterns  

---

## Objectives

The main objective of this project is to:

- Automate data processing from raw CSV emails to a clean analytics-ready database.
- Generate **SCOR-based supply chain KPIs** using modern AI tools.
- Enable **faster, data-driven decision-making** for operations and management.

---

## Key Features

Major functionalities of the project include:

- Demand forecasting and trend analysis  
- Inventory optimization support  
- Supplier and customer performance analysis  
- Supply chain performance dashboards  
- Automated data ingestion from emails using n8n  
- AI-powered analytics via natural language prompts in Quadratic  
- Delivery and fulfillment performance analysis (OT, IF, OTIF, fill rates)

---

## Architecture

High-level data flow:

1. Vendors send daily sales and order CSV files via email.
2. **n8n** monitors the email inbox and automatically ingests CSV attachments.
3. Data is cleaned/transformed and loaded into **PostgreSQL** on **Supabase**.
4. **Quadratic** connects to Supabase and runs AI-assisted Python/SQL for:
   - Data cleaning and merging
   - KPI calculations
   - Visual and tabular analysis
5. Insights and KPIs are shared with stakeholders through slide decks and dashboards.

**Pipeline:**  
Email → n8n Automation → Supabase (PostgreSQL) → Quadratic AI Analysis → Dashboards/Slides

---

## Project Structure and Tools

### Layers and Tools

| Layer              | Tool / Platform      | Purpose                                       |
|--------------------|----------------------|-----------------------------------------------|
| Automation Layer   | n8n (self-hosted)    | Email monitoring, CSV ingestion, ETL          |
| Data Storage       | PostgreSQL (Supabase)| Cloud-native relational database               |
| Analytics Layer    | Quadratic            | AI spreadsheet for analysis and reporting     |
| Visualization      | PowerPoint           | KPI dashboards and stakeholder presentations  |

### What Each Tool Does

- **n8n**  
  - Listens to a Gmail inbox  
  - Downloads CSV attachments  
  - Parses and transforms them  
  - Inserts clean data into PostgreSQL tables  

- **Supabase (PostgreSQL)**  
  - Stores fact and dimension tables (orders, products, customers, targets)  
  - Enables SQL-based analytics and connections from Quadratic  

- **Quadratic**  
  - Connects directly to the Supabase database  
  - Uses natural language prompts to generate Python/SQL code  
  - Performs data cleaning, joins, and KPI calculations  
  - Produces tables, charts, and exports for presentations  

---

## Business Question Prompts

All natural language prompts used in Quadratic to answer business questions are documented in a separate prompt file (e.g., `Prompt-for-New-Tables-Columns-Business-Ex-1-2-3.docx.pdf`).

### Exercise 1 – Core Performance and Revenue

Typical prompts include:

- Show monthly on-time performance by cities.  
- Show top 5 customers based on order value and their OTIF %, IF %, and OT %.  
- Show top 5 customers in India based on order value and their OTIF %, IF %, and OT %.  
- Quantify the revenue loss attributed to undelivered orders.  
- Identify customers with the most significant OTIF discrepancies.  
- Determine product categories that exhibit low "In Full" delivery rates.  
- Calculate the average delay time for late deliveries.  
- Identify product categories with the lowest "In Full" delivery rates.

### Exercise 2 – Reliability and Variability

- Which product categories are facing the highest fulfillment and delivery challenges?  
- Are any customers consistently missing OTIF targets?  
- Where is lead-time variability threatening service levels?  
- Which weeks experienced the worst demand swings, and did that impact service?  
- Do long delivery delays correlate with larger backorders?  
- Which customers are improving or worsening in order cycle time?  
- Are metro and non-metro customers served differently?

These prompts allow non-technical users to explore complex supply chain questions through AI-generated code and charts.

---

## Insights and Visual Analysis

The analysis provides several views for stakeholders, including:

- Weekly and monthly performance graphs.  
- Customer-wise OTIF trends.  
- Category-wise fulfillment and backorder summaries.  
- Revenue loss and service gap views.

A simple performance-flag system is used throughout:

- 🔴 **Red**: Below 60% (critical)  
- 🟡 **Yellow**: 60–80% (needs attention)  
- 🟢 **Green**: Above 80% (good performance)  

These flags make it easier for managers to spot problem areas at a glance.

---

## Core Formulas and KPIs

Key columns and KPIs used in the analysis:

| Column / KPI                 | Formula / Definition                                                                 |
|-----------------------------|----------------------------------------------------------------------------------------|
| `backorder_qty`             | `order_qty - delivery_qty`                                                            |
| `order_cycle_time_days`     | `actual_delivery_date - order_placement_date`                                        |
| `delivery_delay_days`       | `actual_delivery_date - agreed_delivery_date`                                        |
| `in_full_percent`           | `(delivery_qty / order_qty) * 100`                                                   |
| `on_time_flag`              | `1 if actual_delivery_date <= agreed_delivery_date else 0`                           |
| `lead_time_variability`     | Standard deviation of `order_cycle_time_days` by category or customer                |
| `category_demand_variability` | Standard deviation of weekly `order_qty` by product category                       |
| `OTIF %`                    | Percentage of orders where `on_time_flag = 1` and `in_full_percent = 100`           |

These metrics support SCOR-style supply chain performance monitoring (reliability, responsiveness, and variability).

---

## Final Recommendations

Based on the analysis, the project suggests:

- Stabilize **Beverages** and **Dairy** category fulfillment.  
- Track **lead time variability weekly** instead of only monthly.  
- Improve OTIF via **city-specific distribution adjustments**.  
- Introduce **weekly alerts** when demand surges or service drops.  
- Address **inventory allocation issues in non-metro locations**.  

These recommendations show how analytics directly support operational decisions.

---

## Installation

Basic steps to set up this project (adapt to your environment):

1. **Clone the repository**

   ```bash
   git clone https://github.com/arpitdalal7/ai-supplychain-analytics.git
   cd ai-supplychain-analytics
   ```

2. **Configure PostgreSQL via Supabase**

   - Create a free project on Supabase.  
   - Run the SQL schema file (e.g., `database/schema_creation.sql`).  
   - Note the database connection string.

3. **Set up n8n for email monitoring**

   - Install and start n8n (self-hosted or cloud).  
   - Import the workflow file (e.g., `workflows/n8n_email_to_database.json`).  
   - Configure Gmail credentials and filters for incoming CSV emails.  
   - Configure the PostgreSQL credentials using the Supabase connection string.

4. **Connect Quadratic to the database**

   - Create a Quadratic account.  
   - Open the provided workbook (e.g., `quadratic/supply_chain_analysis.grid`).  
   - Add a connection to the Supabase PostgreSQL database.  
   - Use the prompts to generate KPIs and visual analysis.

---

## Usage

Typical workflow:

1. Load supply chain order data through the automated pipeline (vendors send emails, n8n ingests data).  
2. Use Quadratic AI prompts to perform analytics (no manual SQL required).  
3. Explore KPIs such as **OTIF**, **delivery delays**, **demand variability**, and **fulfillment performance**.  
4. Review dashboards and insights using the presentation slides (e.g., `Presentation.pptx`).  

This process turns raw CSV files into ready-to-use insights with minimal manual work.

---

## Skills Demonstrated

- **Workflow Automation**: n8n workflow design, email monitoring, and ETL pipeline creation.  
- **Database Design**: Star-schema modeling, PostgreSQL on Supabase, SQL querying.  
- **AI-Driven Analytics**: Prompt engineering, AI-generated Python/SQL, KPI calculations.  
- **Supply Chain Analytics**: SCOR-based metrics, OTIF analysis, demand and lead-time variability.  
- **Data Storytelling**: Creating clear dashboards and presentations for business stakeholders.

---

## Contributing

Contributions are welcome.

1. Fork the repository.  
2. Create a new branch (`feature/your-feature-name`).  
3. Commit your changes.  
4. Open a pull request for review.

---

## License and Credits

This project is licensed under the **MIT License**.

**Tools Used**

- n8n  
- Supabase  
- Quadratic  
- PostgreSQL  

**Credits**

- Project inspired and guided by the **Codebasics** YouTube channel and their supply chain analytics project tasks.

© 2025 Supply Chain Analytics Portfolio Project

---

## Author

**Arpit Dalal**

- LinkedIn: <https://www.linkedin.com/in/arpitdalal9/>  
- GitHub: <https://github.com/arpitdalal7/ai-supplychain-analytics>  

If you find this project useful, consider starring the repository and connecting on LinkedIn.
```
