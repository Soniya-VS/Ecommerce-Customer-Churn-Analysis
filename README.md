# E-Commerce Customer Churn Patterns and Customer Retention Analysis

Exploring customer churn patterns to understand customer behaviour, purchasing activity, satisfaction, and retention-related indicators in e-commerce.

## Project Overview

Customer retention is important for the long-term growth of e-commerce businesses. When customers stop purchasing products or discontinue their relationship with a business, it can affect revenue, customer lifetime value, and overall business performance.

This project analyses an e-commerce customer churn dataset to explore patterns associated with customer churn and retention.

The analysis focuses on customer segments, purchasing behaviour, satisfaction levels, marketing engagement, customer value, and retention-related indicators.

The objective is to transform customer data into meaningful insights that can support data-driven discussions about customer behaviour and retention opportunities.

## Business Problem

Customer churn can affect sales, revenue, and long-term business growth. Understanding which customer characteristics and behaviours are associated with churn may help businesses identify areas that deserve closer attention.

This project addresses the following question:

**What patterns in customer characteristics, purchasing behaviour, satisfaction, and engagement are associated with customer churn in e-commerce?**

The analysis explores these relationships while recognizing that observed associations do not necessarily establish the causes of customer churn or prove the effectiveness of retention strategies.

## Project Objectives

* Examine the distribution of churned and non-churned customers.
* Explore churn patterns across different customer segments.
* Investigate relationships between purchasing behaviour and churn.
* Examine how customer satisfaction and support interactions relate to churn.
* Analyse customer engagement and marketing-related patterns.
* Explore customer value and retention-related indicators.
* Develop visualizations to communicate analytical findings.
* Identify patterns that may support data-driven customer retention decisions.

## Dataset Information

| Attribute        | Details                           |
| ---------------- | --------------------------------- |
| Dataset          | E-Commerce Customer Churn Dataset |
| Source           | Kaggle                            |
| File format      | CSV                               |
| Original records | 50,000                            |
| Original columns | 48                                |
| Domain           | E-Commerce Analytics              |

**Dataset source:** [Kaggle – E-Commerce Customer Churn Dataset](https://www.kaggle.com/datasets/datascikhan/e-commerce-customer-churn-2026)

The dataset contains information related to customer identifiers, churn status, purchasing behaviour, satisfaction, marketing engagement, customer value, and retention activities.

### Important Variables

Some of the important variables used in the project include:

* `customer_id` – Customer identifier.
* `churn_id` – Churn tracking record identifier.
* `customer_segment` – Customer classification.
* `is_churned` – Indicator showing whether a customer has churned.
* `subscription_type` – Customer subscription type.
* `total_spend_usd` – Total customer spending.
* `avg_order_value_usd` – Average order value.
* `num_purchases` – Number of purchases.
* `satisfaction_score` – Numerical customer satisfaction rating.
* `support_tickets` – Number of customer support tickets.
* `days_since_last_purchase` – Days since the last purchase.
* `customer_lifetime_value_usd` – Customer lifetime value estimate.
* `engagement_level` – Customer engagement classification.
* `marketing_emails_opened` – Number of marketing emails opened.
* `customer_health_score` – Customer health score.
* `churn_risk_category` – Customer churn risk classification.
* `retention_probability` – Estimated likelihood of customer retention.

Precomputed predictions and risk-related variables will be examined carefully before being considered in further analysis.

## Tools and Technologies

* Python – Data analysis and preprocessing.
* Pandas – Data manipulation and analysis.
* NumPy – Numerical operations.
* Matplotlib – Data visualization.
* Jupyter Notebook – Interactive analysis.
* GitHub – Project documentation and version control.

## Project Workflow

The project follows a structured data analysis workflow.

1. Project understanding and problem definition.
2. Initial dataset inspection.
3. Data quality assessment.
4. Data preprocessing and cleaning.
5. Exploratory Data Analysis (EDA).
6. Customer churn pattern analysis.
7. Data visualization.
8. Interpretation of findings and business insights.

## Phase 1 – Project Proposal and Initial Dataset Inspection

Phase 1 focused on defining the project scope, understanding the business problem, identifying project objectives, and inspecting the original dataset.

Initial inspection findings:

| Description          |    Result |
| -------------------- | --------: |
| Total records        |    50,000 |
| Total columns        |        48 |
| Total data elements  | 2,400,000 |
| Duplicate rows       |         0 |
| Total missing values |    65,020 |

Missing values were identified in three columns:

| Column                    | Missing Values |
| ------------------------- | -------------: |
| `subscription_type`       |         13,142 |
| `prevention_method`       |         36,874 |
| `social_media_engagement` |         15,004 |
| **Total**                 |     **65,020** |

These missing values were investigated during the preprocessing phase rather than being automatically replaced.

## Phase 2 – Data Preprocessing and Cleaning

Phase 2 focused on examining and improving the quality of the dataset before performing exploratory analysis.

The following activities were completed:

### 1. Missing Value Investigation and Treatment

* Investigated missing values in `subscription_type`, `prevention_method`, and `social_media_engagement`.
* Examined category distributions and relationships with churn-related variables.
* Replaced missing values in these three categorical columns with `Unknown` because their actual meanings could not be established from the available data.
* Converted `Not Applicable` entries in `churn_date` into `NaT`.
* Verified that the missing churn dates corresponded to non-churned records.

The remaining missing values in `churn_date` were retained because a churn date is not applicable to customers who have not churned.

### 2. Duplicate and Identifier Checks

* Identified 50,000 total records.
* Found 31,644 unique customer IDs.
* Identified 18,356 records associated with repeated customer IDs.
* Verified that all 50,000 `churn_id` values were unique.
* Confirmed that no exact duplicate rows were present.

Repeated customer IDs were retained because they represented multiple records rather than exact duplicate observations.

### 3. Data Consistency Checks

Checked numerical and categorical variables for unusual or inconsistent values.

The following checks were performed:

* Negative values in numerical columns.
* Marketing emails opened exceeding emails sent.
* Marketing emails clicked exceeding emails sent.
* Zero purchases with positive average order value.
* Zero purchases with positive total spending.

A total of 1,041 records had zero purchases despite having positive total spending.

Since the reason for this inconsistency could not be established from the available dataset information, the original values were retained without modification.

### 4. Redundant and Constant Column Removal

The following five columns were removed after investigating their relationships with other variables:

* `churn_flag`
* `churn_risk_score`
* `satisfaction_level`
* `customer_health_category`
* `dataset_year`

These columns were removed because they were redundant, derived from other variables, or contained constant values.

The dataset was reduced from 48 to 43 columns.

### 5. Outlier Investigation

The Interquartile Range (IQR) method was used to identify potential outliers in numerical variables.

Potential outliers were identified in:

* `avg_order_value_usd`
* `days_since_last_purchase`
* `support_interactions`
* `marketing_emails_opened`
* `marketing_emails_clicked`
* `churn_revenue_impact_usd`
* `customer_health_score`

These values were investigated using descriptive statistics and percentile distributions.

The identified values were retained because they could represent genuine customer behaviour. No automatic deletion or capping was performed.

### 6. Final Dataset Validation

The cleaned dataset was validated after preprocessing.

| Validation               | Result |
| ------------------------ | -----: |
| Final records            | 50,000 |
| Final columns            |     43 |
| Duplicate rows           |      0 |
| Unique churn IDs         | 50,000 |
| Remaining missing values | 29,347 |

The remaining missing values are expected `NaT` entries in `churn_date` for non-churned records.

The cleaned dataset was saved separately for subsequent analysis.

## Planned Analysis – Phase 3

The next phase will focus on Exploratory Data Analysis (EDA).

