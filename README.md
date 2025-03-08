# UFC Fight Data Analysis & Visualization

## Overview
As a passionate UFC fan, I’ve always been fascinated by the statistics that define a fight—significant strikes, fight odds, knockouts (KOs), reach advantage, and more. This project is a deep dive into UFC fight data, where I leverage my analytical skills to extract insights using **Python, Pandas, PySpark, and Power BI**.

---

## Dataset Information
- The dataset contains historical fight data, including fighter stats, fight outcomes, and betting odds.
- Data points include:
  - **Significant strikes**, **Takedowns**, **Submission attempts**
  - **Reach advantage**, **Weight class**, **Fighter records**
  - **Betting odds**, **Fight outcome** (Win/Loss/Draw)
- Data is sourced from publicly available UFC datasets.

---

## Data Processing Steps
### **Data Extraction**
```python
# Load CSV file into a Pandas DataFrame
import pandas as pd

df = pd.read_csv('ufc_fight_data.csv')
df.head()
```

### **Data Cleaning & Transformation**
```python
# Handle missing values
# Convert data types if necessary

# Example: Fill missing reach values with median

df['reach'].fillna(df['reach'].median(), inplace=True)
```

### **Exploratory Data Analysis (EDA)**
```python
# Basic Statistics
print(df.describe())

# Distribution of Knockouts (KOs)
import seaborn as sns
import matplotlib.pyplot as plt

sns.histplot(df['knockouts'], bins=10, kde=True)
plt.title("Distribution of Knockouts (KOs)")
plt.show()
```

### ** Data Transformation Using PySpark**
```python
from pyspark.sql import SparkSession

spark = SparkSession.builder.appName("UFC_EDA").getOrCreate()
spark_df = spark.createDataFrame(df)

# Example: Convert weight class to lowercase
from pyspark.sql.functions import lower

spark_df = spark_df.withColumn("weight_class", lower(spark_df.weight_class))
spark_df.show(5)
```

### ** Save Processed Data for Power BI**
```python
# Save cleaned dataset for Power BI visualization
df.to_csv("cleaned_ufc_data.csv", index=False)
```

---

## Power BI Visualizations
Once the data is cleaned and processed, it will be imported into **Power BI** for further analysis and visualization.

### **Key Visuals & Dashboards:**
- **Fighter Performance Dashboard**
  - Win/loss ratio across weight classes
  - Fighter performance trends (significant strikes, takedowns, submissions)
  - Impact of reach advantage on fight outcomes
- **Betting Odds Analysis**
  - Underdog vs. favorite win rates
  - Correlation between odds and fight outcomes
- **KO & TKO Analysis**
  - Knockout rate by weight class
  - Fighters with the highest KO percentages

---

### **Enhancing Power BI Integration**
What I aim to do next to further flesh out the project:
- **Create a UFC Power BI Dashboard** showcasing key fight statistics.
- **Use DAX formulas** to calculate fighter win rates and performance metrics.
- **Implement interactive filters** (e.g., by fighter, weight class, year).
- **Deploy dashboard to Power BI Service** to demonstrate cloud reporting capabilities.



