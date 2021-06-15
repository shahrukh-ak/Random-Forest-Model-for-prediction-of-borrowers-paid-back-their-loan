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

## Exploratory Data Analysis:
I used seaborn and pandas built-in plotting capabilitie to create a histogram of two FICO distributions on top of each other, one for each credit.policy outcome.

![1](https://user-images.githubusercontent.com/55116845/122116601-3b6a0f00-ce3f-11eb-88c4-364e3ad50af6.png)

Create a similar figure, except this time select by the not.fully.paid column.

![2](https://user-images.githubusercontent.com/55116845/122116753-69e7ea00-ce3f-11eb-8c08-2287ef30ae06.png)

Create a countplot using seaborn showing the counts of loans by purpose, with the color hue defined by not.fully.paid.

![3](https://user-images.githubusercontent.com/55116845/122116825-8552f500-ce3f-11eb-83a8-fa1ee6f77807.png)

Let's see the trend between FICO score and interest rate. Recreate the following jointplot.

![4](https://user-images.githubusercontent.com/55116845/122116943-a74c7780-ce3f-11eb-819c-be8b726bd74f.png)

Create the following lmplots to see if the trend differed between not.fully.paid and credit.policy. Check the documentation for lmplot() if you can't figure out how to separate it into columns.

![5](https://user-images.githubusercontent.com/55116845/122117003-c0552880-ce3f-11eb-83c9-5774a1e8ba63.png)

## Setting up the Data:
Then I set up data for Random Forest Classification Model. 

## Categorical Features:
The purpose column is categorical. So, I transformed them using dummy variables so sklearn will be able to understand them. I did this in one clean step using pd.get_dummies.

### Way of dealing with these columns:
<ul>
  <li> Create a list of 1 element containing the string 'purpose'. Call this list cat_feats.</li>
<li> Now use pd.get_dummies(loans,columns=cat_feats,drop_first=True) to create a fixed larger dataframe that has new feature columns with dummy variables. Set this dataframe as final_data.</li>
  </ul>
## Train Test Split
Used sklearn to split your data into a training set and a testing set.

## Training a Decision Tree Model
Started by training a single decision tree first then created an instance of DecisionTreeClassifier() called dtree and fit it to the training data.

## Predictions and Evaluation of Decision Tree
Created predictions from the test set and create a classification report and a confusion matrix.

![R1](https://user-images.githubusercontent.com/55116845/122118834-f398b700-ce41-11eb-8cf3-3dd89d13a8d5.PNG)

![R2](https://user-images.githubusercontent.com/55116845/122119172-512d0380-ce42-11eb-842d-098a6df884b6.PNG)

## Training the Random Forest model

Created an instance of the RandomForestClassifier class and fit it to our training data from the previous step.

Predictions and Evaluation
Let's predict off the y_test values and evaluate our model.

Predict the class of not.fully.paid for the X_test data.

Classification report from the results.

![R3](https://user-images.githubusercontent.com/55116845/122130590-4cbc1700-ce51-11eb-90a5-98ddabdda72a.PNG)

Confusion Matrix for the predictions

![R4](https://user-images.githubusercontent.com/55116845/122130672-7117f380-ce51-11eb-95e3-39096be6af1f.PNG)












