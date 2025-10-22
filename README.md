📘 1. Project Overview

This project demonstrates the Extract and Transform phases of a complete ETL (Extract, Transform, Load) pipeline, applied to a real-world retail sales dataset.

The objective was to:

Extract and validate data from raw sources.

Identify and handle data quality issues.

Apply a variety of transformations (cleaning, standardization, enrichment, structural, and categorization).

Prepare the dataset for future analytical and data warehousing processes.

The entire workflow was implemented using Python, Pandas, and Jupyter Notebook, with the outputs organized into structured folders for reproducibility.

💾 2. Data Source

Dataset Used: Superstore Sales Dataset – Kaggle

Description:
The Superstore dataset contains detailed sales transactions from a US-based retail store.
It includes product, customer, shipping, and financial data across multiple regions and categories.

Size: ~10,000 rows × 21 columns
Format: CSV (Raw_data.csv)

Key Columns:

Order Information: Order ID, Order Date, Ship Date, Ship Mode

Customer Information: Customer ID, Customer Name, Segment, Region, Country

Product Details: Product ID, Category, Sub-Category, Product Name

Sales Metrics: Sales, Quantity, Discount, Profit

🧰 3. Tools and Technologies
Tool	Purpose
Python (Pandas, NumPy)	Data manipulation and transformations
Matplotlib	Data visualization
Jupyter Notebook	Interactive coding and documentation
Git & GitHub	Version control and project submission
🗂️ 4. Project Folder Structure
ET_Exam_Peter_341/
├── data/
│   ├── raw_data.csv
│   ├── incremental_data.csv
│   ├── validated_full.csv
├── transformed/
│   ├── transformed_full.csv
│   ├── transformed_incremental.csv
├── etl_extract.ipynb
├── etl_transform.ipynb
├── README.md
└── .gitignore

🔍 5. ETL Process Summary
A. Extract Phase (etl_extract.ipynb)

Performed the following steps:

Loaded both the main dataset (raw_data.csv) and incremental dataset (incremental_data.csv) using Pandas.

Displayed .head(), .info(), and .describe() for initial inspection.

Checked for:

Missing values → None found

Duplicates → None found

Invalid or negative numerical values → None found

Verified column data types (dates, numeric, and categorical).

Merged the raw and incremental datasets for validation.

Saved a clean version as validated_full.csv.

Key Finding:
The dataset was well-structured and clean, requiring minimal corrections. The only standardization needed was converting Ship Date to a proper datetime format.

B. Transform Phase (etl_transform.ipynb)

Applied 7 major transformations (covering ≥5 categories):

#	Transformation	Type	Description
1	Convert Order Date & Ship Date to datetime	Standardization	Enables date arithmetic
2	Create Shipping_Duration_days	Enrichment	Calculates delivery time in days
3	Calculate Profit_Margin = Profit / Sales	Enrichment	Adds business profitability insight
4	Convert Postal Code to string	Structural	Preserves leading zeros
5	Trim whitespace in text fields	Cleaning	Fixes inconsistent text formatting
6	Categorize Sales_Tier (Low, Medium, High)	Categorization	Segments transactions by sales level
7	Derive Revenue_per_Item = Sales / Quantity	Enrichment	Provides per-unit sales insight

Results Saved As:

transformed_full.csv – complete dataset after transformations

transformed_incremental.csv – transformed subset of new incremental data

Outcome:
The transformed dataset is standardized, enriched with new features, and fully ready for analytical modeling or loading into a data warehouse.

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
