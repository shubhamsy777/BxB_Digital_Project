# <u>Documentation for the BxB Digital Project</u>

Author: Shubham Singh Yadav



## <u>Aim for the Project:</u>

Creating a model that can correctly forecast the demand for the pallets issued by CHEP for the months of July to December of 2017. 

## <u>Data description:</u>

( Data collection duration: Monthly Data for 10 Years [July,2007- June,2017] )

| Feature             | Description for the feature                                  |
| ------------------- | ------------------------------------------------------------ |
| Month               | Last Date of the Month.                                      |
| TransfersInMonth    | Total transfers from Manufacturers to Retailers in that month. |
| BusinessDaysInMonth | Total number of business days in that month.                 |
| IssuesInMonth       | Total number of pallets issued by CHEP in that month.        |

## <u>Evaluation Metric:</u> 

The evaluation metric for the project is MAPE (Mean Absolute Percentage Error). The test set's accuracy is thus set according to this metric only. 

## **<u>*Approach to the solution:*</u>** 

1. Time series problem to Supervised Learning problem: 
   As we have been given all of the input data for all of the features for the next 6 months (except for the output that we have to predict), we could convert this Time Series problem into a Supervised Learning problem, and then we can apply various Machine Learning algorithms(SVM, Linear Regression Models etc.) to it. This is done so as to reduce the complexity of dealing with Time Series problems. 
2. How to convert this problem? :
   We can use the data given to us for the past month as an input in predicting the number of Issues for the current month. With this technique we can make our algorithm learn the dependence on the last months data in predicting the number of Issues in the current month. 
3. Breaking down the Month column: 
   The specific 'day' in the Date is of no use to us, as the data which is provided is monthly. So as to get the maximum out of the feature 'Month' (given as - mm/dd/yyyy), we should extract the 'Month_number' and the 'Year' and use them as two new features.

## <u>Findings from the Dataset:</u>

1. Both the number of transfers and the number of issued pallets from CHEP were on a steady decrease from the year 2007 to 2009. The reason for this decline could be the Global Financial Crisis of 2008-2009, which hit almost all the sectors that CHEP's clients are based in such as Aerospace, Automotive, Consumer goods etc.

## <u>Final Predictions and Outputs:</u> 

The number of Issues for the months July, 2017 to December, 2017 have been provided in the file Submission.csv in the same repository. 

![forecast_plotted](https://user-images.githubusercontent.com/15797312/37564914-6f07c9ea-2ac5-11e8-8ec1-2b80f4fba0d6.png)
