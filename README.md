# Hi, I'm Johnny! | Data Engineering Student @ STI
 
I aim to build robust, scalable data pipelines and am driven by solving real-world problems from raw data to business value. I'm studying to be a Data Engineer at Stockholm Institute of Technology (STI) and I'm looking for a **LIA (internship) position for spring 2027**.
 
Before this I spent fourteen years in process-driven industry - CNC, surface treatment and 3D printing, with assignments for clients including Pfizer, Tetra Pak and KTH. That is work where quality requirements are absolute and every step has to be documented, which is more or less why I build pipelines the way I do: a process nobody can trace is a process nobody can fix.
 
My philosophy is simple: *Let go of and leave the tutorial data behind, build systems that handle real-world messy edge cases, and always be ready to adapt the tech stack to the needs of the business.*
 
---
 
## Degree Project (Examensarbete)
 
### [project3-kms - A RAG Knowledge Management System](https://github.com/JohnnyHyytiainen/project3-kms)
**Status:** *MVP v1-v3 complete (`v3.0.0`) - MVP v4 (serving) in progress: search, answers with cited sources, an eval harness and request tracing are built; a model selector and a query page are next*
 
**Stack:** PostgreSQL, SQLAlchemy 2.0, Alembic, PyMuPDF, ChromaDB, Grunden.ai (bge-m3 embeddings, GLM answers), PydanticAI, FastAPI, Pydantic Logfire, Docker, GitHub Actions
 
* Retrieval-Augmented Generation over a real corpus: 692 PDF, markdown and transcript files across 13 courses -> 631 unique documents -> 7,712 embedded chunks. Content and copies are split, so a lecture reused across courses is stored once and keeps every course link. Postgres is the source of truth; ChromaDB is a derivative that a full rebuild recreates in about 110 s, and a reconciliation step proves every vector has its row and every row its vector.
* `POST /ask` returns the answer and its sources. The sources are the retrieved rows from Postgres, never text from the model - a model can make up a filename, a database row can't. Answers come in the language of the question, with citations that match the ranks.
* Measured, not guessed: a hand-written eval set of 30 dev and 10 hold-out questions, scored with hit rate@k and MRR. After text cleaning, a right document is in the top five for 26 of 30 dev questions and ranked first for 21. With 30 questions one question moves the score 3.3 points, so the set grows before small improvements are judged.
* Every request is traced with Logfire, from the endpoint through embedding, the vector search and each Postgres query to the model call and its tokens. In the first traced request the answer model took 3.5 of 4.0 seconds, while twelve per-hit database queries (an N+1 pattern) took 24 ms - so they stay as they are until they matter. Unit tests are blocked from sending telemetry, and a deliberate sabotage proved the block holds.
*Course material is used with written permission from the instructors, obtained before ingestion began, and is not redistributed with the repository.*
 
---
 
## Featured Projects (Flagship)
 
### [GitHub Data Lake (Medallion Architecture)](https://github.com/JohnnyHyytiainen/data-lake-project)
**Status:** *Active v5.x.x - MVP v5 ongoing, deeper analysis for better insights into GitHub's data.*
 
**Stack:** Kafka (KRaft), PySpark, dbt, Airflow, DuckDB, Grafana, Docker, Parquet
 
* End-to-end streaming pipeline consuming the live GitHub Events API - 2.1M+ deduplicated Silver records across Bronze -> Silver -> Gold layers.
* Built the Kafka producer (KRaft, no ZooKeeper), PySpark Bronze-to-Silver transformation with schema validation, and three Gold analytical models: tool growth trends, community activity heatmap, and PR cycle times. (More insights to come.)
* Orchestrated with Apache Airflow, SQL transformations via dbt, served from DuckDB to Grafana dashboards.
* Diagnosed and fixed real production-grade bugs: PyArrow silent schema inference drop, a cartesian product fan trap in a self-join, and partition zero-padding inconsistencies.
---
 
### [Glossary DB (FastAPI + RAG + Streamlit)](https://github.com/JohnnyHyytiainen/glossary_db)
**Status:** *Active - v1.4.x*
 
**Stack:** FastAPI, PostgreSQL, SQLAlchemy, ChromaDB, Sentence-Transformers, Grunden.ai (GLM 5.1), Streamlit, Docker, Alembic
 
* AI-powered Data Engineering knowledge base with 500+ terms across 11 categories (Python, SQL, Data Engineering, AI Engineering, LLMOps, and more).
* Built a full RAG pipeline: PostgreSQL as the relational source of truth -> ChromaDB vector index (all-MiniLM-L6-v2 embeddings) -> Grunden.ai (GLM 5.1) for multilingual generation.
* Explainable AI (XAI): every response includes a `sources` array of the exact glossary terms used - no hallucinations by design.
* Streamlit frontend with a modular `ui/` package - fully decoupled from the backend, communicates via HTTP only.
---

 
## 🛠️ Tech Stack & Tools
 
* **Data Engineering & Pipelines:** Apache Kafka, Apache Spark (PySpark), dbt, dlt, Airflow, Dagster, Pandas, Databricks
* **Databases & Storage:** PostgreSQL (OLTP), DuckDB (OLAP), Snowflake (cloud data warehouse), ChromaDB (Vector), Parquet, S3 / object storage (boto3), Dimensional Modeling
* **AI & ML:** RAG pipelines, vector embeddings, LLM integration (Grunden.ai / OpenAI-compatible APIs), PydanticAI agents, retrieval evaluation (hit rate@k, MRR)
* **Backend & API:** FastAPI, SQLAlchemy, Pydantic, Alembic
* **Infrastructure & DevOps:** Docker, GitHub Actions (CI/CD), Pytest, Ruff, uv, Pydantic Logfire (OpenTelemetry tracing), and Azure Container Apps + ACR [provisioned with Terraform](https://github.com/JohnnyHyytiainen/lab_azure_fullstack_DE25_johnny_hyytiainen)
* **BI & Visualization:** Grafana, Streamlit, Matplotlib, Power BI
* **Learning right now:** LLMOps in an AIOps course this autumn. The genuinely new parts are LanceDB, LLM-as-a-judge evaluation, hallucination detection, prompt optimization and MCP, plus the GDPR and EU AI Act side of shipping LLM systems. PydanticAI, FastAPI and Logfire from the same course already run in my degree project.
---

## 📫 Let's have a coffee!
 
I'm happy to talk about architecture, data lifecycles, or how to handle unexpected null values in schemaless APIs. I've also led a cross-functional data platform project as Scrum Master and tech lead, so I'm just as happy to talk about how a team gets from a business requirement to a shipped pipeline.
 
I work in Swedish and English. **More course labs and exam assignments are under my repositories.**

* **LinkedIn:** [linkedin.com/in/johnny-hyytiainen](https://www.linkedin.com/in/johnny-hyytiainen/)
* **Email:** [johnny.hyytiainen@gmail.com](mailto:johnny.hyytiainen@gmail.com)
