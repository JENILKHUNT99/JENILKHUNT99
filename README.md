<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=200&section=header&text=Jenil%20Khunt&fontSize=70&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Data%20Engineer%20%7C%20Building%20Scalable%20Data%20Pipelines&descAlignY=58&descSize=18" width="100%" />

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=24&pause=1000&color=00D8FF&center=true&vCenter=true&width=750&lines=Data+Engineer+%7C+ELT+%2F+ETL+Pipelines;Apache+Airflow+%7C+dbt+%7C+PostgreSQL;Star+Schema+Data+Warehouse+Design;Docker+%7C+AWS+S3+%7C+GitHub+Actions;Turning+Raw+Data+Into+Analytics-Ready+Models" alt="Typing SVG" />

<br/>

📍 **India** &nbsp;|&nbsp; 🎓 **Computer Engineering Graduate (2026)** &nbsp;|&nbsp; 📧 **jenil.khunt.d@gmail.com**

<br/>

<a href="mailto:jenil.khunt.d@gmail.com">
  <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/>
</a>
<a href="https://www.linkedin.com/in/jenilkhunt">
  <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
</a>
<a href="https://github.com/JENILKHUNT99">
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
</a>
<img src="https://komarev.com/ghpvc/?username=JENILKHUNT99&label=Profile%20Views&color=00d8ff&style=for-the-badge" alt="Profile Views" />

<br/>

<img src="https://img.shields.io/badge/Open%20To-Data%20Engineer%20Roles-2ea44f?style=for-the-badge" alt="Open to work"/>

</div>

---

## 💫 About Me

```yaml
name: Jenil Khunt
role: Data Engineer
focus:
  - Production-grade ELT / ETL pipelines
  - Star schema data warehouse design
  - Workflow orchestration & data quality
currently_building: Hourly containerized crypto ELT pipeline (Airflow + dbt + PostgreSQL)
currently_learning: [Kafka, Spark, Streaming Architectures]
philosophy: "Load raw first, transform in SQL, test everything."
```

- 🔭 Building **production-grade ELT pipelines** that are containerized, orchestrated and tested
- 🏗️ Designing **star schema warehouses** that turn raw API data into analytics-ready models
- ✅ Big on **data quality gates, audit trails and idempotent (deterministic) keys**
- 🌱 Currently learning **streaming** with **Apache Kafka** and **Apache Spark**
- 💬 Ask me about **Airflow DAGs, dbt models & tests, dimensional modeling, Docker Compose**
- ⚡ Goal: build **reliable, maintainable data infrastructure** that analysts can trust

---

## 🚀 Featured Project

<div align="center">

### 🪙 Crypto Market ELT Pipeline

<a href="https://github.com/JENILKHUNT99/CryptoCurrency_ETL">
  <img src="https://github-stats-extended.vercel.app/api/pin/?username=JENILKHUNT99&repo=CryptoCurrency_ETL&theme=tokyonight&hide_border=true" alt="Crypto Market ELT Pipeline"/>
</a>

<p>
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/Apache%20Airflow-017CEE?style=flat-square&logo=apacheairflow&logoColor=white"/>
<img src="https://img.shields.io/badge/dbt-FF694B?style=flat-square&logo=dbt&logoColor=white"/>
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white"/>
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white"/>
<img src="https://img.shields.io/badge/AWS%20S3-569A31?style=flat-square&logo=amazons3&logoColor=white"/>
<img src="https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white"/>
</p>

</div>

A **containerized, hourly-orchestrated ELT pipeline** for cryptocurrency market data. Python extracts from
the CoinGecko API, gates on data quality and loads raw records into PostgreSQL — then **dbt** transforms
them into a tested star schema, with **Apache Airflow** orchestrating the whole run every hour.

**What's inside**

- 🔁 **4-task Airflow DAG:** `apply_migrations → run_python_etl → dbt_run → dbt_test`
- 🧊 **Immutable raw snapshots** partitioned by UTC run date/hour, optionally synced to **AWS S3**
- ⭐ **dbt star schema:** `fact_crypto_prices` joined to `dim_coin`, `dim_category`, `dim_currency`, `dim_date`
- 🔑 **Deterministic fact keys** (`bitcoin_usd_20250720T100000000000Z`) — reprocessing never duplicates rows
- 🛡 **Quality gates + `pipeline_runs` audit trail**, with `MIN_VALID_RECORDS` failing the run early
- 🧱 **Versioned SQL migrations** applied automatically as the first DAG task
- ✅ **CI on GitHub Actions** running `pytest` and `ruff` on every push and pull request
- 🐳 **Fully Dockerized** — `docker compose up --build` brings up Airflow and PostgreSQL

**Pipeline architecture**

```mermaid
flowchart LR
    API[CoinGecko API] --> EXTRACT[Extract - Python]
    EXTRACT --> RAW[Raw JSON snapshot]
    EXTRACT --> VALIDATE[Validate - Python]
    VALIDATE --> RAWCOINS[(raw_coins)]
    RAWCOINS --> DBT[Transform - dbt models]
    DBT --> STAR[(Star schema in PostgreSQL)]
    RAW -. optional .-> S3[(Amazon S3)]
    VALIDATE --> AUDIT[(pipeline_runs audit)]
```

> **ELT over ETL:** the raw data is loaded *before* it is transformed. Python never reshapes the data —
> it only extracts, gates on quality and loads. Every transformation lives in versioned, tested SQL,
> so the raw layer can always be replayed without re-hitting the API.

<div align="center">
<a href="https://github.com/JENILKHUNT99/CryptoCurrency_ETL">
  <img src="https://img.shields.io/badge/Explore%20the%20Repository-181717?style=for-the-badge&logo=github&logoColor=white"/>
</a>
</div>

---

## 🛠 Tech Stack

<div align="center">

### 🐍 Languages & Databases
<img src="https://skillicons.dev/icons?i=python,postgres,mysql,sqlite,mongodb,bash&theme=dark" />

### ⚙️ Orchestration & Transformation
<p>
<img src="https://img.shields.io/badge/Apache%20Airflow-017CEE?style=for-the-badge&logo=apacheairflow&logoColor=white"/>
<img src="https://img.shields.io/badge/dbt-FF694B?style=for-the-badge&logo=dbt&logoColor=white"/>
<img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white"/>
</p>

### 🗄 Data Modeling & Pipelines
<p>
<img src="https://img.shields.io/badge/ETL%20%2F%20ELT-4B8BBE?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Star%20Schema-6A5ACD?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Batch%20Processing-2E8B57?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Data%20Quality%20Testing-8A2BE2?style=for-the-badge"/>
</p>

### 🌐 Backend & APIs
<img src="https://skillicons.dev/icons?i=django&theme=dark" />
<p>
<img src="https://img.shields.io/badge/Django%20REST%20Framework-092E20?style=for-the-badge&logo=django&logoColor=white"/>
</p>

### ☁️ DevOps & Cloud
<img src="https://skillicons.dev/icons?i=docker,git,github,githubactions,aws,linux,vscode&theme=dark" />
<p>
<img src="https://img.shields.io/badge/AWS%20S3-569A31?style=for-the-badge&logo=amazons3&logoColor=white"/>
<img src="https://img.shields.io/badge/Docker%20Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white"/>
</p>

### 📚 Currently Learning
<p>
<img src="https://img.shields.io/badge/Apache%20Kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white"/>
<img src="https://img.shields.io/badge/Apache%20Spark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white"/>
</p>

</div>

---

## 🎯 Current Focus

| Area | What I'm Doing |
| :--- | :--- |
| 🔁 **Orchestration** | Hardening Airflow DAGs — retries, SLAs, idempotent task design |
| ⭐ **Warehouse Design** | Star schema modeling with dbt: staging → dimensions → facts |
| ✅ **Data Quality** | dbt tests (unique, not-null, relationships) + Python validation gates |
| 🌊 **Streaming** | Learning **Kafka** and **Spark** to move from batch to real-time |
| ☁️ **Cloud** | Deepening **AWS** (S3 layers, IAM, cost-aware storage patterns) |

---

## 📊 GitHub Stats

<div align="center">

<img height="180em" src="https://github-stats-extended.vercel.app/api?username=JENILKHUNT99&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true&hide_border=true&hide=prs,issues,contribs" alt="GitHub Stats"/>
<img height="180em" src="https://github-stats-extended.vercel.app/api/top-langs/?username=JENILKHUNT99&layout=compact&theme=tokyonight&hide_border=true&langs_count=8" alt="Top Languages"/>

<br/><br/>

<img src="https://streak-stats.demolab.com?user=JENILKHUNT99&theme=tokyonight&hide_border=true" alt="GitHub Streak"/>

<br/><br/>

**Contribution Graph**

<img src="https://ghchart.rshah.org/00d8ff/JENILKHUNT99" alt="Contribution Chart" width="90%"/>

</div>

---

## 💡 Data Engineering Philosophy

```python
class DataEngineer:
    def __init__(self):
        self.name = "Jenil Khunt"
        self.stack = ["Python", "Airflow", "dbt", "PostgreSQL", "Docker", "AWS"]
        self.principles = [
            "Load raw first — never lose the source of truth",
            "Validate at the gate, not after the damage",
            "Deterministic keys make reprocessing safe",
            "If it isn't tested, it isn't a pipeline",
            "Orchestration beats cron jobs",
        ]

    def build(self) -> str:
        return "Reliable data infrastructure analysts can trust"
```

---

<div align="center">

### 🤝 Let's Connect

I'm actively looking for **Data Engineer** opportunities.
If you're building data platforms, pipelines or warehouses — I'd love to talk.

<a href="mailto:jenil.khunt.d@gmail.com">
  <img src="https://img.shields.io/badge/Email%20Me-D14836?style=for-the-badge&logo=gmail&logoColor=white"/>
</a>
<a href="https://www.linkedin.com/in/jenilkhunt">
  <img src="https://img.shields.io/badge/Connect%20on%20LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/>
</a>

<br/><br/>

### *"Good data builds great decisions."*

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:2c5364,50:203a43,100:0f2027&height=120&section=footer" width="100%"/>

</div>
