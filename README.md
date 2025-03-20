
# AtliQo Bank Credit Card Launch Project

## Project Overview
The AtliQo Bank Credit Card Launch Project aims to identify a suitable market for a new credit card and validate its effectiveness through data analysis and A/B testing. The project is divided into two phases:
- **Phase 1:** Identifying a target market segment.
- **Phase 2:** Validating the new credit card's performance using A/B testing.

This project follows a data-driven approach to financial strategy, leveraging customer and transaction data to drive business decisions.

## Data and Analysis

### Data Sources
The analysis is based on two key datasets:
- **Customer Data:** Includes demographic details (age, gender, occupation, marital status, annual income) and credit profiles (credit score, credit limit). The dataset comprises 1,000 customers and 1,004 credit profiles.
- **Transaction Data:** Contains transaction history, payment types, product categories, and platforms, with 500,000 transactions recorded.

Data is sourced from CSV files and a MySQL database. Data cleaning and preprocessing were conducted to handle missing values (e.g., replacing null `annual_income` with occupation-wise medians) and outliers (e.g., adjusting extreme ages and incomes to occupation-specific medians), ensuring high-quality input for analysis.

### Analysis Methodology

#### 1. Phase 1: Target Market Identification
- Conducted exploratory data analysis (EDA) on customer demographics and spending patterns.
- Analyzed age distribution, income levels, credit limits, credit scores, payment types, and product preferences across age groups.
- Identified the 18-25 age group as a key target market due to:
  - Low credit card penetration (only ~1,000 transactions using credit cards compared to ~6,000 using UPI).
  - Specific shopping preferences (Beauty & Personal Care, Electronics, Home Decor).
  - High potential for financial growth (average annual income of $50,000, credit limit of $5,000, and credit score of 650).

**Visualizations Supporting Phase 1 Analysis**  
The following visualizations were generated to highlight trends and support the identification of the 18-25 age group as the target market:

![Phase 1 Visualizations](analysis.png)  
*Figure 1: Age Groups Distribution, Average Annual Income, Credit Limit, Credit Score, Payment Types, and Product Categories by Age Group.*

#### 2. Phase 2: A/B Testing & Validation
- Designed an A/B test comparing transaction amounts between control and test groups in the 18-25 age group.
- Sample size was determined using statistical power calculations: 100 customers (40 control, 60 test), based on an effect size of 0.4.
- Campaign execution: The test group received the new credit card for two months (September 10, 2023, to November 10, 2023), while the control group used existing cards.
- Statistical analysis: A two-sample Z-test was conducted to compare the mean transaction amounts between the groups. The alternative hypothesis was set to `two-sided`, meaning the test checked if the difference in means was not equal to zero (default setting).

**Statistical Test Parameters**  
The alternative hypothesis options for the Z-test are defined as follows:

![Alternative Hypothesis Options](alternative_hypothesis.png)  
*Figure 2: Options for the Alternative Hypothesis in the Two-Sample Z-Test.*

The results showed a statistically significant difference, with a Z-score exceeding the critical value and a p-value less than 0.05, leading to the rejection of the null hypothesis. This confirmed that the new credit card significantly increased transaction amounts compared to existing cards.

## Tools and Technologies
| Category             | Tool/Library    | Purpose                                   |
|----------------------|---------------|-----------------------------------------|
| Data Manipulation   | Pandas        | Import, clean, and merge data            |
| Numerical Computing | NumPy         | Perform numerical operations             |
| Data Visualization  | Seaborn, Matplotlib | Generate plots and insights        |
| Statistical Analysis| SciPy         | Conduct statistical tests (e.g., Z-test) |

## Running the Analysis

### Prerequisites
Ensure you have the required datasets (`customer_data.csv`, `transaction_data.csv`) and a MySQL database if needed. Install the required libraries using:
```bash
pip install pandas numpy seaborn matplotlib scipy
```

### Execution Steps
1. **Data Preparation:** Load customer and transaction data, clean missing values, and preprocess relevant columns.
2. **Phase 1 (Target Market Identification):**
   - Run `phase_1_atliqo_bank.ipynb` to generate visualizations and insights.
3. **Phase 2 (A/B Testing & Validation):**
   - Run `phase_2_atliqo_bank.ipynb` to conduct statistical tests and validate the new credit card's impact.

**Note:** Ensure data file paths and database connections are correctly configured in the notebooks to avoid errors during execution.

## Key Findings and Business Implications
- **18-25 Age Group Identified as an Untapped Market:**
  - Low credit card usage with specific shopping preferences (e.g., Beauty & Personal Care, Electronics).
  - Potential for targeted marketing strategies focused on these categories.
- **A/B Test Confirms Significant Improvement:**
  - New credit card led to increased transaction amounts (p-value < 0.05).
  - Statistical validation using the Z-test.
- **Actionable Insights:**
  - Targeted promotions for young customers on platforms like Amazon and Flipkart.
  - Partnering with e-commerce platforms for co-branded credit cards.

This project demonstrates how data-driven decision-making can drive financial growth and optimize product offerings in banking.

## Summary Tables
### Key Findings Overview
| **Phase**              | **Focus**                           | **Key Findings**                                                                |
|----------------------- |------------------------------------ |---------------------------------------------------------------------------------|
| Phase 1: Identification| Target Market Analysis              | 18-25 age group: 18.6% of customers, low income ($50,000 avg), top categories: Beauty & Personal Care, Electronics |
| Phase 2: Validation    | A/B Testing and Statistical Analysis| New card significantly increased transaction amounts (p-value < 0.05), validated by Z-test |

### Demographic and Financial Metrics by Age Group
| **Age Group** | **Percentage** | **Avg Annual Income** | **Avg Credit Limit** | **Avg Credit Score** | **Preferred Payment** | **Top Product Category** |
|---------------|----------------|-----------------------|----------------------|----------------------|-----------------------|--------------------------|
| 18-25         | 18.6%          | $50,000               | $5,000                | 650                  | UPI (~6,000)           | Beauty & Personal Care (~5,000) |
| 26-48         | 25.9%          | $100,000              | $10,000               | 700                  | Net Banking (~4,000)   | Electronics (~5,000)       |
| 49-65         | 55.5%          | $150,000              | $15,000               | 750                  | Debit Card (~5,000)    | Kitchen Appliances (~4,000) |


