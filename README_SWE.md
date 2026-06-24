# Hej, jag är Johnny! | Data Engineering Student @ STI
**[Click here for English version](https://github.com/JohnnyHyytiainen/johnnyhyytiainen/blob/main/README.md)**

Jag bygger robusta, skalbara datapipelines och drivs av att lösa verkliga problem från rådata till affärsvärde. Jag är för närvarande under utbildning till Data Engineer vid Stockholms Tekniska Institut (STI) och letar efter en **LIA-plats (praktik) inför våren 2027**.

Min filosofi är enkel: *Lämna tutorial-datan, bygga system som hanterar verklighetens stökiga kantfall, och var alltid redo att anpassa tech-stacken efter affärens behov.*

---

## Utvalda Projekt (Flaggskepp)

### [GitHub Data Lake (Medallion-arkitektur)](https://github.com/JohnnyHyytiainen/data-lake-project)
**Status:** *Aktiv och under utveckling v5.x.x - MVP v5 pågår, djupare analys för mer insikter kring Githubs data.*

**Stack:** Kafka (KRaft), PySpark, dbt, Airflow, DuckDB, Grafana, Docker, Parquet

* End-to-end strömmande pipeline som konsumerar live-events från GitHub API - 3M+ deduplicerade Silver-records genom Bronze -> Silver -> Gold.

* Kafka-producer (KRaft, utan ZooKeeper), PySpark Bronze-till-Silver med schemavalidering, och tre Gold-tabeller: verktygs-trender, community-aktivitetsheatmap och PR-cykeltider. (Mer insikter arbetas akrivt på)

* Orkestrerat med Apache Airflow, SQL-transformationer via dbt, serverat från DuckDB till Grafana-dashboards.

* Diagnostiserade och löste verkliga produktions-buggar: PyArrow tyst schemadropp, kartesisk produkt i self-join, och inkonsekvent partitionsnyckelpadding.

---

### [Glossary DB (FastAPI + RAG + Streamlit)](https://github.com/JohnnyHyytiainen/glossary_db)
**Status:** *Aktiv och under utveckling v1.4.x*

**Stack:** FastAPI, PostgreSQL, SQLAlchemy, ChromaDB, Sentence-Transformers, Grunden.ai (GLM 5.1), Streamlit, Docker, Alembic

* AI-driven Data Engineering-kunskapsbas med 500+ termer inom 11 kategorier (Python, SQL, Data Engineering, AI Engineering, LLMOps med flera).

* Fullständig RAG-pipeline: PostgreSQL som relationell källa till sanning -> ChromaDB vektorindex (all-MiniLM-L6-v2 embeddings) -> Grunden.ai (GLM 5.1) för flerspråkig generering.

* Explainable AI (XAI): varje svar inkluderar en `sources`-array med exakta ordlisttermer som användes - inga hallucinationer by design.
* Streamlit-frontend med modulärt `ui/`-paket - fullständigt decoupled från backend, kommunicerar enbart via HTTP.

---

## 🛠️ Tech Stack & Verktyg

* **Data Engineering & Pipelines:** Apache Kafka, Apache Spark (PySpark), dbt, Pandas, Airflow, Databricks
* **Databaser & Lagring:** DuckDB (OLAP), PostgreSQL (OLTP), ChromaDB (Vektor), Parquet, Dimensional Modeling
* **AI & ML:** RAG-pipelines, vektorembeddings, LLM-integration (Grunden.ai / OpenAI-kompatibla API:er)
* **Backend & API:** FastAPI, SQLAlchemy, Pydantic, Alembic
* **Infrastruktur & DevOps:** Docker, GitHub Actions (CI/CD), Pytest, Ruff, Black
* **BI & Visualisering:** Grafana, Streamlit, Matplotlib, PowerBI
* **Kommande / Pågående:** AWS / Azure, Terraform

---

## 📫 Låt oss ta en kaffe!
Jag pratar gärna arkitektur, data-livscykler eller hur man hanterar oväntade null-värden i schemalösa API:er.
Fler projekt - labbar och examinationsuppgifter från tidigare kurser - går att hitta under mina repositories.

* **LinkedIn:** [linkedin.com/in/johnny-hyytiainen](https://www.linkedin.com/in/johnny-hyytiainen/)
* **Email:** [johnny.hyytiainen@gmail.com](mailto:johnny.hyytiainen@gmail.com)
