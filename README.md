### 📊Loan-Default-Analysis

## TABLE OF CONTENT
- [Project Overview](#project-overview)
- [Aim of Analysis](#aim-of-analysis)
- [Tools](#tools)
- [Data Preparation](#data-preparation)
- [Insights and Findings](#insights-and-findings)
- [Recommendations](#recommendations)    
- [Conclusion](#conclusion)
- [Data Source](#data-source)  

### Project Overview🗂️
Data Information:This dataset is a real-world loan application dataset containing information on individual applicants and their loan statuses. It includes various demographic, financial, and employment-related features for each applicant, such as gender, income type, credit amount, employment stability, age, occupation, and education level. The dataset also includes a target variable indicating whether an applicant defaulted on their loan. It was designed to help financial institutions assess customer behavior and identify credit risks, supporting data-driven decisions in lending practices.

### Aim of Analysis🗂️
- To identify key factors associated with loan defaults.
- To analyze customer characteristics such as:
    - Gender
    - Income type
    - Credit amount
    - Employment status
    - Age
    - Occupation
    - Education level
- To uncover patterns and trends that differentiate defaulters from non-defaulters.
- To support better risk assessment and credit scoring practices.
- To help financial institutions make informed lending decisions.
- To minimize financial losses by improving default prediction and prevention strategies.

### Tools
Microsft Excel: Data cleaning and manupulation
PowerBI : For data visualization and report creation.
DAX (Data Analysis Expressions) – For creating custom calculations and measures.

### Data Preparation
Data Cleaning: Data has no missing values and duplicates, and data types was formatted using Power Query.
Data Transformation: Standardized column names, created calculated columns, and applied data normalization where necessary.

### Insights and Findings
  ### 🧭Key Metrics 
- Total Loan Applicant : 307.51K
DAX
Total_applicants = COUNTROWS(application_data)
- Total Loan Defaulters : 24.84K
DAX
Total_Defaulters = CALCULATE(
    COUNTROWS('application_data'),
    ('application_data'[TARGET]) = 1
)
-Defaulter Rate: 8.07%
DAX 
Defaulter_Rate = DIVIDE([Total_Defaulters],[Total_applicants])

  ### Trend
- 👥Defaulters by Gender 
Male : 10655
Female : 14170
Indicates potential differences in financial access, income stability, or creditworthiness across gender lines.

- Contract type by Defaulter
Cash Loan: 23221
Revolving loans: 1604
Cash loans may carry higher risks due to less stringent collateral or income verification.

- 💰Average income by Target loan
Average loan of loan defaulter is 165611.75
Average loan of On-time payer is 169077.72
Lower-income applicants are more prone to default, reinforcing the relationship between income level and credit risk.
DAX
Avg_Income = AVERAGE('application_data'[AMT_INCOME_TOTAL])
Target_Loan = if(application_data[TARGET]=1 , "Default" , "On-time" )

- Defaulters by Education status
Secondary : 19524
Higher Education : 4009
Income Higher : 872
Lower Secondary : 417
Academic Degree : 3
Most defaulters are those with Secondary Education, followed by those with Higher Education.
Default is less frequent among the "Academic" and "Lower Education" groups, possibly due to smaller loan amounts.

- 💼Occupation status
Unknown occupation : 627
Laborers : 583
Sales staff : 309
Driver: 210
core staff :173
Managers: 132
Security staff: 72
High skill tech staff: 70
Cooking staff: 62
Medicine staff:57
Accountants:47
Cleaning staff: 44
Low skill laborers : 35
private service staff: 17
waiters/barmen staff: 15
secretaries: 9
Unclassified (Unknown) and manual labor roles (Laborers, Sales Staff, Drivers) account for the highest number of defaults.
White-collar roles such as Managers, Accountants, and High-Skill Tech Staff show relatively lower default rates.
This pattern suggests a potential link between job stability/income reliability and default risk.

- 👥Marital Status
Married individuals dominate the defaulter pool (18K), followed by Single and Separated applicants.
Could indicate increased financial burdens among married individuals (e.g., family expenses, multiple dependents).

- 💰Defaulters by income type
working : 1522
commmercial associate : 536
pensioner : 298
state servant: 124
unemployment: 8
The working class has the highest default count (15K), followed by commercial and pensioners.
Very few defaults are seen in state service or unemployed, likely due to lower loan accessibility or volume.

- 🏠Defaulters by Living Condition
Housing: 21,272 defaulters (85.69%)
Living with Parents: 1,736 defaulters (6.99%)
Municipal Apartment: 955 defaulters (3.85%)
Rented Apartment: 601 defaulters (2.42%)
Office Apartment: 172 defaulters (0.69%)
A significant majority of defaulters (85.69%) reside in owned housing, indicating that ownership status alone may not guarantee repayment reliability. This challenges the assumption that homeowners are less likely to default and suggests that other factors such as income level, loan burden, or financial obligations might outweigh the stability implied by home ownership.

### Recommendations
Based on the analysis I would recommend the follwing actions:
1.  Enhanced Risk Scoring for High-Risk Groups
Integrate stricter credit scoring mechanisms for:
Female applicants (due to high default ratio)
Cash loan applicants.
Low-income earners and labor-intensive occupations
Consider income stability and family obligations when evaluating loan applications.
Lenders should prioritize occupational data as a key feature in credit risk scoring models.

2. Loan Restructuring Options
Offer flexible repayment options (e.g., grace periods or extended tenors) for:
Married applicants
Working-class and commercial income groups

3. Financial Literacy & Support
Introduce mandatory financial education sessions before loan disbursement, especially for:
Secondary education holders
First-time borrowers
Include budgeting, interest rate understanding, and default consequences.

4. Diversify Loan Products
Promote safer, structured loan products (e.g., Revolving Loans) which show significantly lower default rates.
Consider personalized loan plans based on occupational income trends.

5. Strengthen Pre-Loan Vetting
Integrate third-party employment or income validation APIs to improve accuracy.
Cross-validate housing status with income and employment stability before using it as a risk-lowering factor in credit scoring.

### Conclusion
This analysis highlights critical areas where financial institutions can reduce risk exposure and improve repayment outcomes. A combination of data-driven credit evaluation, borrower education, and personalized loan servicing will enhance sustainability in loan disbursement practices.

### Data Source 
https://www.flaticon.com/
https://www.kaggle.com/datasets/gauravduttakiit/loan-defaulter
