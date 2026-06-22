# Data Analytics & Visual Report

## Dataset Focus: Davao Region Municipal Waste Generation and LGU Budgetary Allocations (2021–2025)
**Data Analyst:** Gavin Ross O. Javier  
**Target Audience:** Regional Policymakers and LGU Department Heads  
**Context:** Emergency Budgetary Resource Allocation (Davao Region)  
**Date:** June 2026  

---

## Executive Overview

Managing urban environmental realities requires real-time, clean data pipelines. Our department received a highly unorganized, multi-source dataset compiling daily municipal solid waste (MSW) log entries alongside actual localized budgetary spending across key provincial clusters in the Davao Region (Davao City, Davao del Norte, and Davao de Oro). 

To prepare for the upcoming legislative emergency session on municipal funding, an AI-driven data processing pipeline was utilized to scrub, standardize, and structure the data within a tight one-hour window. This unified report details the structural data cleaning protocols, presents high-contrast trend visualizations, and pairs them with a human-authored narrative checking automated findings against local socio-environmental realities.

---

## 1. Data Cleaning Protocol Log

The raw regional dataset arrived with severe formatting inconsistencies due to varying data logging protocols across different municipal engineering offices. 

### Data Discrepancies Identified:
* **Unit Mismatches:** Waste metrics were randomly logged in kilograms (kg) by some barangays and short tons by others, rather than standard Metric Tons (MT).
* **Missing Structural Data:** The `Budget_Allocation_PHP` column contained multiple null entries for the post-pandemic recovery fiscal year (2022).
* **String Corruptions:** Commas and currency symbols (`₱`, `PHP`) were baked directly into numerical columns, breaking Python/Pandas mathematical parsing engines.

### AI Processing Instructions Implemented:
> `"Scan the raw regional waste dataset. 1) Strip all non-numeric characters like '₱' and commas from the allocation column and cast the values to float64. 2) Identify all null rows in the 2022 budget tier and impute them using the median value of that specific municipality's historical spending. 3) Standardize all mass units to Metric Tons (MT) using a strict 1,000 kg = 1 MT conversion factor. Output a clean table summary."`

### Result & Optimization Summary:
The script successfully normalized **240 raw row inputs** across three major provincial clusters. The processing engine flagged and resolved 14 unit mismatches and structurally imputed 8 missing budget fields, establishing a clean baseline for immediate visualization.

---

## 2. Visualizations Generated

The cleaned dataset was mapped into two distinct, high-contrast visual matrices to isolate rapid trends for local government heads.

### Chart A: Waste Generation vs. Budgetary Tracking (2021–2025)

![Waste Generation vs Budgetary Tracking](../Visuals/CHART%20A.png)

*(Key Trend Visualized: The exponential upward trajectory of physical waste output vastly outpaces the linear, conservative growth of LGU environmental funding).*

### Chart B: Provincial Strain Breakdown (2025 Data Cut)

![Provincial Strain Breakdown](../Visuals/CHART%20B.png)

*(Key Trend Visualized: Extreme structural concentration of waste management pressure centered heavily inside the urban core of Davao City).*

---

## 3. Human Analytical Narrative (The 'Why' Factor)

An automated AI analysis of Chart A initially generated a superficial conclusion, stating that *"the continuous increase in regional solid waste is a natural byproduct of standard population expansion and urban growth spikes."* 

However, cross-referencing this data manually with regional economic timelines reveals a much more specific, systemic economic driver: **the aggressive post-pandemic expansion of rapid digital commerce, packaging footprints, and unchecked retail delivery services throughout urban Davao.**

The catastrophic data shift occurs between 2022 and 2023, where daily waste generation spiked by an unprecedented **52.9%** (climbing from 510 MT to 780 MT), while municipal budgetary allocations crawled forward by a meager **8.3%**. This massive divergence exposes a critical structural failure: local LGUs are managing modern, e-commerce-driven consumer waste volume using rigid, pre-pandemic fiscal frameworks. 

### Core Actionable Takeaways for Policy Resource Allocation:
1. **Urgent Budget Realignment:** The Sangguniang Panlungsod needs to decouple the solid waste management budget from fixed historical baselines and index it directly to real-time municipal weight sensor data.
2. **Infrastructure Investment:** Funding must shift immediately away from mere landfill maintenance and toward establishing integrated material recovery facilities (MRFs) across high-density barangays. This will systematically reduce the physical mass reaching the regional urban landfills.

---
*Prepared by: Gavin Ross O. Javier*  
*Program/Affiliation: BS Finance · Ateneo de Davao University*  
*Classification: Verified Data Report for Legislative Review*
