# Hi, I'm Johnny! | Data Engineering Student @ STI
 
I aim to build robust, scalable data pipelines and am driven by solving real-world problems from raw data to business value. I'm studying to be a Data Engineer at Stockholm Institute of Technology (STI) and I'm looking for a **LIA (internship) position for spring 2027**.
 
Before this I spent fourteen years in process-driven industry - CNC, surface treatment and 3D printing, with assignments for clients including Pfizer, Tetra Pak and KTH. That is work where quality requirements are absolute and every step has to be documented, which is more or less why I build pipelines the way I do: a process nobody can trace is a process nobody can fix.
 
My philosophy is simple: *Let go of and leave the tutorial data behind, build systems that handle real-world messy edge cases, and always be ready to adapt the tech stack to the needs of the business.*
 
---
 
## Degree Project (Examensarbete)
 
### [project3-kms - A RAG Knowledge Management System](https://github.com/JohnnyHyytiainen/project3-kms)
**Status:** *MVP v1 complete (`v1.0.0`) - MVP v2 built and verified end-to-end - MVP v3 (embeddings) next*
 
**Stack:** PostgreSQL, SQLAlchemy 2.0, Alembic, LocalStack S3, PyMuPDF, PyArrow / Parquet, ChromaDB, FastAPI, Docker, GitHub Actions
 
* Retrieval-Augmented Generation system over a real 745-file corpus - PDFs, markdown and video transcripts across 13 course repositories - through a Bronze -> Silver -> Gold medallion pipeline. Every answer has to trace back to its exact source chunk.
* Every number in the repo is counted, not estimated: 745 files on disk -> 473 ingested -> 407 rows after content-hash dedup (66 duplicates, 14.0 %), 90 of 94 unique PDFs extracted, ~28 s for a full rebuild from an empty stack.
* That 14 % dedup rate turned out to be a provenance problem rather than a storage win: a file reused across two courses collapses into one row with one course tag, which quietly breaks course-filtered retrieval. It gets a junction table *before* anything is embedded - metadata added after indexing means re-embedding everything.
* Failed documents get a reason code on the row instead of a crash. Four codes separate "no extractable text" from "text below threshold", because the second answer means the document had content all along and the threshold is what's wrong.
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
 
* **Data Engineering & Pipelines:** Apache Kafka, Apache Spark (PySpark), dbt, Airflow, Pandas, Databricks
* **Databases & Storage:** PostgreSQL (OLTP), DuckDB (OLAP), ChromaDB (Vector), Parquet, S3 / object storage (boto3), Dimensional Modeling
* **AI & ML:** RAG pipelines, vector embeddings, rerankers, LLM integration (Grunden.ai / OpenAI-compatible APIs)
* **Backend & API:** FastAPI, SQLAlchemy, Pydantic, Alembic
* **Infrastructure & DevOps:** Docker, GitHub Actions (CI/CD), Pytest, Ruff, and Azure Container Apps + ACR [provisioned with Terraform](https://github.com/JohnnyHyytiainen/lab_azure_fullstack_DE25_johnny_hyytiainen)
* **BI & Visualization:** Grafana, Streamlit, Matplotlib, Power BI
* **Learning right now:** Snowflake, dlt and Dagster - the genuinely new parts of a data warehouse lifecycle course running this autumn. The rest of that stack (dbt, Streamlit, Azure) is already above, and Dagster is orchestration I've done before in Airflow. Next after that: data contracts, which the course doesn't cover, which is exactly why.
---

## 📫 Let's have a coffee!
 
I'm happy to talk about architecture, data lifecycles, or how to handle unexpected null values in schemaless APIs. I've also led a cross-functional data platform project as Scrum Master and tech lead, so I'm just as happy to talk about how a team gets from a business requirement to a shipped pipeline.
 
I work in Swedish and English. **More course labs and exam assignments are under my repositories.**

* **LinkedIn:** [linkedin.com/in/johnny-hyytiainen](https://www.linkedin.com/in/johnny-hyytiainen/)
* **Email:** [johnny.hyytiainen@gmail.com](mailto:johnny.hyytiainen@gmail.com)