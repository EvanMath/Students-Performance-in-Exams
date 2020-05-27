# Students-Performance-in-Exams

# Overview
The goal of this notebook was to examine the influence of test preparation course (TPC), parental education level on students performance. The [Students Performance in Exams](https://www.kaggle.com/spscientist/students-performance-in-exams) data set contains the marks secured by students in three objects, maths, reading and writing.
Questions that arised by working on this data set were:
- How helpfull is the test preparation course?
- Which major factors contribute to test outcomes?
- Beyond preparation test what are the secondary feature that could affect the final score?

# Exploratory Data Analysis (EDA)
Our data set was very clean and had no Null values. In addition, all columns had the expected type of content. My EDA routine covers a small but fundamental part of it, the collection of **metadata** and **descriptive statistics**:
1. Check for null values and data types of columns
2. Get dataframe shape and columns name
3. Get descriptive statistics
These three steps are enough to get a good insight of the data set. Next step is to visualize some of the relationships that might occur between the features of the data frame. *Matplotlib* and *Seaborn* are two modules that can help make some good visualizations and reveal some hidden patterns of the data.
When I started study data visualization I had hard time to understand what the *figure* and the *axes* were and how they differ. So in this notebook I tried to clarify it as better as I could for all these entry level data scientist that will take a look of the notebook.

For data visualisation I created some boxplots for each course. I choosed boxplots because they provide us with much details:
- Minimum and maximum value(lower and upper cap)
- Median(the green value inside the rectangular)
- Provide quartiles, 25%(bottom of the box), 50%(is the same as median), 75%(top of the box)
- Give us the outliers(circles)

In addition, a heatmap help us visualize the correlations between the features. **Plots and summary statistics revealed that TPC and parental education level could influence the final score for each course.**

# Developing a Linear Regression Model to predict maths' score
In this part I thought that the better way to deal with categorical variables was to create dummy variables of them. Pandas module has a vrey useful function to create dummies. The new data frame had 15 columns.
I also create a new class *ColumnLinearRegression* and a helpful function to compoute the **R<sup>2</sup>adjusted** metrics. Linear regression did good enough. To evaluate the model I compare different metrics on different models. Ultimately the best model was the one with 13 features.

# Conclusions
As a tutor in physics for students in high school I always think that TPC are very helpfull for them. It is the final step before the exams, so they gain a good view of their capabilities and how good they have prepaired. They have the chance focus to the part of curriculum that they didn't do well in TPC. 
The analysis confirmed all that and also show that the parental education level it is possible to influence the final score. 
