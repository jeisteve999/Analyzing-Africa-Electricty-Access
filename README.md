# Analyzing-Africa-Electricty-Access
Analyzing electricity access across Africa using Python, Pandas, NumPy, Matplotlib, and Seaborn.

# ⚡ Electricity Access in Africa

### World Bank World Development Indicators (WDI) | 1990–2024

An exploratory data analysis of **access to electricity across 54 African countries**, built with Python and data from the World Bank's World Development Indicators (WDI).

The project focuses on cleaning and reshaping raw World Bank data, enriching it with country metadata, and analyzing differences in electricity access across countries, income groups, and time.

The analysis uses **access to electricity (% of population)** as an indicator of public service delivery and explores where access is highest, where it remains limited, and which countries have made the greatest progress.

> 📊 Prepared as an open-data contribution to support my volunteer work with [OpenGovAfrica](https://github.com/OpenGovAfrica), focused on governance, transparency, and public-service analysis across Africa.

---

## 🎯 Research Questions

This project explores four main questions:

1. Which African countries have the highest and lowest access to electricity?
2. How has electricity access changed over time?
3. Which countries have improved the most since 2000?
4. How does electricity access vary across income groups?

---

## 🔎 Key Findings

### 🌍 Large differences across countries

Electricity access remains highly unequal across the continent.

In 2024, the highest levels of access in the analyzed dataset included:

* 🇩🇿 Algeria — **100%**
* 🇪🇬 Egypt — **100%**
* 🇸🇨 Seychelles — **100%**
* 🇹🇳 Tunisia — **100%**
* 🇲🇺 Mauritius — **100%**

At the lower end:

* 🇧🇮 Burundi — **20.1%**
* 🇨🇫 Central African Republic — **18.2%**
* 🇲🇼 Malawi — **15.6%**
* 🇹🇩 Chad — **13.4%**
* 🇸🇸 South Sudan — **5.4%**

This represents a gap of approximately **95 percentage points** between the highest and lowest countries in the 2024 analysis.

### 📈 Countries with significant improvement

Comparing 2000 with 2024, several countries experienced substantial increases in electricity access:

* 🇸🇿 Eswatini: **+68.9 percentage points**
* 🇷🇼 Rwanda: **+65.8 percentage points**

Kenya also shows a strong improvement over time, particularly after 2010, eventually overtaking Nigeria in the analysis.

### 📉 Declining access

Libya is the main example of a substantial decline in the analyzed period, decreasing from approximately **99.8% in 2000 to 77.4% in 2024**.

### 💰 Income groups

The analysis suggests a relationship between income group and electricity access, but income alone does not explain the full picture.

Lower-middle- and upper-middle-income countries show considerable variation in access levels, highlighting the importance of looking beyond country income when analyzing public-service outcomes.

---

## 📊 Visualizations

The project includes several visualizations designed to make the differences and trends easier to understand:

* **Highest vs. lowest electricity access** — comparison of the five highest and five lowest countries.
* **Electricity access over time** — trends for selected African countries.
* **2024 distribution** — overall distribution of electricity access across the continent.
* **Growth vs. current access** — relationship between improvement since 2000 and current access levels.
* **Income group comparison** — electricity access across World Bank income classifications.
* **Continental distribution** — summary of countries by access category.
* **Animated bar chart** — evolution of electricity access over time.
* **Summary table** — comparison of 2000 access, 2024 access, and percentage-point change.

The repository also includes an interactive HTML animation:

`electricity_animation.html`

---

## 🗂️ Data

### Source

All data comes from the **World Bank World Development Indicators (WDI)**.

**Main indicator:**

> Access to electricity (% of population)
> Indicator code: `EG.ELC.ACCS.ZS`

The World Bank data is provided under the **CC BY 4.0 license**.

### Raw files

The analysis uses the following WDI files:

| File             | Description                                                                    |
| ---------------- | ------------------------------------------------------------------------------ |
| `WDICSV.csv`     | Main WDI dataset containing country × indicator observations and yearly values |
| `WDICountry.csv` | Country metadata, including region and income group                            |
| `WDISeries.csv`  | Indicator metadata, including definitions and topics                           |

The raw WDI files are approximately **189 MB** and are not included in the repository.

The project uses the **1990–2024** period for the electricity-access analysis.

---

## 🧹 Methodology

The analysis follows these main steps:

### 1. Load and explore the raw WDI data

* Load the World Bank CSV files.
* Inspect the structure of the datasets.
* Review entities, indicators, metadata, and available years.

### 2. Clean and reshape the data

* Reshape the WDI dataset into a long analytical format.
* Convert year values to numeric fields.
* Handle missing values and potential duplicates.
* Restrict the analysis to the relevant period.

### 3. Identify African countries

The analysis focuses on **54 African countries**, combining countries from Sub-Saharan Africa with the North African countries included in the project.

### 4. Enrich the dataset

Country-level metadata is added to provide additional context, including:

* Country
* Region
* Income group
* Electricity access

### 5. Filter the electricity indicator

The analysis focuses on:

`EG.ELC.ACCS.ZS`

**Access to electricity (% of population)**

### 6. Create the analytical dataset

The data is transformed into a country × year structure to facilitate:

* Time-series analysis
* Country comparisons
* Growth calculations
* Distribution analysis
* Income-group comparisons

### 7. Classify 2024 electricity access

Countries are grouped into three categories:

| Category  |    Access |
| --------- | --------: |
| 🟢 High   |     ≥ 80% |
| 🟡 Medium | 40%–79.9% |
| 🔴 Low    |     < 40% |

### 8. Measure improvement

Change between **2000 and 2024** is calculated in percentage points.

The analysis uses 2000 as the starting point because only a small number of countries have electricity-access observations available from 1990.

### 9. Visualize the results

Visualizations are created using:

* **Matplotlib**
* **Seaborn**
* **Plotly**

---

## 🛠️ Technologies

| Tool                      | Purpose                                    |
| ------------------------- | ------------------------------------------ |
| 🐍 Python                 | Data analysis and workflow                 |
| 🐼 Pandas                 | Data cleaning, transformation and analysis |
| 🔢 NumPy                  | Numerical operations                       |
| 📊 Matplotlib             | Static visualizations                      |
| 🎨 Seaborn                | Statistical visualizations                 |
| 📈 Plotly                 | Interactive visualizations                 |
| 🌍 World Bank WDI         | Primary data source                        |
| 📓 Jupyter / Google Colab | Development environment                    |

---

## ⚠️ Limitations

Several limitations should be considered when interpreting the results:

* Some countries have missing observations for earlier years.
* World Bank datasets may contain estimated values and can be updated as methodologies and source data improve.
* Income-group classifications are treated as current categories rather than historical classifications for every year.
* Country-level comparisons are not population-weighted in the project's analytical calculations.
* Electricity access is only one dimension of public-service delivery and does not capture reliability, affordability, quality, or regional disparities within countries.

---

## 🚀 Next Steps

Possible extensions of the project include:

* Analyze **rural vs. urban electricity access**.
* Incorporate **population-weighted analysis**.
* Compare electricity access with **government spending**.
* Explore relationships with **GDP and other socioeconomic indicators**.
* Analyze the relationship between electricity access and broader **public-service outcomes**.
* Extend the project toward a broader **budget-vs-service-delivery analysis**.

---

## 📁 Repository Structure

```text
Analyzing_Africa_Electricity_Access/
│
├── Analyzing_Africa_Electricty_Access.ipynb
├── electricity_animation.html
├── README.md
└── data/
    ├── WDICSV.csv
    ├── WDICountry.csv
    └── WDISeries.csv
```

> **Note:** The raw WDI files are not included in the repository because of their size. Download the World Bank WDI CSV bundle and place the required files in the location expected by the notebook.

---

## ▶️ How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd Analyzing_Africa_Electricity_Access
```

### 2. Install the required libraries

```bash
pip install pandas numpy matplotlib seaborn plotly
```

### 3. Download the World Bank WDI data

Download the WDI CSV dataset and place:

```text
WDICSV.csv
WDICountry.csv
WDISeries.csv
```

in the directory expected by the notebook.

### 4. Open the notebook

The analysis can be run using:

* **Google Colab**
* **Jupyter Notebook**
* **JupyterLab**

---

## 🌍 Why This Project?

This project combines **data analysis, public-sector data, and data storytelling** to explore a real-world development question.

Rather than only producing visualizations, the workflow follows a structured analytical process:

**Raw data → Data cleaning → Transformation → Enrichment → Analysis → Visualization → Insights**

The project is also part of my broader interest in using data and automation to support **evidence-based decision-making and public-service analysis**.

---

## 👤 Author

**Jeisson Rojas**

Data Analyst | Automation Specialist | Psychology Background

Interested in:

* Data Analytics
* Business Intelligence
* Data Automation
* NLP
* Predictive Models
* Public-sector and development data

GitHub: [@jeisteve999](https://github.com/jeisteve999)

---

## 📚 Data Source & License

**World Bank — World Development Indicators**

Indicator: **Access to electricity (% of population)**
Code: `EG.ELC.ACCS.ZS`

Data license: **CC BY 4.0**

Source: [World Bank Data](https://data.worldbank.org/)
