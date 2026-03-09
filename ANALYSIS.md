# 🔍 LA Crime Analysis — Summary of Findings

> DataCamp Data Science Project | LAPD Crime Dataset | 2020

---

## 1. Project Overview

This project analyses Los Angeles Police Department (LAPD) crime data from 2020, covering approximately **185,715 recorded incidents** across the city's 21 geographic patrol divisions. The aim was to identify patterns in when crimes occur, where night-time crime is most concentrated, and which demographic groups are most affected as victims.

---

## 2. Dataset

A single file was used: **`crimes.csv`** — a modified version of publicly available data from [Los Angeles Open Data](https://data.lacity.org/).

Key columns used in analysis:

| Column | Role in Analysis |
|--------|-----------------|
| `TIME OCC` | Extracted hour-of-day to find peak crime times |
| `AREA NAME` | Identified highest night-crime patrol division |
| `Vict Age` | Grouped into age brackets to find most affected demographic |

---

## 3. Key Findings

### 3.1 Peak Crime Hour

| Finding | Value |
|---------|-------|
| 🕛 Hour with the most crimes | **12:00 (noon)** |

Crimes peak at **midday (12:00)**. This likely reflects a combination of factors — higher foot traffic, more people active outdoors, and more opportunity for crimes such as theft and robbery during lunch hours.

---

### 3.2 Night-Time Crime by Area

Night-time was defined as crimes occurring **before 4:00 AM or from 10:00 PM onwards**.

| Finding | Value |
|---------|-------|
| 🌙 Area with most night-time crime | **Central** |

The **Central** division records the highest volume of night-time crime among all 21 LAPD patrol areas. This is consistent with Central's coverage of downtown LA, which sees significant late-night activity including nightlife, homelessness, and transient populations.

---

### 3.3 Victim Age Distribution

Victims were grouped into the following age brackets:

| Age Bracket | Number of Victims |
|-------------|-------------------|
| **26–34** | **47,470** ✅ Most affected |
| 35–44 | 42,157 |
| 45–54 | 28,353 |
| 18–25 | 28,291 |
| 55–64 | 20,169 |
| 65+ | 14,747 |
| 0–17 | 4,528 |

The **26–34 age group** is by far the most frequently victimised, likely because this group is most active in public spaces, commuting, and nightlife. Crime rates generally decrease with age.

---

## 4. Data Processing Steps

1. Loaded `crimes.csv` using `pandas`, with `TIME OCC` read as a string to preserve leading zeros
2. Extracted the **hour of occurrence** from `TIME OCC` by taking the first two characters and converting to integer
3. Visualised crime count by hour using `seaborn.countplot`
4. Identified the **peak crime hour** using `value_counts().idxmax()`
5. Filtered records to **night-time hours** (before 04:00 or from 22:00) using boolean masking
6. Counted night-time crimes per LAPD area and identified the **highest-crime area**
7. Created **age brackets** using `pd.cut()` with custom bins
8. Counted victims per age bracket to identify the **most affected demographic**

---

## 5. Skills Demonstrated

- Feature engineering from raw string data (military time → hour integer)
- Data visualisation with `matplotlib` and `seaborn`
- Frequency analysis using `value_counts()`
- Boolean filtering with compound conditions
- Age binning with `pd.cut()` and custom labels
- Exploratory Data Analysis (EDA) for a real-world public safety dataset

---

*Completed as part of the [DataCamp Data Scientist Career Track](https://www.datacamp.com)*
