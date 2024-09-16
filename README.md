# Infant-Life-Expectancy-Prediction
This is a revised version of my first project from my Machine Learning Foundations course 
For my machine learning foundations course final assignment at Cornell Tech, we were asked to create our own project using the machine learning tools that we were taught in class and a dataset of our choice. 

I decided to create a model that predicts the life expectancy of infants of different countries and regions in the world based on several predictive factors. The earlier version of this project was my first ever machine learning project. It being the first, it had a lot of qualms and issues. Therefore, I generate a new version of the project which addresses most of the issues that I encountered in the original project and explored/played with other independently learned ML tools. 

Data Collection 
The data used was a 2021 world happiness report dataset retrieved from kaggle. The dataset consist of 19 columns and 468 data containing rows. More information about the dataset can be found here: Kaggle. Majority for the countries are in sub-subsaharan Africa. “The happiness scores and rankings use data from the Gallup World Poll. The scores are based on answers to the main life evaluation question asked in the poll. This question, known as the Cantril ladder, asks respondents to think of a ladder with the best possible life for them being a 10 and the worst possible life being a 0 and to rate their own current lives on that scale…The following columns: GDP per Capita, Family, Life Expectancy, Freedom, Generosity, Trust Government Corruption describe the extent to which these factors contribute in evaluating the happiness in each country.” Therefore a lower healthy life expectancy value at birth would eventually result in a lower happiness scale for that country. Lets look at singapore with a higher life expectancy and higher happiness level (cumulative)  and compare that with Nigeria with significantly lower happiness level (cumulative): 




We can see that Healthy life expectancy does play a significant role on the happiness level of each country/region. The goal is see if we can predict the chances an infant will survive after birth from several other factors (listed below): 



Data Cleaning and Preprocessing
My first intention was to understand the overall dynamics of dataset before I eliminate any feature. Once I understood the general overview of the dataset (shape, data type, number of missing values of each column), I began my data cleaning process of replacing missing values, removing outliers and removing features with odd data types (country and year). I ended up with 16 features and one label (Healthy life expectancy at birth).
I didn’t include country in my version two because of the results and errors that I encountered in my version 1. 



Version 1:
My first project showed that country reduces the prediction accuracy of the model. I performed one hot encoding which converts the categorical country data to numerical ones making it functional for all model. This attempt only led to a standard rmse result for the linear regressive model of about 12998459383.313635. That could not be normal. 




Version 2: 
For my second attempt, I completely eliminated the country and year feature. This action did was proven to be beneficial as predicted, improving the overall model performance (more about the result will be discussed in the subsequent section).

Algorithm and Feature Selection
Version 1:
I worked with the standard linear regression model, random forest model, gradient boosting decision tree (GBDT) and a general decision tree model for my first project because those where the regression models that were taught in the course. Unfortunately, the decision tree model didn’t perform well with an accuracy score of -3.4825696699710798. The linear regression model as discussed above also didn’t perform well. I assuming that it has something to do with the data cleaning/ preprocessing. 

Version 2
I decided to exclude the decision tree model from my second version of the project because DT is used for classification problems but my problem is regression. I swapped DT for XGBoost. Although XGBoost wasn’t taught in my course, I loved working with it. Ironically, with some hypertuning, XGBoost performed really well with my dataset with a R-squared of 0.9354633135797662. Higher than its ensemble counterparts. 

Conclusion and Future Projections
I had so much fun redoing this project. It amazes me on how much one can accomplish when not under academic stress. 

Although models performed really well, for future regressive and classification projects, I would perform a feature selection during the data cleaning phase. Something as simple as removing the features with low variance would have made a difference in the performance of my linear regression model in this project. I would also love to play with support vector machines (SVM/SVR) and compare my results with that of linear regression. I have seen mixed reviews in papers about SVMs. Some say that SVMs produces high accuracy compared to decision trees and logistic regression and other say that there isn’t much of a difference in accuracy scale. I would love to test that theory for myself. Lastly, I am really intrigued by artificial neural networks, so for another regression problem I would like to play with a multilayer perceptron written in python. 

Based on my amateur research, It is obvious that technological advancements like machine learning can be proven to be very useful in public health. 
