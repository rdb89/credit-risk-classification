# Credit Risk Analysis

# Module 20 Report

# by Robert Bentz

## Overview of the Analysis

* The purpose of the credit risk analysis is to evaluate a prediction method to determine how safe a loan is. Banks generally charge a higher interest rate to cover the risk of a loan default. However, higher interest rates deter more desirable (safer) loan applicants who shop lower interest rates. The prediction model can be used to 'weed out' (for better or for worse) applicants more likely to default.

* The credit analysis was performed using loan data that appears to be from the bank itself, without obtaining an outside credit score. The determination was made based upon amount of income, debt, income to debt ratio, number of accounts, total debt, loan size and interest rate. The information was used to determine how safe the given loans were. Part of operating a successful bank is to stay in the black, so the number of successful loans should heavily out-weigh defaulted loans to stay in business.

* The data provided contained "loan_status" which would weigh the prediction solution, and is what was to be determined. Therefore, "loan_status" data was dropped after being separated out (to be used for testing later). Initially the "loan_status" had 75,036 good loans and 2,500 bad loans based upon a binary coding ("value_counts" being 0 for good, 1 for a high risk of defaulting).

* The machine learning stages used for this analysis consisted of:
    - Obtaining the banking data as a CSV file.
    - Importing the CSV file into a Jupyter Notebook for analysis.
    - Splitting the data into training and testing datasets using 'train_test_split'.
    - The actual data was split off after being copied to it's own dataset for comparison (y data).
    - The data was split into training and testing where logistical regression modeling of the original data would be used to generate           values to compare to the actual values for accuracy determination.
    - The calculated (predicted) values were compared to the actual values to determine accuracy of the prediction model.

* The Logistic Regression Model method was used with the original data, using a random state parameter of 1 for modeling. The purpose of using logistic regression is to model and predict questions that need a yes/no (positive/negative) answer. In this case, the question was posed as, "Will this person default on a loan?". Yes or No.

## Results

Using Logistic Regression Model Method (a machine learning model) with the original data, the following results were obtained:
* Balanced Accuracy Score comparing test and prediction values for loan status was 0.9918.
* The Confusion Matrix generated for the loan status was ([18663,102],[56,563]).
* The Precision for healthy loans was at 1.00 while 0.85 for high-risk loans.
* The Macro Average Accuracy was 0.92 while the Weighted Average was 0.99.
* Recall scores for healthy loans was at 0.99 and 0.91 for high-risk loans.
* The Recall Accuracy scores for Macro Average was at 0.95 while the Weighted Average was at 0.99.
* The F1 score for healthy loans reached the maximum value at 1.00 while high-risk loans obtained a value of 0.88.

## Summary

If you do not recommend any of the models, please justify your reasoning.

In summary, the Logistic Regression Model Method very accurately predicted the safety of the healthy loan risks. The F1 score (1.00) indicates better accuracy is not possible with a precision of 1.00 and recall of 0.99.

On the other hand, is the accuracy of the healthy loan predictions due to a large safety (fudge) factor? The high-risk loan is less than ideal with an F1 score of 0.88. The precision at 0.85 and a recall of 0.91 does suggest the high-risk loan model could be tweaked... at the risk of making the healthy loan predictions not perfect.

Since a bank is in the business of being profitable to stay open, the risks would need to be on the loan defaulting side. Therefore I conclude the prediction model is accurate enough with the risks being placed in the correct area, the loan default possibility.

The modeling risks may be improved by the addition of credit scores. The prediction evaluation may prove otherwise but more data generally broadens the big picture.

# Sources
* https://vitalflux.com/linear-vs-logistic-regression-differences-examples/#:~:text=Some%20of%20the%20real%2Dworld%20examples%20where%20logistic%20regression%20models,an%20email%20is%20a%20spam
* https://towardsdatascience.com/a-look-at-precision-recall-and-f1-score-36b5fd0dd3ec
* https://machinelearningmastery.com/precision-recall-and-f-measure-for-imbalanced-classification
