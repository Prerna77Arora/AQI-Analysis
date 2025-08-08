# Nuts_And_bolts_of_machine_learning
My learning during Advanced Google Analytic Course...

# 📊 Air Quality Data Distribution & Analysis

## 📌 Business Scenario
You are presented with a **business scenario** and a dataset to explore the scenario.  
You will practice determining the **type of probability distribution** that fits the data, calculating **Z-scores**, detecting **outliers**,  
and computing **mean, median, minimum, and maximum values** to uncover and analyze insights from the dataset.

## 🛠 How to Use This Project in Jupyter Notebook
1. **Open Jupyter Notebook** on your system or in an online environment (e.g., JupyterLab, Google Colab).
2. **Place the dataset** file (`modified_c4_epa_air_quality.csv` or `c4_epa_air_quality.csv`) in the same directory as your notebook.
3. **Follow the step-by-step workflow** in the notebook:
   - Load the dataset using Pandas.
   - Explore the distribution using histograms, boxplots, and statistical summaries.
   - Calculate probability distribution metrics.
   - Detect and analyze outliers.
   - Compute mean, median, min, and max values.
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

## 📊 Example Workflow

```python
import pandas as pd
import numpy as np 

# Load the dataset
df = pd.read_csv("modified_c4_epa_air_quality.csv")

# View basic statistics
print(df.describe())

# Calculate mean, median, min, and max for AQI
mean_aqi = df["aqi_log"].mean()
median_aqi = df["aqi_log"].median()
min_aqi = df["aqi_log"].min()
max_aqi = df["aqi_log"].max()

print(f"Mean: {mean_aqi}, Median: {median_aqi}, Min: {min_aqi}, Max: {max_aqi}")

# Detect outliers using Z-score
from scipy import stats
import numpy as np

z_scores = np.abs(stats.zscore(df["aqi_log"]))
outliers = df[z_scores > 3]
print(outliers)
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
