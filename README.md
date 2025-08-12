# README: Practical Application III: Comparing Classifiers

**Overview**: In this practical application, your goal is to compare the performance of the classifiers we encountered in this section, namely K Nearest Neighbor, Logistic Regression, Decision Trees, and Support Vector Machines.  We will utilize a dataset related to marketing bank products over the telephone.  

Our dataset comes from the UCI Machine Learning repository [link](https://archive.ics.uci.edu/ml/datasets/bank+marketing).  The data is from a Portugese banking institution and is a collection of the results of multiple marketing campaigns.  We will make use of the article accompanying the dataset for more information on the data and features.

The dataset collected is related to 17 campaigns that occurred between May 2008 and November 2010, corresponding  to  a  total  of  79354  contacts.  During  these phone campaigns, an attractive long-term deposit application, with good interest rates, was offered. For each contact,  a  large  number  of  attributes  was  stored  (e.g.  see Table  2)  and  if  there  was  a  success  (the  target  variable). For the whole database considered, there were 6499 successes (8% success rate).

While there is no missing data, a substantial number of rows have "unknown" as a value for one or more categories. Model runs with these rows dropped made model accuracy worse, so leaving them as is. We'll convert the target variable to an integer and one hot encode and scale the input variables. The metadata above says to drop the duration column, I found that doing so significantly decreased the accuracy of my models.

**Business Objective**: The business objective of this task is to enhance the efficiency of targeted campaigns for long-term deposit subscriptions by minimizing the number of customer contacts required.

**Findings**: Grid search for hyperparameter tuning resulted in Decision Tree Classification having the best accuracy of all four models at 91.6%. Interestingly enough, I found that three of the five top factors that influenced whether or not a depoist was made were beyond the control of the campaigners. The employment variation rate, consumer price index, and the eurobor 3 month rate had the greatest influence on outcome based on their LR Coefficients. While our goal was to minimize the number of contacts required to get a deposit, the data supports multiple contacts being advantageous. For unknown reasons, March, May and August also seem to be the best months for getting a deposit so if our goal is to minimize contacts, *we should concentrate efforts to those months and when the macroeconomic indicators are favorable.* Keeping 'duration' in the dataset, while it made the models more accurate, is also of dubious value if one were to attempt to use these models inferentially.

By way of next steps, because of the imbalanced nature of the dataset, perhaps further study leveraging oversampling to balance the data might provide for a better model.

Link to Jupyter Notebook on Git: https://github.com/stephen-scheiman/assignment_17_repo/blob/main/prompt_III.ipynb
