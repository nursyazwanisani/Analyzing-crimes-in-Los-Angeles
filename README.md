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

---

## 4. Project Structure

```
├── crimes.csv
├── la_skyline.jpg
├── notebook.ipynb
├── README.md
└── ANALYSIS.md
```

---

## 5. Analysis Summary

See [ANALYSIS.md](ANALYSIS.md) for a plain-English summary of the findings.

---

## 6. Course

This project was completed as part of the **DataCamp Associate Data Scientist in Python** career track.
