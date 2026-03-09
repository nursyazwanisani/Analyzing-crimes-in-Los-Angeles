# Analyzing Los Angeles Crime Patterns

> A DataCamp Data Science bonus project helping the LAPD identify crime patterns using real 2020 data.

![la_skyline](https://github.com/user-attachments/assets/b05b42bb-99e1-49a7-8282-980239ea0c79)

---

## 1. Project Overview

Los Angeles — the City of Angels — is one of the most iconic cities in the world. But like any major metropolis, it faces a large volume of crime. In this project, we analyse real LAPD crime data to uncover patterns in criminal behaviour across time of day, location, and victim demographics.

The goal is to provide actionable insights that help the **Los Angeles Police Department (LAPD)** allocate resources more effectively.

---

## 2. Dataset

A single dataset is used: **`crimes.csv`**

The dataset contains **~185,715 crime records** from 2020.

| Column | Description |
|--------|-------------|
| `DR_NO` | Division of Records Number (official file number) |
| `Date Rptd` | Date the crime was reported (MM/DD/YYYY) |
| `DATE OCC` | Date the crime occurred (MM/DD/YYYY) |
| `TIME OCC` | Time of occurrence in 24-hour military format |
| `AREA NAME` | Geographic patrol division name |
| `Crm Cd Desc` | Description of the crime committed |
| `Vict Age` | Victim's age in years |
| `Vict Sex` | Victim's sex: `F` (Female), `M` (Male), `X` (Unknown) |
| `Vict Descent` | Victim's ethnic descent (coded) |
| `Weapon Desc` | Description of weapon used, if applicable |
| `Status Desc` | Current status of the crime case |
| `LOCATION` | Street address where the crime occurred |

---

## 3. Skills Demonstrated

- **Data loading and inspection** with `pandas`
- **Feature engineering** — extracting hour-of-day from military time strings
- **Exploratory Data Analysis (EDA)** with `matplotlib` and `seaborn`
- **Frequency analysis** — identifying peak crime hours and high-crime areas
- **Binning and categorisation** — grouping victim ages into demographic brackets
- **Conditional filtering** — isolating night-time crime records

---

## 4. Getting Started

### 4.1 Prerequisites

```bash
pip install pandas numpy matplotlib seaborn
```

### 4.2 Run the Notebook

```bash
jupyter notebook notebook.ipynb
```

---

## 3. Key Questions Explored

- At what hour of the day do most crimes occur?
- Which LAPD area has the highest volume of night-time crime?
- Which victim age group is most frequently affected by crime?

Key columns used in analysis:

| Column | Role in Analysis |
|--------|-----------------|
| `TIME OCC` | Extracted hour-of-day to find peak crime times |
| `AREA NAME` | Identified highest night-crime patrol division |
| `Vict Age` | Grouped into age brackets to find most affected demographic |

---

## 4. Key Findings

### 4.1 Peak Crime Hour

| Finding | Value |
|---------|-------|
| 🕛 Hour with the most crimes | **12:00 (noon)** |

Crimes peak at **midday (12:00)**. This likely reflects a combination of factors — higher foot traffic, more people active outdoors, and more opportunity for crimes such as theft and robbery during lunch hours.

### 4.2 Night-Time Crime by Area

Night-time was defined as crimes occurring **before 4:00 AM or from 10:00 PM onwards**.

| Finding | Value |
|---------|-------|
| 🌙 Area with most night-time crime | **Central** |

The **Central** division records the highest volume of night-time crime among all 21 LAPD patrol areas. This is consistent with Central's coverage of downtown LA, which sees significant late-night activity including nightlife, homelessness, and transient populations.

### 4.3 Victim Age Distribution

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

## 5. Data Processing Steps

1. Loaded `crimes.csv` using `pandas`, with `TIME OCC` read as a string to preserve leading zeros
2. Extracted the **hour of occurrence** from `TIME OCC` by taking the first two characters and converting to integer
3. Visualised crime count by hour using `seaborn.countplot`
4. Identified the **peak crime hour** using `value_counts().idxmax()`
5. Filtered records to **night-time hours** (before 04:00 or from 22:00) using boolean masking
6. Counted night-time crimes per LAPD area and identified the **highest-crime area**
7. Created **age brackets** using `pd.cut()` with custom bins
8. Counted victims per age bracket to identify the **most affected demographic**

---

## 6. Project Structure

```
├── crimes.csv
├── notebook.ipynb
└── README.md
```

---

## 7. Course

This project was completed as part of the **DataCamp Associate Data Scientist in Python** career track.
