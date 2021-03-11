# Understanding Twitter Sentiment Analysis

## Overview
![Blight](https://www.newstatesman.com/sites/default/files/styles/cropped_article_image/public/blogs_2014/07/lafayette.jpg?itok=0My_zKs4)


   For this project we wanted to better predict what kind of sentiment a twitter comment 
   had, between positive and negative.

   When any particular event takes place you want to know how it was recieved, but going 
   through each individual tweet and understanding the sentiment can be time consumming
   and tiersome. So we decided to try and automate the process using natural language 
   processing.

   In order to preform this task we first needed to understand what kind of words someone
   would typically use to convey a particular type of sentiment. 


    
## Methodology
1. Gather and merge the data along usefull columns and synthesize a more useable dataset
2. Perform EDA with statistical analysis to determine statistically significant features as well as dropping nan values and useless features.
4. Test baseline model and tune to Precision
5. Test different models with different hyper perameters and use cross validation
6. Implement the different models to preform on the data set and categorize the values

## Results

    For this project we started with very large data sets, so the 
    first step was stripping down what we thought would be usefull 
    and combining it all into one dataset. This is primarilly what 
    the ingeniring notebook was used for. We also used this notebook 
    to do some feature engineering with the crime_count. 

    After this was done we moved on to trying out different models with 
    the synthesized data. In. order to get a minimum for how much money 
    we can expect for the budgest we decided to go with precision. This 
    would allow us to be certain and correctly allocate revenue with flase 
    negatives giving us an upper bound on the budget. 
    
    With this in mind we decided to start with a baseline model using 
    Logistic Regression. With this model we were able to get a precision 
    score of .61. This isn't a terrible score but because of the class imbalance 
    we got a low F1 score (.03). As a result we decided to try and fix this 
    imbalance using SMOTE, this did help with the F! score  (.33), but drastically 
    reduced our precision rate (.23). 
    
    With this in mind we decided to move forward with tuning for precision, as we 
    wanted to be certain that the stated amount would come through and an upper bound on 
    the budget would only be a possitive thing. 
    
    Next we decided to try a Decission tree model, this resulted in a much better 
    precission rate (.61), but the problem of a low F! score (.31) presisted. We 
    wanted to better tune our model for precision so we decided to use smote again, 
    but the same problem aross of lowering the precession score to raise the F!.

## Modeling
Using Scikit-learn and IMBlearn packages 7 classification models were crated.
- Logerithmic Regression 
- Logerithmic Regression with SMOTE
- Decession Tree 
- Decession Tree with SMOTE
- Random Forest
- Decission Tree with GridSearchCV
- AdaBoost Gradient Boosting and Weak Learners

It was determined that the Random Forest model perfromed the best and was utilized for the final implementation. 

## Conclusion
The synthesized data was analyzed and modeled. Some of the significant factors in determining if someone was going to pay on time were Judgement amount, crime count, disposition, and the condition of the lot. Applying the Scikit-learn Models we were able to get a precision score of 91%. The feature that had the most impact was judgement amount


## Future Work
-Tune the Model to better predict on both Recall and Precision
-Better synthesize the data to account for Nan and null values
-Apply a multivariable classification to include people who didn't pay on time but still paid.

## Repository Structure

    "├── README.md                    <- The top-level README for reviewers of this project\n",
    "├── moduling.ipynb               <- Notebook that gpes pver out modling process\n",
    "├── ingeniring_utils.py          <- Contains python feature functions\n",
    "├── modeling_utils.py            <- Contains python module functions\n",
    "├── images                       <- Both sourced externally and generated from Code\n",       
    "│                                          
    "├── ingeniring.ipynb             <- Notebook Used for feature engineering before Modeling\n",
    "├── modules                      <- Saved models\n",
    "└── data                         <- Synergized Data obtained from University of Michigan and Detroit Open Data Portal\n",
    
**Authors** <br>
[Ivan Vanko](https://github.com/vanitoz)<br>
[Kelvin Arellano](https://github.com/Kelvin-Arellano)<br>
