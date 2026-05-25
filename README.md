<div align="center">

# solo-inteligente

**Automated Terrain Scouting: Leveraging AI for Streamlined Residential Development in São Paulo.**

![Python](https://img.shields.io/badge/Python-0d1117?style=for-the-badge&logo=python&logoColor=58a6ff)
![FAISS](https://img.shields.io/badge/FAISS-0d1117?style=for-the-badge&logoColor=58a6ff)
![pandas](https://img.shields.io/badge/pandas-0d1117?style=for-the-badge&logo=pandas&logoColor=58a6ff)
![SQLite](https://img.shields.io/badge/SQLite-0d1117?style=for-the-badge&logo=sqlite&logoColor=58a6ff)

</div>

---

## The Problem

São Paulo's 2023 directorial plan charts an ambitious roadmap: densify the sparsely populated central regions while curbing the mass daily commute from the densely populated outskirts. New zoning rules allow higher-density construction near transit hubs — train/metro stations, major bus corridors. This creates a window for construction companies to acquire underutilized lots before the market prices in the new regulations.

The bottleneck: lot scouting is done by "perdigueiros" — named after the Portuguese Pointer hunting dog. These professionals comb the city using Google Maps, GeoSampa, or plain footwork, marking potential construction sites one by one. It's slow, labor-intensive, and can't scale to meet the demand the new plan unlocks.

This project replaces that process with an AI-powered pipeline.

---

## What it does

**`notebooks/organiza_terrenos.ipynb`** — Data ingestion & normalization

Aggregates public land parcel data from INCRA, CAR, and SIGEF registries — normalizing ownership records, lot boundaries, area measurements, and environmental constraints into a clean, queryable dataset.

**`notebooks/rag_terrenos.ipynb`** — Similarity search & RAG pipeline

- **PCA + KNN** — reduces dimensionality across zoning class, IPTU fiscal value, floor-area ratio, lot area, proximity to transit, and socioeconomic features; finds lots structurally similar to known high-potential parcels across 11M+ IPTU records
- **FAISS vector store** — indexes unstructured documents (rural deeds, environmental reports, registration filings) for semantic retrieval
- **Hybrid retrieval** — dense (semantic) + sparse (keyword/BM25) for best recall on Brazilian legal and zoning terminology
- **Natural language interface** — query the parcel dataset in plain language: ownership history, environmental constraints, development potential, proximity to transit

---

## Context

São Paulo's central paradox: the core of the richest city in Latin America is underpopulated because large, antiquated properties inflate land prices, pushing residents to the periphery. The 2023 plan targets exactly these parcels. Identifying them before competitors — and before the market adjusts — is the entire edge this system creates.

---

## Data sources

| Source | Used for |
|--------|----------|
| INCRA (SNCR) | Rural property cadastre — owner, area, location |
| CAR | Cadastro Ambiental Rural — environmental constraints overlay |
| SIGEF | Georeferenced rural properties with certified boundaries |
| GeoSampa (PMSP) | Urban IPTU records, zoning, floor-area ratio |

---

*Urban counterpart: [urban-space](https://github.com/Guicicca90/urban-space) — same ML methodology applied to the city.*
