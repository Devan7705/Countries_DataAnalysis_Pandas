# 🌍 World Countries — Pandas Data Analysis

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-1.x-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

> A hands-on Pandas practice project exploring a rich dataset of **194 countries** across **64 features** — covering demographics, economics, energy, health, politics, and more.

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Dataset](#-dataset)
- [Project Structure](#-project-structure)
- [Analyses Performed](#-analyses-performed)
- [Key Findings](#-key-findings)
- [Technologies Used](#-technologies-used)
- [Getting Started](#-getting-started)
- [Skills Practiced](#-skills-practiced)

---

## 🔍 Overview

This project is a **Pandas practice notebook** designed to build proficiency in real-world data extraction and analysis. Using a comprehensive world countries dataset, various queries are answered programmatically — ranging from population rankings and regional counts to political insights and democracy scores.

---

## 📊 Dataset

| Property | Details |
|---|---|
| **File** | `Countries.csv` |
| **Rows** | 194 (one per country) |
| **Columns** | 64 features |
| **Source** | World Countries Aggregated Dataset |

### Feature Categories

The dataset contains a rich mix of columns spanning multiple domains:

| Category | Features |
|---|---|
| 🗺️ **Geographic** | `country`, `country_long`, `capital_city`, `region`, `continent`, `latitude`, `longitude` |
| 💰 **Economic** | `gdp`, `inflation`, `unemployment_pct`, `tax_revenue_pct_gdp`, `central_government_debt_pct_gdp` |
| 👥 **Demographic** | `population`, `rural_population`, `urban_population`, `birth_rate`, `death_rate`, `median_age` |
| ⚡ **Energy** | `electricity_access_pct`, `fossil_energy_consumption_pct`, `renewable_energy_consumption_pct` |
| 🏥 **Health** | `health_expenditure_pct_gdp`, `life_expectancy`, `hospital_beds`, `suicide_rate` |
| 🗳️ **Political** | `democracy_score`, `democracy_type`, `political_leader`, `title`, `press` |
| 🌱 **Environment** | `co2_emissions`, `methane_emissions`, `forest_area`, `agricultural_land` |

---

## 📁 Project Structure

```
world-countries-pandas/
│
├── 📓 Countires.ipynb       # Main Jupyter Notebook with all analyses
├── 📄 Countries.csv         # Dataset (194 countries × 64 features)
└── 📘 README.md             # Project documentation (this file)
```

---

## 🔬 Analyses Performed

### 1. 📥 Data Loading & Preview
- Imported the dataset using `pd.read_csv()`
- Previewed with `df.head()` to understand structure

### 2. 🔧 Feature Engineering
- Created a new derived column:
  ```python
  df['Total_Population'] = df['rural_population'] + df['urban_population']
  ```

### 3. 🌐 Population Analysis
| Query | Method Used |
|---|---|
| Country with **highest** population | `df[df['Total_Population'] == df['Total_Population'].max()]` |
| Capital of most populous country | Boolean indexing with column selection |
| Country with **least** population | `df[df['Total_Population'] == df['Total_Population'].min()]` |
| Capital of least populous country | Combined multi-column filtering |
| Top most populous country (full row) | `df.nlargest(1, 'Total_Population')` |

### 4. 🗳️ Democracy Analysis
- **Top 5 countries by democracy score** using `df.nlargest(5, 'democracy_score')`

### 5. 🗺️ Regional Analysis
- **Unique regions** in the dataset using `df['region'].nunique()`
- **Countries in Eastern Europe** using `df[df['region'] == 'Eastern Europe']`

### 6. 👤 Political Leadership Insights
- Political leader of the **2nd most populous country** using `nlargest` + `iloc`
- Countries with **no political leader recorded** using `.isna()` filtering

### 7. 🌍 Continental Filtering
- Most populous country in **Africa** using chained filtering with `nlargest`

### 8. 🔤 String Search
- All countries with the word **"Republic"** in their official name using a `for` loop with `in` keyword:
  ```python
  for i in df['country_long']:
      if 'Republic' in i:
          print(i)
  ```

---

## 💡 Key Findings

> *(Sample insights from the analysis — actual outputs visible in the notebook)*

- 🇨🇳 **China** holds the highest total population in the dataset
- 🇮🇳 **India** is the country with the 2nd highest population
- **Norway / Sweden / Iceland** rank among the top for democracy scores (score close to 9.87)
- **Eastern Europe** contains a notable cluster of countries within the dataset
- A significant number of countries carry the word **"Republic"** in their official name
- Some entries have **no political leader recorded**, reflecting data gaps or unique governance structures

---

## 🛠️ Technologies Used

| Tool | Purpose |
|---|---|
| **Python 3.x** | Core programming language |
| **Pandas** | Data loading, filtering, aggregation, feature engineering |
| **NumPy** | Numerical support (imported alongside Pandas) |
| **Jupyter Notebook** | Interactive development environment |

---

## 🚀 Getting Started

### Prerequisites

Make sure you have Python 3.x installed along with the required libraries.

```bash
pip install pandas numpy jupyter
```

### Run the Notebook

```bash
# Clone or download the project files
# Navigate to the project directory

jupyter notebook Countires.ipynb
```

> **Note:** Keep `Countries.csv` in the same directory as the notebook, as it is loaded with a relative path: `pd.read_csv("Countries.csv")`

---

## 🎯 Skills Practiced

This project helped reinforce the following **core Pandas concepts**:

- ✅ Reading CSV files with `pd.read_csv()`
- ✅ Exploring data with `.head()`, `.shape`, `.dtypes`
- ✅ **Boolean indexing** for conditional filtering
- ✅ **Feature engineering** (creating new derived columns)
- ✅ Aggregation with `.max()`, `.min()`, `.nunique()`
- ✅ Ranking with `.nlargest()` / `.nsmallest()`
- ✅ Positional access with `.iloc[]`
- ✅ Handling missing values with `.isna()`
- ✅ String searching within column values
- ✅ Multi-column selection and chained filtering

---

## 📬 Author

> Built as a **self-practice project** to strengthen data analysis skills using Pandas on a real-world dataset.

---

<div align="center">

⭐ *If you found this project helpful, consider giving it a star!* ⭐

</div>