# UFC Dataset Exploration & Analysis

## 📌 Project Overview
This project is an exploratory data analysis (EDA) of a UFC dataset, chosen out of my passion for MMA and my deep understanding of fight statistics. By leveraging my knowledge of significant strikes, fight odds, knockouts (KOs), reach advantages, and other critical fight metrics, I aim to uncover interesting insights and patterns from historical UFC fights.

## 📂 Data Extraction
- The dataset is stored in a CSV file and will be loaded into a Pandas DataFrame.
- Initial data inspection will be performed to understand structure, missing values, and data types.

```python
# Load necessary libraries
import pandas as pd
import numpy as np

# Load the dataset
file_path = "path_to_your_ufc_data.csv"
df = pd.read_csv(file_path)

# Display basic information about the dataset
df.info()
df.head()
```

## 📊 Exploratory Data Analysis (EDA)
- Cleaning the dataset (handling missing values, data inconsistencies, etc.).
- Analyzing key statistics such as fighter win rates, striking accuracy, submission rates, and reach advantages.
- Identifying trends related to fight outcomes and betting odds.

```python
# Perform data cleaning and transformation
# (Fill in later with data cleaning and wrangling code)
```

## 🔄 Data Transformations
- Creating new calculated columns for deeper insights (e.g., strike differential, control time percentage, etc.).
- Aggregating fight stats per fighter to analyze long-term trends.

```python
# Apply transformations
# (Fill in later with DataFrame transformations)
```

## 📈 Visualization & Power BI Integration
- Exporting transformed data to be uploaded to Power BI.
- Creating interactive visualizations in Power BI to effectively present findings.

```python
# Save processed data for Power BI analysis
df.to_csv("cleaned_ufc_data.csv", index=False)
```

## 🚀 Goals & Outcomes
- Showcase proficiency in **data engineering with DataFrames**, **EDA for analysis**, and **data manipulation skills**.
- Display the results in an easy-to-understand format through **Power BI visualizations**.
- Provide a strong portfolio piece for interviews, demonstrating expertise in working with real-world sports datasets.

---
Stay tuned as I continue to update this project with insights and visualizations! 🏆🥊
