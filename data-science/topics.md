# Data Science Topics Cheatsheet (Ordered by Exam Frequency)

1. **Model Evaluation Metrics / Performance Evaluation** - 6 reps
    - **Accuracy**: Ratio of correct predictions to total predictions.
    - **Precision**: TP / (TP + FP); focus on minimizing false positives.
    - **Recall**: TP / (TP + FN); focus on minimizing false negatives.
    - **F1-Score**: Harmonic mean of Precision and Recall.
    - **Confusion Matrix**: A table used to describe the performance of a classification model.
    - **ROC/AUC**: Plot of True Positive Rate vs False Positive Rate; AUC represents the degree of separability.

2. **Comparison with other fields** - 5 reps
    - **BI vs DS**: BI focuses on the past/present (reporting); DS focuses on the future (predictions).
    - **AI vs ML**: AI is the broad concept of machines acting "smart"; ML is a subset of AI that learns from data.
    - **DW vs DM**: Data Warehousing is for structured storage; Data Mining is the process of finding patterns in data.

3. **Bias-variance tradeoff, underfitting, and overfitting** - 5 reps
    - **Bias**: Error due to overly simplistic assumptions in the learning algorithm.
    - **Variance**: Error due to too much complexity (sensitivity to small fluctuations in training set).
    - **Underfitting**: Model is too simple to capture the underlying trend (High Bias).
    - **Overfitting**: Model captures noise along with the underlying pattern (High Variance).

4. **Tools and Libraries** - 4 reps
    - **Pandas**: Essential for data manipulation and analysis using DataFrames.
    - **NumPy**: Supports large, multi-dimensional arrays and matrices.
    - **Scikit-Learn**: The primary library for machine learning algorithms in Python.
    - **Matplotlib/Seaborn**: Standard libraries for data visualization.

5. **Data governance and data quality assurance** - 4 reps
    - **Data Governance**: High-level rules/processes for data availability, usability, integrity, and security.
    - **Data Quality**: Ensuring data is accurate, complete, consistent, and timely.

6. **Data wrangling techniques** - 3 reps
    - The process of cleaning, transforming, and mapping raw data into a usable format.
    - Techniques include **Reshaping**, **Pivoting**, and **Aggregating**.

7. **Exploratory Data Analysis (EDA) / Visualization techniques** - 3 reps
    - Using visual methods (histograms, box plots, scatter plots) to understand data structure, detect outliers, and check assumptions.

8. **Visualization tools** - 3 reps
    - **Matplotlib**: Basic plotting library for static visualizations.
    - **Seaborn**: Built on top of Matplotlib; provides a high-level interface for attractive statistical graphics.
    - **Tableau**: A powerful BI tool for interactive dashboards and data storytelling.

9. **Data management activities** - 3 reps
    - Tasks involving the collection, storage, and movement of data throughout its lifecycle.

10. **Data pipelines (ETL)** - 3 reps
    - **Extract**: Collecting data from various sources.
    - **Transform**: Cleaning and formatting data for analysis.
    - **Load**: Inserting data into a target system (like a database).

11. **Applications and domains of Data Science** - 2 reps
    - Used in Healthcare (diagnosis), Finance (fraud detection), E-commerce (recommendations), and Marketing.

12. **Data sources** - 2 reps
    - Origins of data: Databases (SQL), APIs, Web Scraping, Sensors, and Social Media.

13. **Different types of data** - 2 reps
    - **Structured**: Organized in rows/columns (SQL).
    - **Unstructured**: No predefined format (Images, Video, Text).
    - **Semi-structured**: Has some organization but not rigid (JSON, XML).

14. **Data transformation** - 2 reps
    - **Scaling/Normalization**: Adjusting feature values to a standard range (e.g., 0 to 1).
    - **Encoding**: Converting categorical labels into numerical values.

15. **Descriptive statistics** - 2 reps
    - **Mean/Median/Mode**: Measures of central tendency.
    - **Standard Deviation**: Measure of how spread out numbers are from the mean.

16. **Hypothesis testing** - 2 reps
    - **Null Hypothesis (H0)**: Assumption that there is no effect or difference.
    - **Alternative Hypothesis (H1)**: What you want to prove.
    - **Tests**: t-tests (compare means), Chi-square (test independence).

17. **Supervised learning** - 2 reps
    - Learning with labeled data. Includes **Classification** (discrete labels) and **Regression** (continuous values).

18. **Unsupervised learning** - 2 reps
    - Learning from unlabeled data. Includes **Clustering** (grouping similar items) and **Dimensionality Reduction**.

19. **Ensemble Learning** - 2 reps
    - Combining multiple models to improve performance.
    - **Bagging**: Parallel training (e.g., Random Forest).
    - **Boosting**: Sequential training where each model fixes errors of the previous one.

20. **Data storytelling** - 2 reps
    - Communicating insights effectively using a combination of data, visuals, and narrative for stakeholders.

21. **Data privacy and security considerations** - 2 reps
    - Protecting sensitive data through encryption, access controls, and compliance with regulations like GDPR.

22. **Definition and scope of Data Science** - 1 rep
    - An interdisciplinary field using scientific methods and algorithms to extract knowledge and insights from data.

23. **Data cleaning** - 1 rep
    - Handling missing values (imputing or deleting), removing duplicates, and correcting outliers.

24. **Feature engineering and time-series data** - 1 rep
    - Creating new features to improve model performance; handling data points indexed in time order.

25. **Dummification** - 1 rep
    - Converting categorical variables into binary (0 or 1) indicators (One-Hot Encoding).

26. **Simple linear regression** - 1 rep
    - Predicting a dependent variable based on a single independent variable using a straight line.

27. **Stepwise regression** - 1 rep
    - An automated process of selecting the most significant variables for a regression model.

28. **Hyperparameter tuning** - 1 rep
    - Optimizing the internal settings of an algorithm (e.g., learning rate) to achieve the best performance.

29. **Support Vector Machines (SVM)** - 1 rep
    - Finding the optimal hyperplane that best separates different classes in the feature space.

30. **Artificial Neural Networks (ANN)** - 1 rep
    - Computing systems inspired by biological brains, consisting of interconnected layers of "neurons."

31. **Evaluating models for imbalanced datasets** - 1 rep
    - Using metrics like Precision-Recall curves instead of accuracy when one class heavily outweighs the other.

32. **Types of visualizations** - 1 rep
    - **Bar Charts**: Comparing quantities.
    - **Line Charts**: Showing trends over time.
    - **Scatter Plots**: Showing relationships between two variables.
