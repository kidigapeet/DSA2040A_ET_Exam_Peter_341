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

## 📈 6️⃣ Visualizations & Insights

### **1️⃣ Total Sales & Profit by Region**
```python
trans_raw.groupby('Region')[['Sales','Profit']].sum().plot(kind='bar')
West and East regions lead in both sales and profit volumes.

2️⃣ Average Profit Margin by Category
python
Copy code
trans_raw.groupby('Category')['Profit_Margin'].mean().plot(kind='bar')
Technology products have the highest profitability margins.

3️⃣ Monthly Sales Trend
python
Copy code
trans_raw.groupby(trans_raw['Order Date'].dt.to_period('M'))['Sales'].sum().plot()
Sales show seasonal peaks during end-of-year months.

4️⃣ Distribution of Sales Tiers
python
Copy code
trans_raw['Sales_Tier'].value_counts().plot(kind='bar')
Most transactions fall under the Medium Sales Tier.

5️⃣ Average Shipping Duration by Region
python
Copy code
trans_raw.groupby('Region')['Shipping_Duration_days'].mean().plot(kind='barh')
Western regions have slightly faster shipping times on average.

🧰 7️⃣ How to Run the Project
Requirements
bash
Copy code
pip install pandas numpy matplotlib jupyter
Execution Steps
Open Jupyter Notebook.

Run etl_extract.ipynb → performs extraction and profiling.

Run etl_transform.ipynb → applies all transformations.

(Optional) Run visualization cells for graphical insights.

All notebooks are fully re-runnable and require no manual edits.

💡 8️⃣ Key Learnings
Understanding ETL workflows in a data warehousing context

Performing data profiling and quality validation

Applying cleaning, enrichment, and structural transformations

Building derived variables for analytical readiness

Implementing data visualization for insight communication

Managing structured GitHub repositories for professional submissions

🏁 9️⃣ Conclusion
This project successfully demonstrates an end-to-end ETL pipeline using Python and Pandas.
The transformed dataset is standardized, enriched, and analytics-ready — providing insights into sales performance, profitability, and logistics efficiency.

The final output serves as a robust foundation for future Load and OLAP phases in data warehousing.

🌐 🔟 Repository Information
🧭 GitHub Repo Name: DSA2040A_ET_Exam_Peter_341

📦 Contents:

Jupyter notebooks for Extract and Transform phases

Input & transformed CSV datasets

README documentation and visualization insights
