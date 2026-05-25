# solo-inteligente

Agricultural intelligence — land parcel analysis and RAG pipeline for rural property research in Brazil.

---

## What it does

Brazilian rural property data is fragmented across INCRA, CAR, and state registries — expensive to access and hard to cross-reference. This project builds a pipeline to:

1. **Aggregate land parcel data** — structure and normalize records from public rural cadastres
2. **RAG pipeline** — retrieve relevant property intelligence from unstructured documents (registrations, environmental reports, rural deeds) using FAISS vector search
3. **Query interface** — ask questions about parcels, ownership history, and environmental constraints in natural language

---

## Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![FAISS](https://img.shields.io/badge/FAISS-0467DF?style=flat)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat&logo=pandas&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white)

---

## Data sources

- INCRA (SNCR) — rural property cadastre
- CAR — Cadastro Ambiental Rural
- SIGEF — georeferenced rural properties

---

*Sibling project to [urban-space](https://github.com/MaxPower90/urban-space) — same methodology applied to rural markets.*
