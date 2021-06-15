# Random-Forest-Model-for-prediction-of-borrowers-paid-back-their-loan
The goal of this project is to classify and predict whether or not the borrower paid back their loan in full using Random Forest Model. 

## Project Overview:
For this project we will be exploring publicly available data from LendingClub.com. Lending Club connects people who need money (borrowers) with people who have money (investors). Hopefully, as an investor you would want to invest in people who showed a profile of having a high probability of paying you back. We will try to create a model that will help predict this.
<br>
Lending club had a very interesting year in 2016, so let's check out some of their data and keep the context in mind. This data is from before they even went public.
<br>
We will use lending data from 2007-2010 and be trying to classify and predict whether or not the borrower paid back their loan in full. You can download the data from here or just use the csv already provided. It's recommended you use the csv provided as it has been cleaned of NA values.
<br>

## Dataset:
Here are what the columns represent:
<ul>
  <li>credit.policy: 1 if the customer meets the credit underwriting criteria of LendingClub.com, and 0 otherwise.</li>
  <li>purpose: The purpose of the loan (takes values "credit_card", "debt_consolidation", "educational", "major_purchase", "small_business", and "all_other").</li>
  <li>int.rate: The interest rate of the loan, as a proportion (a rate of 11% would be stored as 0.11). Borrowers judged by LendingClub.com to be more risky are assigned higher interest rates.</li>
  <li>installment: The monthly installments owed by the borrower if the loan is funded.</li>
  <li>log.annual.inc: The natural log of the self-reported annual income of the borrower.</li>
  <li>dti: The debt-to-income ratio of the borrower (amount of debt divided by annual income).</li>
  <li>fico: The FICO credit score of the borrower.</li>
  <li>days.with.cr.line: The number of days the borrower has had a credit line.</li>
  <li>revol.bal: The borrower's revolving balance (amount unpaid at the end of the credit card billing cycle).</li>
  <li>revol.util: The borrower's revolving line utilization rate (the amount of the credit line used relative to total credit available).</li>
  <li>inq.last.6mths: The borrower's number of inquiries by creditors in the last 6 months.</li>
  <li>delinq.2yrs: The number of times the borrower had been 30+ days past due on a payment in the past 2 years.</li>
  <li>pub.rec: The borrower's number of derogatory public records (bankruptcy filings, tax liens, or judgments).</li>
</ul>
