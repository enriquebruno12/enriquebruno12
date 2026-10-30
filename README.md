<h1 align="center">Enrique Soares</h1>

<p align="center">
  <strong>Data Analytics &amp; BI · Data Engineering Portfolio</strong><br/>
  Electrical Engineering background · Operational data · Reliable pipelines
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/enriquebruno/">
    <img alt="Connect on LinkedIn" src="https://img.shields.io/badge/LinkedIn-enriquebruno-0A66C2?style=for-the-badge"/>
  </a>
  <a href="mailto:enrique.bruno12@outlook.com">
    <img alt="Email Enrique" src="https://img.shields.io/badge/Email-Get_in_touch-333333?style=for-the-badge"/>
  </a>
</p>

<p align="center">
  <img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=flat-square&amp;logo=python&amp;logoColor=white"/>
  <img alt="SQL" src="https://img.shields.io/badge/SQL-336791?style=flat-square"/>
  <img alt="PostgreSQL" src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&amp;logo=postgresql&amp;logoColor=white"/>
  <img alt="Docker" src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&amp;logo=docker&amp;logoColor=white"/>
  <img alt="Power BI" src="https://img.shields.io/badge/Power_BI-F2C811?style=flat-square&amp;logoColor=black"/>
  <img alt="scikit-learn" src="https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&amp;logo=scikitlearn&amp;logoColor=white"/>
</p>

## About me

I work across **data analytics, business intelligence and automation**, with a background in **Electrical Engineering** and Data Analytics studies through a Higher Diploma (2025–2026).

My current focus is developing data engineering skills through working portfolio projects: modeling operational data, validating inputs, building ingestion pipelines and making results usable for reporting. My engineering background gives me a particular interest in manufacturing, maintenance and operational performance.

I value explicit business rules, reproducible environments, useful tests and documentation that explains how the system works.

## Featured projects

| Project | Focus | Current evidence |
| --- | --- | --- |
| **[FactoryPulse](https://github.com/enriquebruno12/factorypulse-real-time-lakehouse)** | Data engineering · Industrial events | Local transactional ingestion, source-ID deduplication, validation and tests; cloud roadmap in development |
| **[Video Game Sales](https://github.com/enriquebruno12/vgsales-data-project)** | Data warehousing · Business intelligence | CSV ingestion, SQL quality checks, dimensional model and Power BI dashboard |
| **[Flu Shot Vaccine Prediction](https://github.com/enriquebruno12/vaccine_prediction_ml_project)** | Data analysis · Machine learning | EDA, preprocessing, Logistic Regression, tuning and held-out evaluation |

### 01 · FactoryPulse — Industrial event ingestion

**[Explore FactoryPulse →](https://github.com/enriquebruno12/factorypulse-real-time-lakehouse)**

A personal data engineering portfolio project built around a synthetic manufacturing scenario: **machines, production orders, faults and incremental production events**. I am developing the pipeline in stages, with runnable code and documented design decisions.

**Implemented locally**

- **Operational modeling:** PostgreSQL tables, primary/foreign keys, machine–order integrity, unique source event IDs and an event-derived production summary view.
- **Event simulation and validation:** a deterministic Python generator, JSONL input checks, timestamp offsets, event types and production-unit rules.
- **Transactional ingestion:** Psycopg queries resolve business codes to internal IDs and load events within a transaction.
- **Replay protection:** duplicate source IDs are skipped with `ON CONFLICT`, preserving the existing event.
- **Verification and documentation:** 16 Python unit tests for selected simulator/reader behaviors, SQL constraint tests, a data dictionary and an event contract.

```text
Python simulator → JSONL → Payload validation → ID lookup → PostgreSQL → Summary view
```

**Local replay demonstration:** the first run inserted 7 events; processing the same file again inserted 0 and skipped all 7. The current implementation uses synthetic data and runs locally; cloud streaming and lakehouse layers are planned.

**Current project stack:** Python 3.12+ · SQL · PostgreSQL 17 · Docker Compose · Psycopg 3 · python-dotenv · unittest · Git/GitHub

[Ingestion code](https://github.com/enriquebruno12/factorypulse-real-time-lakehouse/blob/main/src/ingestion/db.py) · [Tests & setup](https://github.com/enriquebruno12/factorypulse-real-time-lakehouse/blob/main/TESTING.md) · [Event contract](https://github.com/enriquebruno12/factorypulse-real-time-lakehouse/blob/main/docs/event_contract.md) · [Architecture & roadmap](https://github.com/enriquebruno12/factorypulse-real-time-lakehouse#architecture)

### 02 · Video Game Sales — Data Warehouse & Power BI

**[Explore the project →](https://github.com/enriquebruno12/vgsales-data-project)**

An analytics portfolio project covering **CSV ingestion → SQL data quality checks → normalization and deduplication → dimensional model → reporting view → Power BI dashboard**.

- Built raw and clean staging layers with a documented business grain and deduplication rule.
- Modeled fact and dimension tables and exposed a SQL view for analytical consumption.
- Delivered a Power BI dashboard covering sales trends, regional distribution, platforms and publishers.

**Stack:** Python · pandas · SQLAlchemy · psycopg2 · PostgreSQL · Docker Compose · Power BI

### 03 · Flu Shot Vaccine Prediction — Applied Machine Learning

**[Explore the project →](https://github.com/enriquebruno12/vaccine_prediction_ml_project)**

An academic machine learning project using survey data to model **H1N1 and seasonal flu vaccination uptake** with separate Logistic Regression classifiers.

- Explored missing values, class distributions and relationships between survey features and vaccination outcomes.
- Applied imputation, categorical encoding and numerical scaling before modeling.
- Compared baseline and GridSearchCV-tuned models using train/validation/test splits and metrics including ROC-AUC, precision, recall and F1-score.

**Stack:** Python · pandas · NumPy · scikit-learn · Matplotlib · Seaborn · Jupyter Notebook

## Technologies I use in projects

| Area | Tools and practices |
| --- | --- |
| Data ingestion & validation | Python, pandas, Psycopg 3, psycopg2, SQLAlchemy, JSONL/CSV, python-dotenv |
| Databases & modeling | SQL, PostgreSQL, relational constraints, joins, staging layers, dimensional modeling |
| Analytics & BI | Power BI, Power Query, DAX, KPI reporting and dashboard design |
| Analysis & machine learning | NumPy, scikit-learn, Matplotlib, Seaborn, Jupyter Notebook; EDA, preprocessing and model evaluation |
| Automation | Power Platform and Power Apps |
| Development & verification | Docker Compose, Git/GitHub, unittest, SQL quality checks, DBeaver, VS Code |

## FactoryPulse — planned next stages

The technologies below belong to the **project roadmap**. The current implementation and evidence are documented in the repository.

| Planned stage | Technologies | Intended outcome |
| --- | --- | --- |
| Cloud ingestion & storage | Azure Data Factory, Azure Event Hubs, ADLS Gen2 | Batch extraction, event streaming and raw data storage |
| Lakehouse processing | Databricks, PySpark, Delta Lake | Bronze/Silver/Gold datasets and incremental transformations |
| Analytics & serving | dbt, Power BI; Snowflake in a later stage | Documented analytical models, manufacturing KPIs and dashboards |
| Delivery & operations | Terraform, GitHub Actions, monitoring and logging | Reproducible infrastructure, automated checks and pipeline observability |

## Additional BI & automation work

- **Maintenance KPI Dashboard:** weekly reporting for factory performance.
- **Daily Route Check App:** an internal Power App for logging electrical maintenance parameters.
- **AWS Goals Tracker:** a Power BI dashboard with automated integration of partner metrics.

## Connect

For engineering and ingestion, start with **FactoryPulse**. For analytics delivery, explore **Video Game Sales**. For modeling and evaluation, see **Flu Shot Vaccine Prediction**.

You can reach me on **[LinkedIn](https://www.linkedin.com/in/enriquebruno/)** or by **[email](mailto:enrique.bruno12@outlook.com)**.
