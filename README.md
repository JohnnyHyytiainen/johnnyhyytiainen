# Hi, I'm Johnny! | Data Engineering Student @ STI
**[Klicka här för svensk version](https://github.com/JohnnyHyytiainen/johnnyhyytiainen/blob/main/README_SWE.md)**

I build robust, scalable data pipelines and am driven by solving real-world problems from raw data to business value. I'm currently studying to be a Data Engineer at Stockholm Institute of Technology (STI) and am looking for a **LIA (internship) position for spring 2027**.

My philosophy is simple: *Leave the tutorial data, build systems that handle real-world messy edge cases, and always be ready to adapt the tech stack to the needs of the business.*

---

## Featured Projects (Flagship)

### [GitHub Data Lake (Medallion Architecture)](https://github.com/JohnnyHyytiainen/data-lake-project)
**Status:** *Active v5.x.x - MVP v5 ongoing, Deeper Analysis for Better Insights regarding Github's Data. *

**Stack:** Kafka (KRaft), PySpark, dbt, Airflow, DuckDB, Grafana, Docker, Parquet

* End-to-end streaming pipeline consuming live GitHub Events API - 3M+ deduplicated Silver records across Bronze -> Silver -> Gold layers.

* Built Kafka producer (KRaft, no ZooKeeper), PySpark Bronze-to-Silver transformation with schema validation, and three Gold analytical models: tool growth trends, community activity heatmap, and PR cycle times(More insights to come)

* Orchestrated with Apache Airflow, SQL transformations via dbt, served from DuckDB to Grafana dashboards.

* Diagnosed and fixed real production-grade bugs: PyArrow silent schema inference drop, cartesian product fan trap in a self-join, and partition zero-padding inconsistencies.

---

### [Glossary DB (FastAPI + RAG + Streamlit)](https://github.com/JohnnyHyytiainen/glossary_db)
**Status:** *Active - v1.4.x*

**Stack:** FastAPI, PostgreSQL, SQLAlchemy, ChromaDB, Sentence-Transformers, Grunden.ai (GLM 5.1), Streamlit, Docker, Alembic

* AI-powered Data Engineering knowledge base with 500+ terms across 11 categories (Python, SQL, Data Engineering, AI Engineering, LLMOps, and more).

* Built a full RAG pipeline: PostgreSQL as the relational source of truth -> ChromaDB vector index (all-MiniLM-L6-v2 embeddings) -> Grunden.ai (GLM 5.1) for multilingual generation.

* Explainable AI (XAI): every response includes a `sources` array of the exact glossary terms used - no hallucinations by design.

* Streamlit frontend with modular `ui/` package - fully decoupled from backend, communicates via HTTP only.

---

## 🛠️ Tech Stack & Tools

* **Data Engineering & Pipelines:** Apache Kafka, Apache Spark (PySpark), dbt, Pandas, Airflow, Databricks
* **Databases & Storage:** DuckDB (OLAP), PostgreSQL (OLTP), ChromaDB (Vector), Parquet, Dimensional Modeling
* **AI & ML:** RAG pipelines, Vector Embeddings, LLM integration (Grunden.ai / OpenAI-compatible APIs)
* **Backend & API:** FastAPI, SQLAlchemy, Pydantic, Alembic
* **Infrastructure & DevOps:** Docker, GitHub Actions (CI/CD), Pytest, Ruff, Black
* **BI & Visualization:** Grafana, Streamlit, Matplotlib, PowerBI
* **Upcoming / Ongoing:** AWS / Azure, Terraform

---

## 📫 Let's have a coffee!
I'm happy to talk about architecture, data lifecycles, or how to handle unexpected null values in schemaless APIs.
More projects - labs and exam assignments from previous courses - can be found under my repositories.

* **LinkedIn:** [linkedin.com/in/johnny-hyytiainen](https://www.linkedin.com/in/johnny-hyytiainen/)
* **Email:** [johnny.hyytiainen@gmail.com](mailto:johnny.hyytiainen@gmail.com)
