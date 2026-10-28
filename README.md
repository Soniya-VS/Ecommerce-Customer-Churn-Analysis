# E-Commerce Customer Churn Patterns and Customer Retention Analysis

**Exploring customer churn patterns to support data-driven insights into customer behavior, business performance, and retention strategies.**

## Project Overview

Customer retention is important for the long-term growth of e-commerce businesses. When customers stop purchasing products or discontinue their relationship with a business, it can affect revenue, customer lifetime value, and business performance.

This project explores e-commerce customer data to understand **patterns associated with customer churn and retention**.

Using the E-Commerce Customer Churn Dataset, the project aims to identify patterns across customer segments, purchasing behavior, satisfaction levels, marketing engagement, and customer retention activities.

The goal is to transform customer data into meaningful analytical insights that can support further investigation into customer behavior and retention opportunities.

## Business Problem

Customer churn can affect sales, revenue, and long-term business growth. Understanding which customer groups and behaviors are associated with churn may help businesses identify areas that deserve closer attention.

This project addresses the following question:

**What patterns in customer characteristics, purchasing behavior, satisfaction, and engagement are associated with customer churn in e-commerce?**

The analysis will explore these relationships while recognizing that observed associations do not necessarily establish the causes of customer churn or prove the effectiveness of retention strategies.

## Project Objectives

* Examine the distribution of churned and non-churned customers.
* Explore churn patterns across different customer segments.
* Investigate relationships between purchasing behavior and churn.
* Examine how customer satisfaction and support interactions relate to churn.
* Analyze customer engagement and marketing-related patterns.
* Explore customer value and retention-related indicators.
* Develop clear visualizations to communicate analytical findings.
* Identify patterns that may support data-driven customer retention decisions.

## Dataset Information

| Attribute           | Details                                                |
| ------------------- | ------------------------------------------------------ |
| Dataset             | E-Commerce Customer Churn Dataset                      |
| Source              | Kaggle                                                 |
| File format         | CSV                                                    |
| Number of records   | 50,000                                                 |
| Number of columns   | 48                                                     |
| Unit of observation | Churn tracking record, subject to dataset verification |
| Domain              | E-Commerce Analytics                                   |

**Dataset source:** [Kaggle – E-Commerce Customer Churn Dataset](https://www.kaggle.com/datasets/datascikhan/e-commerce-customer-churn-2026)

The dataset contains 50,000 records and 48 columns related to customer information, churn status, purchasing behavior, satisfaction, marketing engagement, customer value, and retention activities.

### Key Fields

Some of the fields relevant to this project include:

* `customer_id` – Customer identifier.
* `customer_segment` – Business classification of the customer.
* `is_churned` – Indicator showing whether a customer has churned.
* `churn_flag` – Numeric representation of churn status.
* `subscription_type` – Customer subscription or membership type.
* `total_spend_usd` – Total customer spending.
* `avg_order_value_usd` – Average order value.
* `num_purchases` – Number of purchases.
* `satisfaction_score` – Numerical customer satisfaction rating.
* `support_tickets` – Number of customer support tickets.
* `days_since_last_purchase` – Days since the last purchase.
* `customer_lifetime_value_usd` – Customer lifetime value estimate.
* `engagement_level` – Customer engagement classification.
* `marketing_emails_opened` – Number of marketing emails opened.
* `customer_health_score` – Composite customer health score.
* `churn_risk_category` – Customer churn risk classification.
* `retention_probability` – Estimated likelihood of customer retention.

The actual definitions, data types, and suitability of these variables will be examined before detailed analysis. Precomputed predictions and risk scores will be reviewed carefully to understand their meaning and limitations.

## Tools and Technologies

* **Python** – Data analysis.
* **Pandas** – Dataset loading, inspection, and tabular analysis.
* **NumPy** – Numerical operations.
* **Matplotlib** – Data visualization.
* **Jupyter Notebook** – Interactive analysis and documentation.
* **GitHub** – Version control and project presentation.

## Project Workflow

The project will follow a structured data analysis workflow:

1. **Understand the data:** Load the dataset and inspect its dimensions, column names, data types, and sample records.
2. **Assess data quality:** Examine missing values, duplicate records, inconsistent values, and potential data quality issues.
3. **Prepare the data:** Investigate missing values and prepare relevant variables for analysis.
4. **Explore churn patterns:** Examine the distribution of churn status and compare customer groups.
5. **Analyze customer behavior:** Explore relationships involving purchasing activity, satisfaction, support interactions, and engagement.
6. **Visualize insights:** Create suitable charts and summaries to communicate the findings.
7. **Interpret findings:** Discuss the observed patterns, their business relevance, and the limitations of the analysis.

## Planned Analysis

The main areas of investigation are:

| Analysis Area           | Key Questions                                                                                            |
| ----------------------- | -------------------------------------------------------------------------------------------------------- |
| Customer churn patterns | How are customers distributed across churn statuses?                                                     |
| Customer segmentation   | How do churn patterns differ across customer segments and subscription types?                            |
| Purchasing behavior     | How are purchase frequency, spending, and order value associated with churn?                             |
| Customer satisfaction   | How do satisfaction scores and feedback relate to churn patterns?                                        |
| Customer support        | What patterns appear across support tickets, interactions, and support channels?                         |
| Marketing engagement    | How do email engagement, marketing conversions, and social media engagement vary across customer groups? |
| Customer value          | How do customer lifetime value and customer value categories relate to churn?                            |
| Retention indicators    | What patterns appear in retention-related variables and customer health indicators?                      |
| Data visualization      | How can the findings be communicated clearly to support business decisions?                              |

## Initial Dataset Inspection

During the initial inspection, the dataset was confirmed to contain **50,000 records and 48 columns**, representing 2,400,000 data elements.

The following missing values were identified:

| Column                    | Missing Values |
| ------------------------- | -------------: |
| `subscription_type`       |         13,142 |
| `prevention_method`       |         36,874 |
| `social_media_engagement` |         15,004 |
| **Total**                 |     **65,020** |

No duplicate rows were detected during the initial inspection.

The missing values represent approximately 1.35% of all data elements. However, missingness is concentrated in three columns. Their possible causes and appropriate handling methods will be investigated during data preparation rather than automatically replacing the missing values.

## Expected Business Value

The project aims to demonstrate how e-commerce customer data can be used to:

* Identify customer groups with different churn patterns.
* Understand relationships between purchasing behavior and customer churn.
* Examine how satisfaction and engagement vary across customer groups.
* Explore customer value and retention-related indicators.
* Communicate analytical findings through clear visualizations.
* Support evidence-based discussions about customer retention opportunities.

These are intended applications of the analysis, not claims that the dataset alone can establish the causes of churn or demonstrate that a particular retention strategy is effective.

## Repository Structure

The repository will be organized as follows:

```text
Ecommerce-Customer-Churn-Analysis/
│
├── data/
│   └── dataset.csv
│
├── Ecommerce_Customer_Churn_Phase1.ipynb
│
├── Ecommerce_Customer_Churn_SRS.docx
│
└── README.md
```

* `data/dataset.csv` – Dataset used for the project.
* `Ecommerce_Customer_Churn_Phase1.ipynb` – Project overview, business problem, objectives, dataset inspection, and planned analysis.
* `Ecommerce_Customer_Churn_SRS.docx` – Software Requirements Specification documenting project requirements.
* `README.md` – Project overview and documentation.

## Scope and Limitations

* The analysis depends on the accuracy and completeness of the available dataset.
* Missing values may affect particular analyses and must be investigated before treatment.
* The meaning and consistency of churn-related variables must be verified.
* Multiple records may relate to the same customer; this must be checked before interpreting record-level results as customer-level results.
* Precomputed churn predictions and risk scores may depend on methods or assumptions that are not documented in the dataset.
* Observed associations do not establish causation.
* The effectiveness of retention strategies cannot be established solely from descriptive patterns without an appropriate evaluation design.
* Findings may not generalize to all e-commerce businesses.

## Project Status

**Phase 1 – Project Proposal and Initial Dataset Inspection**

The project scope, business problem, objectives, dataset requirements, and planned analysis have been defined. The dataset has been loaded and its initial structure inspected.

The initial inspection identified 50,000 records, 48 columns, 65,020 missing values across three columns, and no duplicate rows.

Further investigation of data quality, missing values, variable definitions, and churn patterns will be carried out in subsequent phases.
