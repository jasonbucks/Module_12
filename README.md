# Module_12 - Supervised Learning

Credit risk poses a classification problem that’s inherently imbalanced. This is because healthy loans easily outnumber risky loans. In this Challenge, we’ll use various techniques to train and evaluate models with imbalanced classes. We’ll use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

   ![Charts Picture](Images/12-5-challenge-image.png)

## Overview of the Analysis

* The purpose of our analysis is to predict whether a loan is healthy or high risk.
* Financial information used in our data includes the loan size, interest rate, borrower income, debt to income ratio, number of accounts, any derogatory marks on the borrower, and the total debt of the borrower.  Using this data, we'll attempt to predict the credit worthiness of the borrower: loan status of 0 (healthy) or 1 (high risk) in our data.
* Our data included 77,536 records of historical loans, 2500 of which were flagged to be at high risk of defaulting.
* We split the data into a training dataset and a testing dataset.  For each prediction model we used, we first fit the model with our training data.  Second, we used our test data to predict based on our fitted model.  Each model's performance is then evaluated for accuracy, recall and precision.
* Both of the models we used were Logistic Regression models.  One of these models used our original training data.  The second model used oversampled training data to make up for the fact that there's only a small number of high risk loans to fit, possibly skewing results in the first model to be more likely to predict loans as healthy.

## Results

* Machine Learning Model 1 - Original Training Data:
  * Balanced Accuracy Score of 0.95
  * Precision for healthy loans of 1.00; Precision for high risk loans of 0.85
  * Recall for healthy loans of 0.99; Recall for high risk loans of 0.91


* Machine Learning Model 2 - Resampled Training Data:
  * Balanced Accuracy Score of 0.99
  * Precision for healthy loans of 1.00; Precision for high risk loans of 0.84
  * Recall for healthy loans of 0.99; Recall for high risk loans of 0.99

## Summary

Using the oversampled data had very little impact on predicting the healthy loan labels - the Precision increased slightly while the Recall decreased slightly, but neither change was statistically significant (Precision remains at 1.00 and Recall is still 0.99 for healthly loan labels).  Precision for the high-risk loans went down slightly, from 0.85 to 0.84 using the oversampled data.  However, the Recall for high-risk loans improved significantly using the oversampled data, increasing to 0.99 from just 0.91 using the original data.  Overall, results using the oversampled greatly improved the model's ability to correctly predict the loans that were actually high-risk while not sacrificing predictive capabilities in any other categories.

I recommend using the Logistic Regression model with the oversampled training data.  This model significantly improves the ability to accurately identify the actual high-risk loans, which is the primary problem we are trying to solve. The model's recall score for high-risk loans is therefore the most important performance metric for our analysis, so the model using the resampled data is the best choice.  The fact that every single other performance metric is either just as good or, at worst, drops by a mere single percentage point using the oversampled data makes that the model the clear winner.


## Contributors

Starter code was provided by UW Fintech Bootcamp.  Updates and analysis by Jason Buckholt.  

---

## License

MIT License

Copyright (c) 2022 Jason Buckholt

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.