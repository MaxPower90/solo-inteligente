<div align="center">

# solo-inteligente

**Agricultural intelligence — land parcel analysis and RAG pipeline for rural property research in Brazil.**

![Python](https://img.shields.io/badge/Python-0d1117?style=for-the-badge&logo=python&logoColor=58a6ff)
![FAISS](https://img.shields.io/badge/FAISS-0d1117?style=for-the-badge&logoColor=58a6ff)
![SQLite](https://img.shields.io/badge/SQLite-0d1117?style=for-the-badge&logo=sqlite&logoColor=58a6ff)

</div>

---

Brazilian rural property data is fragmented across INCRA, CAR, and state registries — expensive to access and hard to cross-reference. This project builds an intelligence layer on top of it.

---

## What it does

**`notebooks/organiza_terrenos.ipynb`** — Data organization pipeline
- Ingests and normalizes land parcel records from public rural cadastres
- Structures ownership, area, environmental constraints, and geolocation data
- Produces a clean, queryable dataset from heterogeneous public sources

**`notebooks/rag_terrenos.ipynb`** — RAG pipeline
- Indexes unstructured documents (rural deeds, environmental reports, registration filings) into a FAISS vector store
- Enables natural language queries over property data: ownership history, environmental constraints, development potential
- Hybrid retrieval: dense (semantic) + sparse (keyword) for best recall on Brazilian legal terminology

---

## Data sources

| Source | Used for |
|--------|----------|
| INCRA (SNCR) | Rural property cadastre — owner, area, location |
| CAR | Cadastro Ambiental Rural — environmental overlay |
| SIGEF | Georeferenced rural properties with boundaries |

---

*Sibling project to [urban-space](https://github.com/MaxPower90/urban-space) — same methodology, rural markets.*
