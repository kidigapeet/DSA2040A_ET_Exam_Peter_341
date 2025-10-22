# 🧠 Data Warehousing & Mining – ETL Project (DSA 2040A FS 2025)

> 🧩 *An end-to-end Python ETL pipeline transforming raw retail sales data into clean, analytics-ready insights.*

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Processing-green?logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange?logo=plotly)
![GitHub](https://img.shields.io/badge/Platform-GitHub-black?logo=github)
![License](https://img.shields.io/badge/License-Academic-lightgrey)

---

## 🗂️ Project Title
### **Sales Transactions ETL Pipeline Using Python & Pandas**  

A complete Extract–Transform workflow applied to real-world retail data from Kaggle’s *Superstore Sales* dataset.  
This project demonstrates data extraction, quality assessment, transformation, enrichment, and visualization in preparation for analytical use.

---

## 🧾 1️⃣ Project Overview
The objective of this project was to design and execute the **Extract** and **Transform** phases of an ETL pipeline.  
The workflow loads, inspects, cleans, standardizes, and enriches a dataset containing retail sales transactions, preparing it for future analysis or data warehouse integration.

### ✅ Key Goals:
- Load and inspect large-scale retail data  
- Detect and document data quality issues  
- Apply diverse transformations across multiple categories  
- Generate clean, structured, and analytics-ready datasets  

---

## 💾 2️⃣ Dataset Description

**📍 Source:** [Superstore Sales Dataset – Kaggle](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)  
**📊 Size:** ~10,000 rows × 21 columns  
**📂 Format:** CSV (`Raw_data.csv`)

**Main Features:**
| Category | Example Columns | Description |
|-----------|-----------------|--------------|
| **Order Info** | `Order ID`, `Order Date`, `Ship Date`, `Ship Mode` | Purchase and shipping details |
| **Customer Info** | `Customer ID`, `Customer Name`, `Segment`, `Region` | Customer demographics |
| **Product Info** | `Product ID`, `Category`, `Sub-Category`, `Product Name` | Product classification |
| **Sales Metrics** | `Sales`, `Quantity`, `Discount`, `Profit` | Transactional performance metrics |

---

## ⚙️ 3️⃣ Tools & Technologies

| Tool | Purpose |
|------|----------|
| 🐍 **Python (Pandas, NumPy)** | Data manipulation and transformation |
| 📊 **Matplotlib** | Data visualization and insights |
| 🧮 **Jupyter Notebook** | Interactive documentation and reproducibility |
| 💻 **Git & GitHub** | Version control and public submission |

---

## 🧭 4️⃣ Project Folder Structure

ET_Exam_Peter_341/
├── data/
│ ├── raw_data.csv
│ ├── incremental_data.csv
│ ├── validated_full.csv
├── transformed/
│ ├── transformed_full.csv
│ ├── transformed_incremental.csv
├── etl_extract.ipynb
├── etl_transform.ipynb
├── README.md
└── .gitignore

yaml
Copy code

---

## 🔍 5️⃣ ETL Workflow Summary

### **A. 🧮 Extract Phase (`etl_extract.ipynb`)**
**Steps Performed:**
1. Loaded `raw_data.csv` and `incremental_data.csv` using Pandas.  
2. Conducted exploratory profiling using `.head()`, `.info()`, and `.describe()`.  
3. Checked for:
   - ✅ Missing values → None found  
   - ✅ Duplicates → None found  
   - ✅ Invalid numerical values → None found  
4. Verified proper column data types (dates, numbers, text).  
5. Merged datasets and saved validated copy as `validated_full.csv`.

**Result:**  
> Dataset was clean and consistent — ready for transformation.

---

### **B. 🔧 Transform Phase (`etl_transform.ipynb`)**

Applied **7 major transformations** across multiple categories:

| # | Transformation | Category | Description |
|---|----------------|-----------|--------------|
| 1️⃣ | Convert `Order Date` & `Ship Date` → datetime | Standardization | Enables date operations |
| 2️⃣ | Create `Shipping_Duration_days` | Enrichment | Days between order and delivery |
| 3️⃣ | Compute `Profit_Margin = Profit / Sales` | Enrichment | Adds business profitability metric |
| 4️⃣ | Convert `Postal Code` → string | Structural | Preserves leading zeros |
| 5️⃣ | Clean text fields (trim spaces) | Cleaning | Improves consistency |
| 6️⃣ | Create `Sales_Tier` (Low/Medium/High) | Categorization | Sales segmentation using quantiles |
| 7️⃣ | Derive `Revenue_per_Item = Sales / Quantity` | Enrichment | Per-item revenue insight |

**Files Generated:**
- 📄 `transformed_full.csv` — Transformed main dataset  
- 📄 `transformed_incremental.csv` — Transformed incremental dataset  

---

📊 6. Sample Visualizations & Insights

To gain deeper insights, several simple visualizations were created:

1️⃣ Sales and Profit by Region

Shows regional revenue distribution. The West and East regions generated the most sales.

2️⃣ Average Profit Margin by Category

Technology products recorded the highest average profit margins.

3️⃣ Monthly Sales Trend

Displays seasonal fluctuations, with spikes in end-of-year sales periods.

4️⃣ Distribution of Sales Tiers

Majority of transactions fall within the Medium sales tier.

5️⃣ Average Shipping Duration by Region

Reveals differences in delivery times across regions — useful for supply chain analysis.

⚙️ 7. How to Run the Project
Requirements

Install dependencies:

pip install pandas numpy matplotlib jupyter

Steps

Open Jupyter Notebook.

Run etl_extract.ipynb → This loads, validates, and profiles the data.

Run etl_transform.ipynb → This applies all transformations and saves new CSVs.

(Optional) Run the visualization cells to generate insights.

All notebooks are fully re-runnable and do not require manual intervention.

🧾 8. Key Learnings and Skills Demonstrated

Understanding of ETL pipeline architecture (Extract & Transform phases).

Data profiling using Pandas (info(), describe(), and missing value checks).

Implementing data cleaning and enrichment transformations.

Creating derived variables for business analysis.

Using Python visualization libraries for insight generation.

Version control and project organization using GitHub.

🏁 9. Conclusion

This project successfully demonstrates the end-to-end data extraction and transformation process using Python and Pandas.
The final transformed dataset is well-structured, consistent, and enriched with additional analytical features such as shipping duration, profit margin, and sales tier.

These transformations set the foundation for the “Load” phase, where the cleaned data could be integrated into a warehouse for advanced reporting and business intelligence.

📎 10. Repository Information

GitHub Repo Name:
DSA2040A_ET_Exam_Peter_341

Contents:

Jupyter Notebooks for extraction and transformation

Input and output CSV files

Visualizations and documentation (this README)
Jupyter notebooks for Extract and Transform phases

Input & transformed CSV datasets

README documentation and visualization insights
