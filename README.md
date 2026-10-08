# Strategic Data Analytics Framework: Customer Retention & CLV Optimization

## Project Overview
This project delivers an enterprise-grade strategic data analytics framework focused on e-commerce customer segmentation, retention analysis, and Customer Lifetime Value (CLV) forecasting using an end-to-end Python pipeline.

### Core Objectives
- Mitigate high customer churn post-first purchase.
- Transition marketing operations from blanket discounts to targeted cohort interventions.
- Harmonize transactional, behavioral, and demographic telemetry into an actionable feature store.

---

## Data Pipeline Architecture
- **Data Sources:** PostgreSQL OLTP Database, Clickstream JSON telemetry logs, and Payment/CRM APIs.
- **Security & Governance:** Automated PII masking via SHA-256 hashing; intermediate staging in partitioned Apache Parquet format.

---

## Technology Stack & Python Libraries
- **SQLAlchemy & psycopg2:** Database connection pooling, ORM mapping, and batch extraction.
- **pandas & numpy:** Data wrangling, vectorized feature engineering, and RFM calculations.
- **matplotlib & seaborn:** Statistical distributions, correlation heatmaps, and cohort retention decay curves.
- **scikit-learn:** Data normalization (`StandardScaler`), dimensionality reduction, and unsupervised clustering (`KMeans`).
- **lifetimes / btyd:** Probabilistic purchase forecasting via BG/NBD and Gamma-Gamma models.
- **shap:** Model explainability and feature attribution for business stakeholders.

---

## Project Roadmap & Work Breakdown Structure (32 Hours Total)
| Phase | Focus / Deliverable | Hours |
| :--- | :--- | :--- |
| **Phase 1: Setup & Scoping** | Business scoping, schema mapping, extraction pipelines | 5.0 hrs |
| **Phase 2: Hygiene & Wrangling** | Outlier handling, missing value imputation, RFM features | 6.5 hrs |
| **Phase 3: Exploratory EDA** | Univariate/bivariate analysis, cohort retention heatmaps | 5.5 hrs |
| **Phase 4: Segmentation Modeling** | Skewness transforms, Elbow/Silhouette testing, K-Means | 6.0 hrs |
| **Phase 5: Predictive Valuation** | BG/NBD and Gamma-Gamma modeling, holdout validation | 5.0 hrs |
| **Phase 6: Playbook Synthesis** | Actionable playbooks, executive deck, DOC dossier | 4.0 hrs |
| **Total Workload** | **End-to-End Strategic Delivery** | **32.0 hrs** |

---

## Risk Assessment & Mitigations
- **Heavy Outliers & Skewness:** Handled using 99th percentile Winsorization and `numpy.log1p` transformation.
- **Data Leakage:** Prevented using strict temporal partitions (Train: Months 1–9, Evaluation: Months 10–12).
- **Cold-Start Users:** Multi-purchase users routed to probabilistic models; single-order users routed to heuristic onboarding workflows.
