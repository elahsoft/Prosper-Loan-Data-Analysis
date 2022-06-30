# Prosper Loan Dataset Exploration
## by Opara Febechukwu Chinonyerem


## Dataset

> The dataset we worked on is the Prosper Loan data, which contains 82 fields. We focused on these fields in our exploration, which are:
1. TotalProsperLoans: Number of Prosper loans the borrower had at the time they created this listing. This value will be null if the borrower had no prior loans.
2. OnTimeProsperPayments: Number of on time payments the borrower had made on Prosper loans at the time they created this listing. This value will be null if the borrower has no prior loans.
3. ProsperPaymentsLessThanOneMonthLate: Number of payments the borrower made on Prosper loans that were less than one month late at the time they created this listing. This value will be null if the borrower had no prior loans.
4. ProsperPaymentsOneMonthPlusLate: Number of payments the borrower made on Prosper loans that were greater than one month late at the time they created this listing. This value will be null if the borrower had no prior loans.
5. ProsperPrincipalBorrowed: Total principal borrowed on Prosper loans at the time the listing was created. This value will be null if the borrower had no prior loans.
6. ProsperPrincipalOutstanding:Principal outstanding on Prosper loans at the time the listing was created. This value will be null if the borrower had no prior loans.
7. LoanCurrentDaysDelinquent: The number of days delinquent.
8. LoanFirstDefaultedCycleNumber: The cycle the loan was charged off. If the loan has not charged off the value will be null.
9. LoanMonthsSinceOrigination: Number of months since the loan originated.
10. LoanOriginalAmount: The origination amount of the loan.
11. LoanOriginationDate:The date the loan was originated.
12. MonthlyLoanPayment:The scheduled monthly loan payment.
13. LP_CustomerPayments: Pre charge-off cumulative gross payments made by the borrower on the loan. If the loan has charged off, this value will exclude any recoveries.
14. LP_CustomerPrincipalPayments: Pre charge-off cumulative principal payments made by the borrower on the loan. If the loan has charged off, this value will exclude any recoveries.
15. LP_InterestandFees: Pre charge-off cumulative interest and fees paid by the borrower. If the loan has charged off, this value will exclude any recoveries.
16. LP_GrossPrincipalLoss: The gross charged off amount of the loan.
17. LP_NetPrincipalLoss: The principal that remains uncollected after any recoveries.
18. Investors: The number of investors that funded the loan.
19. LoanStatus: The current status of the loan: Cancelled,  Chargedoff, Completed, Current, Defaulted, FinalPaymentInProgress, PastDue. The PastDue status will be accompanied by a delinquency bucket.
20. Recommendations: Number of recommendations the borrower had at the time the listing was created.
21. InvestmentFromFriendsCount: Number of friends that made an investment in the loan.
22. InvestmentFromFriendsAmount: Dollar amount of investments that were made by friends.
23. StatedMonthlyIncome: The monthly income the borrower stated at the time the listing was created.
24. Term: The length of the loan expressed in months.
25. MemberKey: The unique key that is associated with the borrower. This is the same identifier that is used in the API member object.
26. DebtToIncomeRatio:The debt to income ratio of the borrower at the time the credit profile was pulled. This value is Null if the debt to income ratio is not available. This value is capped at 10.01 (any debt to income ratio larger than 1000% will be returned as 1001%).
27. LenderYield: The Lender yield on the loan. Lender yield is equal to the interest rate on the loan less the servicing fee.
28. BorrowerRate:The Borrower's interest rate for this loan.
29. EstimatedEffectiveYield: Effective yield is equal to the borrower interest rate (i) minus the servicing fee rate, (ii) minus estimated uncollected interest on charge-offs, (iii) plus estimated collected late fees.  Applicable for loans originated after July 2009.
30. EstimatedLoss: Estimated loss is the estimated principal loss on charge-offs. Applicable for loans originated after July 2009.
31. EstimatedReturn: The estimated return assigned to the listing at the time it was created. Estimated return is the difference between the Estimated Effective Yield and the Estimated Loss Rate. Applicable for loans originated after July 2009.
32. ProsperScore: A custom risk score built using historical Prosper data. The score ranges from 1-10, with 10 being the best, or lowest risk score.  Applicable for loans originated after July 2009. 


## Summary of Findings
>1. From the sample of 7000 dataset taken, it seems that loans with over 2000+ monthly repayment were completed and alot of loans within 0-750 were defaulted and also alot of loans within 0-750 were completed and fewer loans were charged off, cancelled and in final payment in progress status. From the scatter plot we are advicing that loans with higher monthly repayment and higher borrower rate should be given by Prosper. 
> 2. Some Loans of higher risk were estimated to give a negative return but they turned out to give a positive yield of 0.15+. This implies that Prosper can take higher risk by issuing loans of higher risk that would give higher returns and shoulder the risk by having more friends investing in the loan as can be seen below that not much friends are investing in Prosper loans
>3. Prosper have loans of different borrower rate running and it appears that loans of higher borrower rate are associated with higher estimated loss which is in line, but that should not discourage of risk taking, as the soul of every business is risk taking, not just risk taking but calculated risk taking.More loans of higher borrower rate that will result to high estimated returns should be issued and as can be seen that a fewer set of such loans existing were actually completed.
>4. High loan amounts have higher monthly loan repayments but it isn't absolute. As was seen, even very risky loans are having the same range of monthly repayment as less risky loans, which isn't appropriate. Prosper can change this (i.e. more risky loans should have a higher monthly repayment) and then effect a change in their risk appetite and make the loans less risky by reducing the loan term thus having higher monthly repayment and the loan backed with investment from friends to make the loan less risky.
>5. In the multivariate plot of MonthlyLoanPayment, LoanOriginalAmount and LoanStatus we saw that Prosper is not taking much risk in giving higher figures of loans, I observed that the region of 30000 to 35000 was not dense.
>6. In the multivariate plot of loan status, borrower rate and term, we observed that Loans of term 12 and 60 have none cancelled but there are in loans of term 36, We have high defaulted loans of term 12 and 60 with high borrower rate, which means high loss since they are defaulted and high chargedoff loans of term 60. Loans of term 60 have higher value of completed. Nevertheless more loans of term 12 should be given since it has the least amount charged off and least amount currently running and it should be backed up with friends investment to reduce the mean value of defaulted.
>7. In the multivariate plot of stated monthly income, loan original amount and loan status, we observed that Prosper was not considering the stated monthly income in issuing out loan of particular sizes, for more effective yield and a more healthy portfolio individuals with high monthly income should be given higher loans and individuals with lower income should be given lower loans. Majority of low income earners were given high loans and they defaulted and as was seen in stated monthly income of 0-10000 and loan original amounts of 25000 defaulted.
>8. **Observation in the multivariate plot of ProsperScore, LoanStatus and TotalProsperLoans:** All the loans of different ProsperScore have past due and defaulted loans but loans of ProsperScore of 10 seem lesser, and all loans of varied ProsperScore have  chargedoff loans and TotalProsperLoans seems to make difference as they are residing in the range of 0.0 and 1.5. In summary, from the above plot, Prosper needs increase it's risk appetite by giving out more risky loans. By observation, all the customers with cancelled loan do not have TotalProsperLoans > 0.
>9. **Observation in the Multivariate plot of BorrowerRate, LoanOriginalAmount and LenderYield:** From the heat map, it was observed that Loans of borrower rate of 0.2 to 0.3 of 0-5000 amount yielded more that others, and we can't conclude that loans with low borrower rate yield more than loans of higher amount and high borrower rate, as Prosper is not taking the risk of issuing high figure loans at higher borrower rate. I think if Prosper should give higher figure loans to high income earners at a considerable interest rate backed up with friends investing in the loan, more yield can be gotten for the organization.
> 10. **Observation in Multivariate Plot of BorrowerRate, LoanOriginalAmount and InvestmentFromFriendsAmount:** We saw that loans of 30000 and above have no friends investment backing it up and higher loans are not issued at higher interest rate to reduce the risk associated with such loans in terms of their high yields incase of defaulting after the first few months.
>11. **Observation in the Multivariate Plot MonthlyLoanPayment, LoanOriginalAmount and Term:** Prosper loans are following the right trend, loans of higher amount at long term have smaller monthly repayment and loans of high amount at short term have a higher monthly repayment, but the straight line graph is not explicit, Prosper has work to do in making the trend more explicit.
> 12. **Observation in the Multivariate Plot of Term, BorrowerRate and LoanOriginalAmount:** As can be seen from the above plot, high amount of loans at long term are not issued at a higher borrower rate to ensure a high yield at the first few months incase of a default, and also loans of term 12 at a higher amount are not existing, Prosper needs to look into this, their portfolio should be properly mixed.


## Key Insights for Presentation

> The relationship between LenderYield, ProsperScore and EstimatedReturn: To expose that some Loans of higher risk were estimated to give a negative return but they turned out to give a positive yield of 0.15+, which implies that Prosper could venture into higher risk taking by issuing loans of higher risk that would give higher returns and shoulder the risk by having more friends investing in the loan as was seen  that not much friends were investing in Prosper loans.

> The relationship between BorrowerRate, EstimatedLoss and LoanStatus: To expose that more loans of higher borrower rate which will result to high estimated returns (though a great loss at default) should be issued and as can be seen that a fewer set of such loans existing were actually completed, controlled risk taking is adviced.
> The relationship between MonthlyLoanPayment, LoanOriginalAmount and LoanStatus: To expose that Prosper is residing in their comfort zone and is not taking much risk in giving higher figures of loans as the region of 30000 to 35000 LoanOriginalAmount was not dense even when loans in that bracket were completed.

> The relationship existing between StatedMonthlyIncome, LoanOriginalAmount, and LoanStatus: To expose that Prosper was not considering the stated monthly income in issuing out loans of particular sizes. Also to expose that individuals with high stated monthly income were not being issued higher loans and individuals with lower income issued small figure loans, which resulted to some high figure loans issued to low income earners being defaulted.

> The relationship between BorrowerRate, LoanOriginalAmount and LenderYield: To expose that though Prosper portfolio is quite healthy but it wasn't taken much risk by issuing high figure loans with high borrower rate as majority of loans were of the range of 0-5000 at 0.2 to 0.3 borrower rate.

> The relationship between BorrowerRate, LoanOriginalAmount and InvestmentFromFriendsAmount: To expose that loans of 30000 and above have no friends investment backing it up and higher loans were not issued at higher interest rate to reduce the risk associated with such loans in terms of their high yield incase of a default in the first few months.

> High amount of loans at long term are not issued at a higher borrower rate to ensure a high yield at the first few months incase of a default, and also loans of term 12 at a higher amount are not existing, Prosper needs to look into this, their portfolio should be properly mixed.

> Prosper loans are following the right trend, loans of higher amount at long term have smaller monthly repayment and loans of high amount at short term have a higher monthly repayment, but the straight line graph is not explicit, Prosper has work to do in making the trend more explicit.