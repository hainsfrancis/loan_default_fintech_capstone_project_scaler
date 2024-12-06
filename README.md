# Abstract

This project explores the foundational principles of risk analytics in banking and financial services, emphasizing how data-driven strategies can mitigate financial losses in lending. By examining the influence of variables such as loan type, loan purpose, business or commercial nature, and credit score on loan defaults, the study aims to enhance risk assessment frameworks. Additionally, the project investigates the relationship between upfront charges, loan amount, interest rates, and property values with default probabilities. Through analyzing patterns and uncovering insights into default tendencies, the project seeks to support lending institutions in making informed decisions and implementing proactive measures for default prevention.

# About Data

| 1   | 'ID'                       | ID unique id  for each row                                                                                                                                      |
| --- | -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2   | 'year'                     | year when the loan was taken                                                                                                                                    |
| 3   | 'loan_limit'               | confirming loan ('cf') or non-conforming loan ('ncf)                                                                                                            |
| 4   | 'Gender'                   | 'male', 'female', 'Sex Not Available', 'Joint'( if applying as as a couple for home loan)                                                                       |
| 5   | 'loan_type'                | Type of loan(masked data) 'type1','type2','type3'                                                                                                               |
| 6   | 'loan_purpose'             | Purpose of the loan (masked data) :-  'p1', p2','p3','p4'                                                                                                       |
| 7   | 'business_or_commercial'   | if the loan is intended for personal('nob/c') or commercial establishment('b/c')                                                                                |
| 8   | 'loan_amount'              | Amount of Loan(Loan Ticket Size)                                                                                                                                |
| 9   | 'rate_of_interest'         | Rate of Interest on the loan                                                                                                                                    |
| 10  | 'Upfront_charges'          | Upfront charges for the loan                                                                                                                                    |
| 11  | 'property_value'           | Value of the property offered/being constructed for which the loan is taken                                                                                     |
| 12  | 'occupancy_type'           | Occupancy type for the establishment:- 'pr','sr','ir', stands for primary residence, secondary residence, investment residence                                  |
| 13  | 'income'                   | Income of the applicant                                                                                                                                         |
| 14  | 'credit_type'              | Shows names of credit bureaus where information of applicant is taken: 'EXP'(Experian),'EQUI'(Equifax), 'CRIF' ( CRIF High mark Score), 'CIB'(CIBIL Transunion) |
| 15  | 'co-applicant_credit_type' | Shows names of credit bureaus where information of co-applicant is taken                                                                                        |
| 16  | 'age'                      | Age Group of the applicant                                                                                                                                      |
| 17  | 'LTV'                      | Loan to Value ratio, ratio between loan amount and property value                                                                                               |
| 18  | 'Region'                   | Region of the applicant                                                                                                                                         |
| 19  | 'Status'                   | Shows whether the applicant is defaulted or normal, Defaulter(1), Normal(0)                                                                                     |
## Loan Limits Explained: Conforming vs. Non-Conforming Loans

### **Confirming Loans (CF):**

Confirming loans meet the standards set by GSEs like Fannie Mae and Freddie Mac, including loan limits, borrower creditworthiness, and property eligibility. These loans are designed for traditional financial profiles and are easier to qualify for under standardized criteria. They offer high liquidity due to their alignment with GSE requirements, making them easily tradable in the secondary market. This ensures stability and wide acceptance in the lending ecosystem.

### **Non-Conforming Loans (NCF):**

Non-conforming loans do not meet GSE criteria, often due to higher loan amounts (e.g., jumbo loans) or unconventional borrower or property conditions. These loans are tailored for borrowers with unique financial needs or special property requirements. They have lower liquidity because they cannot be sold to GSEs, limiting their tradability in the secondary market. Despite this, they serve a critical role in addressing non-standard borrowing situations.


# Business Recommendations and Insights

## Insights

- Default is linked with missing data in the rate of interest column and the property column.
- LTV (Loan-to-Value ratio) is derived from property value and loan amount; missing values for property affect this calculation.
- Most missing values in the gender field ('Sex Not Available') are from the southern region.
- Since the purpose and type of loan are masked, the missing property value could be due to the absence of collateral or a lack of valuation.
- Almost all loans with missing property values are defaulters.
- **Credit Type**: Credit type shows a stronger correlation with default than credit score, as credit scores are almost evenly distributed across categories.
- Interest rates for non-conforming loans are higher, as expected.
- Loans with missing property values also have higher interest rates.
- After clipping the minimum interest rate movement to 12.5 basis points, the median interest rates show the hierarchy: Type 1 > Type 2 > Type 3.
- Standard loans have a wider spread of interest rates, while defaulted loans have a tighter range.
- Combined credit type 'EQUI-EXP' is associated with higher median anchor rates.
- Combined credit type 'EQUI-EXP' is associated with missing upfront charges.
- Combined credit type 'EQUI-EXP' is associated with missing property values.
- There are 20,770 loans with zero upfront charges, but only 53 of these are defaults.
- Loans with purpose `p4` have a higher proportion of loans with zero upfront charges.
- Income varies significantly across age groups.
- Income shows minimal variation by region.
- Income shows no variation with credit scores.
- A higher loan-to-income ratio indicates financial stress and increases credit risk.
- An LTV ratio exceeding 100 indicates that the property value is insufficient to cover the loan amount, making default highly likely.
### Recommendations

1. Loans without property backing are highly likely to become NPAs and should be closely monitored.
2. Increasing upfront charges can help deter willful defaulters and improve initial risk coverage.
3. If raising upfront charges isn’t feasible, consider marking up interest rates to offset potential risks.
4. When raising interest rates is not viable, reduce the loan amount as a final risk mitigation strategy.
5. Offer smaller loans without property, second mortgages, or balance transfers exclusively to high-credit and high-income customers.
6. Reducing loan tenure can improve recovery efficiency and minimize long-term default risk.
7. For securitization, prioritize including lower ticket-size loans only when supported by high credit scores.
8. Focus on upfront charges and commission income to enhance overall profitability.
9. Discounting interest rates in exchange for higher upfront fees could be a viable profitability strategy.
10. Implementing higher upfront fees can act as a deterrent to willful defaulters.
11. Non-conforming loans should target higher ticket sizes to optimize returns and manage risks effectively.
12. For lower ticket-size loans, consider joint borrowers to reduce default risk.
13. Avoid smaller ticket-size loans unless secured by a first or second charge on property.
14. Pool loans from diverse regions into a single securitization portfolio to decrease credit risk.
15. Include highly creditworthy, higher interest rate, lower ticket-size loans to improve the rate of return while maintaining a balanced risk profile.
16. Inspect data quality in the southern region, particularly addressing missing gender information, to ensure robust analytics and compliance.
