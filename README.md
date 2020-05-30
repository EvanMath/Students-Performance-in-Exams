# Students-Performance-in-Exams

# Overview
The goal of this notebook was to examine the influence of test preparation course (TPC), parental education level on students' performance. The [Students Performance in Exams](https://www.kaggle.com/spscientist/students-performance-in-exams) data set contains the marks secured by students in three objects, maths, reading, and writing.
Questions that arose by working on this data set were:
- How helpful is the test preparation course?
- Which major factors contribute to test outcomes?
- Beyond the preparation test, what are the second feature that could affect the final score?

# Exploratory Data Analysis (EDA)
Our data set was very clean and had no Null values. Also, all columns had the expected type of content. My EDA routine covers a small but fundamental part of it, the collection of **metadata** and **descriptive statistics**:
1. Check for null values and data types of columns
2. Get data frame shape and columns name
3. Get descriptive statistics
These three steps are enough to get a good insight into the data set. The next step is to visualize some of the relationships that might occur between the features of the data frame. *Matplotlib* and *Seaborn* are two modules that can help make some good visualizations and reveal some hidden patterns of the data.
When I started study data visualization I had a hard time understanding what the *figure* and the *axes* were and how they differ. So in this notebook, I tried to clarify it as better as I could for all these entry-level data scientists that will take a look at the notebook.

For data visualization, I created some boxplots for each course. I chose boxplots because they provide us with many details:
- Minimum and maximum value(lower and upper cap)
- Median(the green value inside the rectangular)
- Provide quartiles, 25%(bottom of the box), 50%(is the same as the median), 75%(top of the box)
- Give us the outliers(circles)

Besides, a heatmap helps us visualize the correlations between the features. **Plots and summary statistics revealed that TPC and parental education level could influence the final score for each course.**

# Developing a Linear Regression Model to predict maths' score
In this part, I thought that the better way to deal with categorical variables was to create dummy variables. Pandas module has a very useful function to create dummies. The new data frame had 15 columns.
I also create a new class *ColumnLinearRegression* and a helpful function to compute the **R<sup>2</sup>adjusted** metrics. Linear regression did good enough. To evaluate the model I compare different metrics on different models. Ultimately the best model was the one with 13 features.

# Conclusions
As a tutor in physics for students in high school, I always think that TPC is very helpful for them. It is the final step before the exams, so they gain a good view of their capabilities and how good they have prepared. They have the chance to focus on the part of the curriculum that they didn't do well in TPC. 
The analysis confirmed all that and also show that the parental education level it is possible to influence the final score. 
