# CMS Medicare Beneficiary Analytics Platform

> An end-to-end **Databricks lakehouse** implementing the medallion architecture 
> (Bronze → Silver → Gold) on **11 years (2015–2025) of CMS synthetic Medicare 
> beneficiary data** — 50M+ records, 200+ columns — with Unity Catalog governance, 
> data-quality observability, and a published AI/BI Dashboard.

![Architecture](docs/architecture.png)

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Pipeline Layers](#-pipeline-layers)
  - [Bronze Layer](#1-bronze-layer--raw-ingestion) · [📓 Notebook](https://github.com/AbenezerYBekele/CMS-Beneficiary-Data/blob/main/Bronze%20Layer%20Cms.ipynb)
  - [Silver Layer](#2-silver-layer--cleansed--reshaped) · [📓 Notebook](https://github.com/AbenezerYBekele/CMS-Beneficiary-Data/blob/main/Silver%20Layer%20CMS.ipynb)
  - [Gold Layer](#3-gold-layer--business-kpis) · [📓 Notebook](https://github.com/AbenezerYBekele/CMS-Beneficiary-Data/blob/main/Gold%20Layer%20CMS.ipynb)

---

## 🎯 Overview

CMS (Centers for Medicare & Medicaid Services) publishes beneficiary data as 
pipe-delimited CSVs where **200+ columns** include 12 monthly variants for each 
of 13 metric groups (e.g., `HMO_IND_01` … `HMO_IND_12`). The raw shape is 
impossible for BI tools to consume directly.

This project builds a **production-style lakehouse pipeline** that:

1. **Ingests** raw CSVs into a governed Bronze layer
2. **Reshapes** 156 monthly columns into a normalized long-format fact table
3. **Delivers** 9 business-ready KPI marts for analytics
4. **Monitors** data quality on every run
5. **Presents** insights through a 3-page AI/BI Dashboard

**Scale:** 11 years · 50M+ rows · 200+ raw columns · 23 Delta tables/views · 9 Gold KPIs

---
