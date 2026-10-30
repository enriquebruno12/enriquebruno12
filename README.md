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

I am a data professional with **3+ years of experience in data integration, analytics and reporting automation** across technology and manufacturing, with a background in **Electrical Engineering** and Data Analytics studies through a Higher Diploma (2025–2026).

My experience includes work at **Compass.UOL, Procter & Gamble and Jabil**. My current portfolio focus is data engineering: modeling operational data, validating inputs, building reliable ingestion and making results usable for reporting. Manufacturing and maintenance experience informs the business context behind FactoryPulse.

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

**Engineering practices implemented locally**

| Practice | How I applied it |
| --- | --- |
| **Unit testing** | 16 `unittest` cases covering selected simulator and reader behaviors, with positive/negative scenarios, exception assertions and temporary file fixtures. |
| **Idempotency & deduplication** | A unique source event ID and `ON CONFLICT ... DO NOTHING` prevent duplicate inserts when the same events are replayed. |
| **Data contract & fail-fast validation** | Check required fields, types, nonblank strings, allowed event types, timezone-aware timestamps and production-unit rules before loading. |
| **Exception handling & error context** | Raise validation errors with field/line context and preserve parsing causes through exception chaining. |
| **Parameterized SQL** | Pass business codes and event values separately from SQL for machine/order lookups and inserts. |
| **Transaction management & atomicity** | Group each file load in one transaction: commit on success, rollback when an exception escapes; report counters after commit. Context managers close cursors and the connection. |
| **Relational integrity** | Use primary keys, foreign keys (including composite keys), unique constraints and check constraints to protect machine/order relationships and payload rules. |
| **State machine validation** | Validate `STOPPED`, `RUNNING` and `FAULTED` transitions in the simulator, including strict event ordering. |
| **Reproducibility & documentation** | Docker Compose, deterministic sample events, version-controlled SQL, separate seeds/tests, a data dictionary and an event contract. |

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

## Professional BI & Automation Work

### AWS Goals Tracker · Compass.UOL
*Business Analyst II · March 2023–March 2025*

**Built:** a Power BI reporting solution for AWS opportunity tracking, automating data extraction, transformation and dashboard refreshes **three times daily**. Translated stakeholder needs into KPI requirements and validated the reporting data.

**Result:** eliminated approximately **2 hours of manual work per week** previously spent on Excel exports and slide preparation.

### Maintenance KPI Dashboard · Procter & Gamble
*Process Engineer Trainee · July 2022–March 2023*

**Built:** a maintenance KPI dashboard to replace Excel-heavy reviews, alongside automated weekly production-line hardware reporting and manufacturing performance analysis.

**Result:** shortened maintenance review meetings from **3–4 hours to 1 hour or less**—approximately **67–75% less meeting time**.

### Daily Route Check App · Jabil
*Facilities Analyst · March 2021–July 2022*

**Built:** an internal Power Apps application for electricians to record inspection parameters, with paperless submission and filing of inspection records.

**Result:** reduced inspection rounds from **120 to 45 minutes**—**75 minutes saved per round (62.5%)**. Removing paper forms, scanning and archiving also saved approximately **30 minutes per week**.

*These are professional work examples; the public portfolio repositories above provide code and documentation for my personal and academic projects.*

## Tools & practices across work and portfolio

| Area | Tools and practices |
| --- | --- |
| Data ingestion & validation | Python, pandas, Psycopg 3, psycopg2, SQLAlchemy, JSONL/CSV, python-dotenv |
| Databases & modeling | SQL, PostgreSQL, MySQL, relational constraints, joins, staging layers, dimensional modeling |
| Analytics & BI | Power BI, Power Query, DAX, advanced Excel, KPI reporting and dashboard design |
| Analysis & machine learning | NumPy, scikit-learn, Matplotlib, Seaborn, Jupyter Notebook; EDA, preprocessing and model evaluation |
| Automation | Power Platform and Power Apps |
| Development & verification | Docker Compose, Git/GitHub, unit testing with unittest, SQL constraint tests, parameterized queries, transaction management, DBeaver, VS Code |

## FactoryPulse — planned next stages

The technologies below belong to the **project roadmap**. The current implementation and evidence are documented in the repository.

| Planned stage | Technologies | Intended outcome |
| --- | --- | --- |
| Cloud ingestion & storage | Azure Data Factory, Azure Event Hubs, ADLS Gen2 | Batch extraction, event streaming and raw data storage |
| Lakehouse processing | Databricks, PySpark, Delta Lake | Bronze/Silver/Gold datasets and incremental transformations |
| Analytics & serving | dbt, Power BI; Snowflake in a later stage | Documented analytical models, manufacturing KPIs and dashboards |
| Delivery & operations | Terraform, GitHub Actions, monitoring and logging | Reproducible infrastructure, automated checks and pipeline observability |

## Connect

For engineering and ingestion, start with **FactoryPulse**. For analytics delivery, explore **Video Game Sales**. For modeling and evaluation, see **Flu Shot Vaccine Prediction**.

You can reach me on **[LinkedIn](https://www.linkedin.com/in/enriquebruno/)** or by **[email](mailto:enrique.bruno12@outlook.com)**.
