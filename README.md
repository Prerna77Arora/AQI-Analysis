# Nuts_And_bolts_of_machine_learning
My learning during Advanced Google Analytic Course...

# 📊 Air Quality Data Distribution & Analysis

## 📌 Business Scenario
You are presented with a **business scenario** and a dataset to explore the scenario.  
You will practice determining the **type of probability distribution** that fits the data, calculating **Z-scores**, detecting **outliers**,  
and computing **mean, median, minimum, and maximum values** to uncover and analyze insights from the dataset.

## 🛠 How to Use This Project in Jupyter Notebook
1. **Open Jupyter Notebooks** on your system or in an online environment (e.g., JupyterLab, Google Colab).
2. **Place the dataset** file (`modified_c4_epa_air_quality.csv` or `c4_epa_air_quality.csv`) in the same directory as your notebook.
3. **Run the Analysis**  
   Follow the provided Python workflow.
4. **Run each cell** sequentially to reproduce the analysis.

---

## 📂 Data Dictionary

### Dataset 1: modified_c4_epa_air_quality.csv
**Rows:** 260  
**Columns:** 8

| Column Name       | Type      | Description |
|-------------------|-----------|-------------|
| date_local        | datetime  | Date of AQI reading |
| state_name        | str       | Name of the state |
| county_name       | str       | Name of the U.S. county |
| city_name         | str       | U.S. City where monitoring occurred |
| local_site_name   | str       | Identifier of the site in the owning agency's nomenclature |
| parameter_name    | str       | Description of the parameter measured |
| units_of_measure  | str       | Standard unit of measure |
| aqi_log           | int       | Log-transformed AQI reading |

### Dataset 2: c4_epa_air_quality.csv
**Rows:** 260  
**Columns:** 10

| Column Name       | Type      | Description |
|-------------------|-----------|-------------|
| [None]            | int       | Index |
| date_local        | datetime  | Date of AQI reading |
| state_name        | str       | Name of the state |
| county_name       | str       | Name of the U.S. county |
| city_name         | str       | U.S. City where monitoring occurred |
| local_site_name   | str       | Identifier of the site in the owning agency's nomenclature |
| parameter_name    | str       | Description of the parameter measured |
| units_of_measure  | str       | Standard unit of measure |
| arithmetic_mean   | int       | Mean of observed pollutant data values for the quarterly dataset |
| aqi               | int       | Air Quality Index (0-500 scale) |

---

## 🧮 Example Workflow

```python
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from scipy import stats

# Load dataset
df = pd.read_csv("modified_c4_epa_air_quality.csv")

# Descriptive statistics
print(df.describe())

# Mean, Median, Min, Max
mean_aqi = df["aqi_log"].mean()
median_aqi = df["aqi_log"].median()
min_aqi = df["aqi_log"].min()
max_aqi = df["aqi_log"].max()

print(f"Mean: {mean_aqi}, Median: {median_aqi}, Min: {min_aqi}, Max: {max_aqi}")

# Outliers using Z-score
z_scores = np.abs(stats.zscore(df["aqi_log"]))
outliers = df[z_scores > 3]
print(outliers)

# Seaborn Boxplot
sns.boxplot(x=df["aqi_log"])
plt.title("AQI Log Distribution")
plt.show()

# Confidence Interval (95%)
confidence = 0.95
n = len(df["aqi_log"])
mean = np.mean(df["aqi_log"])
std_err = stats.sem(df["aqi_log"])
h = std_err * stats.t.ppf((1 + confidence) / 2, n - 1)

print(f"{confidence*100}% confidence interval: ({mean-h}, {mean+h})")
```

---

## 📚 References
- [EPA Air Quality Data](https://www.epa.gov/outdoor-air-quality-data)
- [AirNow](https://www.airnow.gov/)
- [Z-Score Explanation - Wikipedia](https://en.wikipedia.org/wiki/Standard_score)

---

## 📄 License
This project is for **educational purposes only**.  
Dataset is adapted from publicly available EPA resources.
