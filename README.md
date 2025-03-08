# UFC Fight Data Analysis & Visualization

## Overview
As a passionate UFC fan, I’ve always been fascinated by the statistics that define a fight—significant strikes, fight odds, knockouts (KOs), reach advantage, and more. This project is a deep dive into UFC fight data, where I leverage my analytical skills to extract insights using **Python, Pandas, PySpark, and Power BI**.

Through this project, I aim to showcase my ability to:
- Extract and clean real-world fight data from a CSV file
- Conduct **Exploratory Data Analysis (EDA)** and transformations using **Jupyter Notebooks**
- Manipulate data using **Pandas** and **PySpark DataFrames**
- Upload and visualize the cleaned dataset in **Power BI** for impactful insights

This project will be hosted on GitHub to **demonstrate my Data Engineering and Data Analysis skills to potential employers**.

---

## 📂 Dataset Information
- The dataset contains historical fight data, including fighter stats, fight outcomes, and betting odds.
- Data points include:
  - **Significant strikes**, **Takedowns**, **Submission attempts**
  - **Reach advantage**, **Weight class**, **Fighter records**
  - **Betting odds**, **Fight outcome** (Win/Loss/Draw)
- Data is sourced from publicly available UFC datasets.

---

## 🔧 Tools & Technologies Used
- **Python** (for data extraction & transformation)
- **Jupyter Notebooks** (for EDA and data visualization)
- **Pandas & PySpark** (for DataFrame operations and transformations)
- **Power BI** (for interactive visualizations and dashboards)
- **SQL** (for query optimization and analysis within Power BI)

---

## 📊 Data Processing Steps
### **1️⃣ Data Extraction**
```python
# Load CSV file into a Pandas DataFrame
import pandas as pd

df = pd.read_csv('ufc_fight_data.csv')
df.head()
```

### **2️⃣ Data Cleaning & Transformation**
```python
# Handle missing values
# Convert data types if necessary

# Example: Fill missing reach values with median

df['reach'].fillna(df['reach'].median(), inplace=True)
```

### **3️⃣ Exploratory Data Analysis (EDA)**
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

### **4️⃣ Data Transformation Using PySpark**
```python
from pyspark.sql import SparkSession

spark = SparkSession.builder.appName("UFC_EDA").getOrCreate()
spark_df = spark.createDataFrame(df)

# Example: Convert weight class to lowercase
from pyspark.sql.functions import lower

spark_df = spark_df.withColumn("weight_class", lower(spark_df.weight_class))
spark_df.show(5)
```

### **5️⃣ Save Processed Data for Power BI**
```python
# Save cleaned dataset for Power BI visualization
df.to_csv("cleaned_ufc_data.csv", index=False)
```

---

## 📈 Power BI Visualizations
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

## 🚀 Next Steps: Expanding the Project
To further enhance this project and make it **more appealing for Data Engineering (DE) and Data Analyst (DA) roles**, my next steps include:

### 🔹 **Enhancing Power BI Integration**
✅ **Create a UFC Power BI Dashboard** showcasing key fight statistics.
✅ **Use DAX formulas** to calculate fighter win rates and performance metrics.
✅ **Implement interactive filters** (e.g., by fighter, weight class, year).
✅ **Deploy dashboard to Power BI Service** to demonstrate cloud reporting capabilities.

### 🔹 **Adding More Data Engineering Features**
✅ **Convert CSV to Parquet format** for improved performance.
✅ **Automate data ingestion pipelines** using Python scripts.
✅ **Optimize queries** inside Power BI for better performance (avoid subqueries when possible).
✅ **Set up scheduled data refresh in Power BI Service** to automate updates.

---

## 📌 Why This Project Matters
- This project **combines my passion for UFC** with **data analytics and engineering**.
- It demonstrates my ability to **handle real-world data**, clean it, analyze it, and visualize insights.
- It highlights my proficiency in **Python, SQL, PySpark, and Power BI**—all critical skills for **Data Engineer and Data Analyst roles**.

### 🎯 **Goal**: Build a UFC Analytics Dashboard that can be used by analysts, fight promoters, and sports bettors.

---

## 📝 Author
👤 **[Your Name]**  
💼 Aspiring Data Engineer | Data Analyst  
🔗 [LinkedIn Profile](#)  
📂 [GitHub Repository](#)
