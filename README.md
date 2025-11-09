# EDA-and-Data-Preprocessing-sql
SQL-based data cleaning and EDA of laptop specifications dataset to prepare data for machine learning price prediction.

# 💻 Laptop Price Data Cleaning & Exploratory Data Analysis (EDA) using MySQL

## 📋 Project Overview
This project focuses on **data cleaning and exploratory data analysis (EDA)** of an **uncleaned laptop dataset** using **MySQL**.  
The dataset was initially scraped from an e-commerce website and contained **missing values, inconsistent formatting, and duplicated records**.

The goal of this project was to:
- Clean and preprocess the dataset
- Handle missing and duplicate values
- Extract useful features for analysis
- Perform exploratory data analysis (EDA)
- Prepare the data for future use in a **Machine Learning model for Laptop Price Prediction**

---

## 🧩 About the Dataset

**Name:** Uncleaned Laptop Price Dataset  
**Total Records:** ~1,300 laptop listings  
**Source:** Scraped from an online e-commerce website  

### 📑 Columns (Before Cleaning)
`index`, `Company`, `TypeName`, `Inches`, `ScreenResolution`, `Cpu`, `Ram`, `Memory`, `Gpu`, `OpSys`, `Weight`, `Price`

The dataset contained a mix of **categorical** and **numerical** variables:
- **Categorical:** Company, TypeName, ScreenResolution, Cpu, Ram, Memory, Gpu, OpSys  
- **Numerical:** Inches, Weight, Price  

---

## 🧼 Data Cleaning Steps

The raw dataset was cleaned using **MySQL queries** to ensure it was ready for analysis.  

### ✅ Cleaning Tasks Performed
- Checked and removed **NULL** and **empty** rows  
- Detected and removed **duplicate rows**  
- Fixed inconsistent text formats (e.g., removed units like `'GB'`, `'kg'`, `'GHz'`, etc.)  
- Converted numeric columns stored as text into proper data types  
- Split combined columns into multiple features for better analysis  

### 🧠 Final Cleaned Columns
After cleaning and feature extraction, the final dataset includes:

`index`, `Company`, `TypeName`, `Inches`, `ScreenResolution`, `resolution_width`, `resolution_height`, `touchscreen`,  
`Cpu`, `cpu_brand`, `cpu_name`, `cpu_speed`, `Ram`, `Memory`, `memory_type`, `primary_storage`, `secondary_storage`,  
`Gpu`, `OpSys`, `Weight`, `Price`, `ppi`

---

## 📊 Exploratory Data Analysis (EDA)

EDA was performed to understand the structure, trends, and relationships within the dataset.

### 1️⃣ Initial Data Inspection
- Displayed `head`, `tail`, and random `sample` records
- Checked dataset shape and data types

### 2️⃣ Univariate Analysis
- **Numerical Columns:** count, min, max, mean, std, quartiles (Q1, Q2, Q3)
- **Categorical Columns:** value counts, unique categories
- Identified **missing values** and **outliers**
- Visualized distributions using histograms, boxplots, and pie charts

### 3️⃣ Bivariate Analysis
- **Categorical vs Categorical:** Crosstabs and bar charts  
- **Numerical vs Numerical:** Correlation matrix, scatter plots  
- **Categorical vs Numerical:** Mean price by category using bar charts  

### 4️⃣ Handling Missing Values
- Missing price values replaced with **mean of price**
- Other missing categorical values handled appropriately

### 5️⃣ Feature Engineering
- Created new features such as:
  - `ppi` (pixels per inch)
  - `resolution_width` and `resolution_height` from `ScreenResolution`
  - `cpu_brand`, `cpu_name`, `cpu_speed` extracted from `Cpu`
  - `primary_storage` and `secondary_storage` split from `Memory`
- Applied **One-Hot Encoding** to categorical features for ML-readiness

---

## 🛠️ Tools & Technologies Used
| Tool | Purpose |
|------|----------|
| **MySQL** | Data cleaning, preprocessing, and analysis |
| **Python (Planned)** | Future ML model development |
| **Data Visualization Tools** | For plots (bar charts, pie charts, box plots, scatter plots) |

---

## 🚀 Future Scope
- Build a **Machine Learning model** to predict laptop prices based on specifications.
- Use libraries like **Pandas**, **Scikit-learn**, and **Matplotlib/Seaborn** for model building and visualization.
- Automate the full cleaning and analysis pipeline using Python + SQL integration.

---

## 📚 Key Learnings
- Advanced SQL data cleaning techniques (`UPDATE`, `ALTER`, `DELETE`, `REPLACE`, `JOIN`, `REGEXP_REPLACE`)
- Handling NULLs and empty strings
- Identifying and removing duplicate rows
- Data preprocessing for model readiness
- Extracting structured information from unstructured text

---

### 🏁 Conclusion
This project demonstrates the end-to-end process of **cleaning raw data** and performing **data analysis** using SQL — a critical step before building any data-driven solution.  
It lays the groundwork for developing a **Laptop Price Prediction Model** in future iterations.
