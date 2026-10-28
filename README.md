# 🧱 Local Data Platform — Base

Base de uma **plataforma de dados local** em Docker Compose, para desenvolver e testar pipelines sem nuvem: orquestração com **Airflow**, transformação com **dbt**, processamento com **Spark** e armazenamento simulado de **AWS S3 (LocalStack)** e **Azure Blob (Azurite)**.

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Airflow](https://img.shields.io/badge/Airflow_2.10-017CEE?style=flat-square&logo=apacheairflow&logoColor=white) ![dbt](https://img.shields.io/badge/dbt-FF694B?style=flat-square&logo=dbt&logoColor=white) ![Spark](https://img.shields.io/badge/Spark-E25A1C?style=flat-square&logo=apachespark&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)

## 🧩 Serviços
| Serviço | Papel | Porta |
|---|---|---|
| Airflow (webserver + scheduler) | Orquestração (LocalExecutor) | 8080 |
| PostgreSQL 15 | Metadados do Airflow | — |
| LocalStack | AWS S3 simulado | 4566 |
| Azurite | Azure Blob, Queue e Table simulados | definidas no `.env` |
| Spark | Processamento distribuído | definida no `.env` |

O Airflow já sobe com os providers de Spark, AWS e Azure, além de `dbt-spark` e `delta-spark`.

## ▶️ Como rodar
```bash
docker compose up -d
```
Acesse o Airflow em http://localhost:8080. As DAGs ficam em `airflow/dags/` e o projeto dbt em `dbt/`.
