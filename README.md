# Enumeration-Area-Delineation-for-West-Tselemti-Woreda
Sample enumeration and Supervisors area to conduct Household surveys in Ethiopia 
# Enumeration Area Delineation – West Tselemti Woreda

This repository documents the **Enumeration Area (EA)** delineation process for **West Tselemti Woreda**, developed to support population-based humanitarian assessments, survey sampling, and field supervision structures.  
The work can be implemented using **ArcGIS Pro** or QGIS.

---

## 🧭 Project Overview
The project established **balanced, population-based enumeration areas** that are operationally manageable for field enumerators and supervisors.  
Each EA represents a residential cluster, designed to optimize data collection efficiency and ensure statistical consistency across the woreda.

### Objectives
- Create **balanced EAs** based on residential population and building counts.  
- Segment **West Tselemti Woreda** into **enumerator- and supervisor-level zones**.  
- Exclude non-residential zones (commercial, industrial, and administrative).  
- Enable quality control through **sample re-validation and spatial deviation monitoring**.

---

## 🗂️ Data Sources

| Dataset | Source | Description |
|----------|---------|-------------|
| **WorldPop Population Data** | [worldpop.org](https://www.worldpop.org) | Gridded population estimates used for population balancing. |
| **Meta Population Data** | Meta (Facebook Data for Good) | Supplemental population distribution dataset. |
| **Microsoft Building Footprints** | Microsoft Open Data | Base geometry for residential building counts. |
| **Google Footprints & Imagery** | Google Maps / Earth | Used for settlement density validation. |
| **Administrative Boundaries** | CSA / OCHA | Woreda and kebele reference layers. |

---

## ⚙️ Methodology

### 1. Data Preparation
- Filtered building footprints to **residential-only** features.  
- Combined **WorldPop** and **Meta population** data to assign estimated population per building.  
- Defined woreda boundary as the **analysis mask**.

### 2. Territory Design (EAs)
- Implemented **ArcGIS Pro Territory Design Tools**.  
- Applied balancing variables:
  - **Population target:** 2,000–3,000 individuals  
  - **Buildings per EA:** 300–700 residential structures  
- Weights: 90% population, 10% building count.  
- **Sparse rural areas** have *larger coverage*; **dense urban areas** have *smaller coverage*.

### 3. Supervisor-Level Zones
- Aggregated **10 or more enumeration areas** into each **Supervisor Area (SA)**.  
- Supervisors conduct **validation sampling**:
  - From each EA (e.g., 10 sampled HHs), supervisors re-survey **2–3 of the same households**.  
  - Ensures **data verification** and field accuracy.

### 4. Spatial Validation Rule
- Household GPS coordinates collected via **KoBoCollect**.  
- If recorded locations deviate by **>100 m** from expected EA centroid or reference point,  
  the **form flags the deviation** automatically in Kobo for review.  
- This ensures **geo-reference accuracy** and strengthens **data quality control**.

### 5. Quality Assurance
- Manual inspection of EA and SA boundaries for logical continuity.  
- Summary tables generated for total population, number of buildings, and area per EA.

---

## 📦 Outputs
| File | Description |
|------|--------------|
| `EA_Boundaries_WestTselemti.shp` / `.gdb` | Final enumeration polygons. |
| `Supervisor_Zones_WestTselemti.shp` | Supervisor-level zones. |
| `EA_Population_Summary.csv` | Population, buildings, and coverage statistics. |
| `EA_Map_Outputs.pdf` | Visual map outputs for reference. |

---

## 🧩 Notes
- Designed for **population balance**, not equal geographic size.  
- **Sparse areas → larger EAs**, **dense areas → smaller EAs**.  
- Commercial and administrative structures excluded.  
- Coordinate System: **WGS 1984 / UTM Zone 37N**.  
- Validation workflow embedded in **KoBo forms** for automated flagging.

---

## 🛰️ Applications
- Census and **household survey planning**  
- **Sampling frame design** and field supervision  
- **Humanitarian needs assessments**  
- **M&E systems** and **conflict-sensitive spatial analysis**

---

## 👤 Author
**Abraham Zelalem Admassie**  
*Data Analyst / GIS Specialist*  
**Tools:** ArcGIS Pro 3.x | QGIS with QGIS plugin| Python Geopandas | Google Earth Engine | Power BI | KoBoToolbox  
**Date:** October 2025  

---

### 📚 Reference
Esri (2025). *Balance Territories for a National Census.* Learn ArcGIS Project.  
[https://learn.arcgis.com/en/projects/balance-territories-for-a-national-census/](https://learn.arcgis.com/en/projects/balance-territories-for-a-national-census/)

