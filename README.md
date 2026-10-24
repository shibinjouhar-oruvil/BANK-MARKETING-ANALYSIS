# BANK-MARKETING-ANALYSIS
Bank Marketing Analysis Dashboard | Power BI
An interactive Power BI dashboard for analyzing a bank's direct-marketing campaign and understanding which customer and campaign characteristics are associated with term-deposit subscriptions.
📌 Project Overview
Banks use direct-marketing campaigns, such as phone calls, to contact customers and promote term deposits. This project explores the Bank Additional Full dataset to summarize campaign outcomes, compare subscription patterns, and support data-informed marketing decisions.

The report is organized into four pages:
- Intro — project introduction
- Overview — high-level campaign overview
- Subscription — subscription-related analysis
- Loan Data — loan-related customer analysis
🎯 Objectives
- Measure the overall campaign and term-deposit subscription outcomes.
- Explore customer characteristics such as age, job, education, and marital status.
- Compare outcomes by contact method, campaign month, and previous campaign results.
- Examine whether housing-loan and personal-loan status are associated with subscription outcomes.
- Present findings in an interactive dashboard that can be filtered for deeper analysis.
📂 Dataset
- Dataset: Bank Additional Full / Bank Marketing
- Source: Kaggle — Bank Additional Full CSV
- Target column: y
  - yes — customer subscribed to a term deposit
  - no — customer did not subscribe to a term deposit
The dataset includes customer details, contact and campaign information, previous campaign outcomes, and economic indicators. Examples of fields include age, job, marital, education, housing, loan, contact, month, campaign, poutcome, and y.
Note: Exact row counts, KPI values, and percentages are not listed here because they should be taken directly from the final dataset/report and may change after data preparation or filtering.

🧹 Data Preparation
The preparation workflow for this project includes:
1. Load the CSV dataset into Power BI Desktop.
2. Review column names, data types, and the structure of the data.
3. Check for blank/null values and investigate values marked as unknown.
4. Confirm that categorical columns and numeric columns use suitable data types.
5. Review duplicate records and data-quality issues before deciding whether any action is needed.
6. Create calculated columns or groups where useful, such as Age Group and Duration Group.
7. Validate the subscription outcome column (y) before building measures and visuals.
Data-quality note: In this dataset, unknown can be a category indicating unavailable information; it should not automatically be treated as a blank or deleted without checking its meaning.
📊 Dashboard & Analysis
The report includes pages for overview, subscription, and loan analysis. Suitable analyses for this dataset include:
- Campaign overview: total customers contacted, subscribed customers, and subscription rate.
- Customer profile: subscription outcomes by age group, job, education, and marital status.
- Contact analysis: comparison by contact method and campaign month.
- Campaign performance: comparison by number of contacts and previous campaign outcome.
- Loan analysis: compare subscription rates for customers with and without housing or personal loans.
- Interactive filtering: use available slicers and filters to explore customer segments.
The dashboard is intended to help identify patterns in the data. These patterns show associations and should not be interpreted as proof that a single factor causes a customer to subscribe.
🧮 Example DAX Measures
Adjust table and column names if they differ in your Power BI model.
Total Customers =
COUNTROWS('bank-additional-full')
Subscribed Customers =
CALCULATE(
    COUNTROWS('bank-additional-full'),
    'bank-additional-full'[y] = "yes"
)
Subscription Rate (%) =
DIVIDE(
    [Subscribed Customers],
    [Total Customers],
    0
)
Format Subscription Rate (%) as a percentage in Power BI. If your model uses a different table name, replace 'bank-additional-full' with the exact table name shown in the Fields pane.
🔍 Key Questions
This report can be used to explore questions such as:
1. What proportion of contacted customers subscribed to a term deposit?
2. Which customer groups show higher or lower subscription rates?
3. How do contact method and campaign month relate to subscription outcomes?
4. Does the previous campaign outcome appear related to the current outcome?
5. How do housing-loan and personal-loan groups compare?
Add the final findings and verified KPI values from your report here after checking the dashboard.
🛠️ Tools Used
- Microsoft Power BI Desktop — data modeling, DAX measures, visuals, and dashboard design
- Power Query — data inspection and preparation
- DAX — measures and calculated analysis
- CSV / Kaggle — source data
🚀 How to Open the Project
1. Download or clone this repository.
2. Open the .pbix file using Microsoft Power BI Desktop.
3. If prompted, update the CSV file path or reconnect to the dataset.
4. Refresh the data if required.
5. Explore the report pages and use the slicers/filters to inspect different segments.
📁 Suggested Repository Structure
bank-marketing-analysis/
├── README.md
├── bank-marketing-analysis.pbix
└── data/
    └── bank-additional-full.csv   # Include only if you have permission to redistribute it
💡 Conclusion
This Power BI project turns bank campaign data into an interactive report for exploring term-deposit subscription patterns across customer, contact, campaign, and loan-related attributes. It demonstrates data preparation, DAX measure creation, visual analytics, and dashboard development.
