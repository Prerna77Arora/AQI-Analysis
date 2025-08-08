# Nuts_And_bolts_of_machine_learning
My learning during Advanced Google Analytic Course...
# AQI Distribution Analysis

## 📌 Overview
This repository contains a Jupyter Notebook lab activity focused on exploring **how data across a dataset is distributed** and identifying **data points that need further examination**.  
The primary objectives are to:
- Determine the type of probability distribution that fits the data
- Calculate **z-scores**
- Detect **outliers**
- Understand the dataset’s distribution

The lab uses **Air Quality Index (AQI)** data from the United States Environmental Protection Agency (EPA) and a **modified dataset** designed for educational purposes.

---

## 📂 Dataset Information
**File Name:** `modified_c4_epa_air_quality.csv`  
**Source:** Adapted from the [EPA's AQI Data Repository](https://www.epa.gov/outdoor-air-quality-data) for pedagogical use  
**Rows:** 260  
**Columns:** 8

### **Data Dictionary**
| Column Name       | Type     | Description |
|-------------------|----------|-------------|
| `date_local`      | datetime | Date of AQI reading |
| `state_name`      | str      | Name of the U.S. state |
| `county_name`     | str      | Name of the U.S. county |
| `city_name`       | str      | U.S. city where monitoring occurred |
| `local_site_name` | str      | Identifier of the monitoring site (agency nomenclature) |
| `parameter_name`  | str      | Parameter measured (pollutant or other) |
| `units_of_measure`| str      | Unit of measurement for the data |
| `aqi_log`         | int      | Log-transformed AQI reading |

---

## 🎯 Learning Outcomes
By completing this lab, you will:
1. Explore the **distribution** of a dataset
2. Identify the **probability distribution type**
3. Calculate **z-scores**
4. Detect and interpret **outliers**
5. Relate statistical findings to **real-world environmental data**

---

## 📖 Instructions
1. **Open the Jupyter Notebook** provided in this repository.
2. Follow the guided steps to:
   - Import and explore the dataset
   - Visualize data distributions
   - Calculate z-scores
   - Detect and interpret outliers
3. Provide both **code** and **written responses** in the notebook.
4. **Download the dataset** within the notebook:
   - Navigate to `Lab Files` → `/home/jovyan/work`
   - Select `modified_c4_epa_air_quality.csv`
   - Click **Download**

---

## 🛠 Requirements
- Python 3.x
- Jupyter Notebook
- pandas
- numpy
- matplotlib / seaborn
- scipy

Install dependencies:
```bash
pip install pandas numpy matplotlib seaborn scipy
```

---

## 📊 Example Workflow, References & License
### Example Workflow:
1. **Load the Dataset**
   ```python
   import pandas as pd
   df = pd.read_csv("modified_c4_epa_air_quality.csv")
   ```
2. **Visualize Distributions**
   - Plot histogram of AQI values
   - Create a boxplot for outlier detection
3. **Check Statistical Properties**
   - Calculate skewness and kurtosis
   - Fit to probability distributions
4. **Calculate Z-Scores**
   - Identify values beyond ±3 as outliers
5. **Interpret Results**
   - Summarize how AQI varies by location and parameter

### References:
- [EPA Air Quality Data](https://www.epa.gov/outdoor-air-quality-data)  
- [AirNow](https://www.airnow.gov/)  
- [Z-Score Explanation - Wikipedia](https://en.wikipedia.org/wiki/Standard_score)  

### License:
This project is for **educational purposes only**. Dataset is adapted from publicly available EPA resources.

