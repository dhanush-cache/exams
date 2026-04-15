# Data Science - November 2025 - Answers

## Q1

**a) Describe various domain specific applications of Data Science.**

Data Science is applied across numerous domains to solve complex problems and drive decision-making. 
- In **Healthcare**, it's used for predicting diseases from medical imaging, personalizing treatment plans, and optimizing hospital operations. 
- The **Finance** sector uses it for algorithmic trading, credit scoring, and fraud detection. 
- In **Retail**, data science powers recommendation engines, optimizes supply chains, and analyzes customer sentiment. 
- **Transportation** benefits from route optimization, predictive maintenance for vehicles, and demand forecasting. 
- In **E-commerce**, it is used for customer segmentation, churn prediction, and personalized marketing.

**b) Differentiate between Data Science and Artificial Intelligence.**

- **Artificial Intelligence (AI)** is a broad field focused on creating machines that can perform tasks that typically require human intelligence, such as learning, problem-solving, and understanding language.
- **Data Science** is a multidisciplinary field that uses scientific methods, processes, algorithms, and systems to extract knowledge and insights from structured and unstructured data.
- **Relationship:** Data Science is a subset of AI. While AI is the broader concept of intelligent machines, Data Science is the practice of using data to train these machines and to extract insights. Data scientists often use AI techniques (like machine learning) to build models, but their work also includes data collection, cleaning, and analysis, which are not purely AI tasks.

**c) Explain difficulties in handling unstructured data and explain how difficulties can be resolved.**

Unstructured data (e.g., text, images, videos) lacks a predefined data model, making it difficult to process and analyze.
**Difficulties:**
1.  **Lack of Structure:** It doesn't fit neatly into traditional databases.
2.  **Scalability:** The sheer volume of unstructured data can be overwhelming.
3.  **Analysis:** It requires specialized techniques to extract meaningful information.
4.  **Noise:** It often contains irrelevant information that needs to be filtered out.

**Resolutions:**
1.  **Natural Language Processing (NLP):** For text data, techniques like tokenization, stemming, and sentiment analysis can be used to extract features.
2.  **Computer Vision:** For images and videos, techniques like object detection and image classification can be used.
3.  **NoSQL Databases:** Databases like MongoDB are designed to store and manage unstructured data.
4.  **Feature Engineering:** Converting raw unstructured data into a structured feature set that can be used by machine learning models.

**d) What is data cleaning? Discuss the steps involved in handling missing values and outliers.**

Data cleaning is the process of detecting and correcting (or removing) corrupt or inaccurate records from a dataset. It is a crucial step in the data science pipeline as it directly impacts the quality of the models.

**Handling Missing Values:**
1.  **Deletion:** If the number of missing values is small, the entire row or column can be deleted.
2.  **Imputation:** Missing values can be filled with a substitute value, such as the mean, median, or mode of the column.
3.  **Prediction:** A model can be trained to predict the missing values based on the other features in the dataset.

**Handling Outliers:**
1.  **Deletion:** Outliers can be removed from the dataset, but this should be done with caution as they can sometimes contain valuable information.
2.  **Transformation:** Applying mathematical transformations like logarithmic or square root can reduce the effect of outliers.
3.  **Binning:** Outliers can be grouped into separate bins.

**e) What is data wrangling? Describe data wrangling techniques.**

Data wrangling (or data munging) is the process of transforming and mapping data from one raw data format into another format with the intent of making it more appropriate and valuable for a variety of downstream purposes such as analytics.

**Techniques:**
1.  **Parsing:** Reading data from various sources like CSVs, JSON, or databases.
2.  **Joining:** Combining data from multiple sources.
3.  **Restructuring:** Changing the structure of the data, such as pivoting or unpivoting.
4.  **Enriching:** Adding new data to the existing dataset.
5.  **Filtering and Aggregating:** Selecting specific rows or columns and summarizing the data.

**f) Why is Scikit-learn popular among data scientists, explain.**

Scikit-learn is a popular Python library for machine learning.
**Reasons for its popularity:**
1.  **Comprehensive:** It provides a wide range of supervised and unsupervised learning algorithms.
2.  **Ease of Use:** It has a simple and consistent API, making it easy to learn and use.
3.  **Integration:** It is built on top of other popular Python libraries like NumPy, SciPy, and Matplotlib.
4.  **Open Source:** It is free to use and has a large, active community that contributes to its development.
5.  **Good Documentation:** It has excellent documentation with many examples.

## Q2

**a) What is EDA? Describe any four data visualization techniques applicable for EDA.**

Exploratory Data Analysis (EDA) is the process of analyzing datasets to summarize their main characteristics, often with visual methods. It is used to understand the data, discover patterns, spot anomalies, and check assumptions before formal modeling.

**Data Visualization Techniques for EDA:**
1.  **Histogram:** Displays the distribution of a single numerical variable by dividing the data into bins and showing the frequency of observations in each bin.
2.  **Scatter Plot:** Shows the relationship between two numerical variables. Each point represents an observation.
3.  **Box Plot:** Visualizes the distribution of a numerical variable through its quartiles. It is useful for detecting outliers.
4.  **Heatmap:** A graphical representation of data where the individual values contained in a matrix are represented as colors. It is useful for visualizing correlation matrices.

**b) How hypothesis testing can be done with the help of t-tests and chi-square tests? Give proper examples.**

Hypothesis testing is a statistical method used to make decisions or judgments about a population based on a sample of data.

-   **t-test:** A t-test is used to compare the means of two groups.
    -   **Example:** A pharmaceutical company wants to test if a new drug has an effect on blood pressure. They could take a sample of patients, measure their blood pressure before and after taking the drug, and use a paired t-test to see if there is a significant difference in the mean blood pressure.

-   **Chi-square test:** A chi-square test is used to compare categorical variables.
    -   **Example:** A marketing manager wants to know if there is a relationship between gender and preference for a new product. They could survey a sample of people, ask for their gender and their preference (like, dislike, neutral), and use a chi-square test to see if there is a statistically significant association between the two variables.

**c) Justify the comparison between supervised and unsupervised learning.**

-   **Supervised Learning:** In supervised learning, the algorithm learns from labeled data, meaning each data point is tagged with a correct output. The goal is to learn a mapping function that can predict the output for new, unseen data.
    -   **Examples:** Classification (predicting a category) and regression (predicting a continuous value).
-   **Unsupervised Learning:** In unsupervised learning, the algorithm learns from unlabeled data. The goal is to find hidden patterns or intrinsic structures in the data.
    -   **Examples:** Clustering (grouping similar data points) and dimensionality reduction (reducing the number of variables).

-   **Comparison Justification:** The choice between supervised and unsupervised learning depends on the nature of the problem and the data available. If you have labeled data and a clear prediction goal, supervised learning is the way to go. If you have unlabeled data and want to explore its structure, unsupervised learning is the appropriate choice. They are not competing approaches but rather tools for different tasks.

**d) Describe stepwise regression with its role in model selection.**

Stepwise regression is a method of fitting a regression model in which the choice of predictive variables is carried out by an automatic procedure. In each step, a variable is considered for addition to or subtraction from the set of explanatory variables based on some prespecified criterion.

**Role in Model Selection:**
The main role of stepwise regression is to simplify a model by selecting a subset of the original variables to include. This can help to:
1.  **Reduce multicollinearity:** By removing redundant variables.
2.  **Improve model interpretability:** A simpler model is easier to understand.
3.  **Avoid overfitting:** By reducing the complexity of the model.

There are three main approaches: forward selection, backward elimination, and bidirectional elimination.

**e) Discuss various techniques available for evaluating model performance.**

Evaluating model performance is crucial to determine the quality of a machine learning model.

**Techniques for Classification Models:**
1.  **Confusion Matrix:** A table that summarizes the performance of a classification model.
2.  **Accuracy:** The proportion of correct predictions.
3.  **Precision and Recall:** Precision is the proportion of true positives among all positive predictions, while recall is the proportion of true positives among all actual positives.
4.  **F1-Score:** The harmonic mean of precision and recall.
5.  **AUC-ROC Curve:** A plot of the true positive rate against the false positive rate at various threshold settings.

**Techniques for Regression Models:**
1.  **Mean Absolute Error (MAE):** The average of the absolute differences between the predicted and actual values.
2.  **Mean Squared Error (MSE):** The average of the squared differences between the predicted and actual values.
3.  **R-squared:** A statistical measure of how close the data are to the fitted regression line.

**f) Write a note on Artificial Neural Network.**

An Artificial Neural Network (ANN) is a computational model inspired by the structure and function of biological neural networks. ANNs are composed of interconnected nodes called "neurons," organized in layers.

-   **Structure:** An ANN consists of an input layer, one or more hidden layers, and an output layer. Each connection between neurons has a weight associated with it, which is adjusted during the training process.
-   **Function:** Each neuron receives inputs, applies a weighted sum, and then passes the result through an activation function to produce an output.
-   **Learning:** ANNs learn by a process called training, where the weights of the connections are adjusted to minimize the difference between the network's output and the desired output. A common training algorithm is backpropagation.
-   **Applications:** ANNs are used in a wide variety of applications, including image recognition, natural language processing, and financial forecasting.

## Q3

**a) Describe evaluating model for imbalanced data sets.**

Imbalanced datasets are those where the number of observations per class is not equally distributed. In this case, standard evaluation metrics like accuracy can be misleading.

**Evaluation Metrics for Imbalanced Data:**
1.  **Precision-Recall Curve:** A better alternative to the ROC curve for imbalanced datasets.
2.  **F1-Score:** The harmonic mean of precision and recall, providing a balanced measure.
3.  **Cohen's Kappa:** A statistic that measures inter-rater agreement for categorical items. It takes into account the possibility of the agreement occurring by chance.
4.  **Matthews Correlation Coefficient (MCC):** A correlation coefficient between the observed and predicted binary classifications. It returns a value between -1 and +1.

**Techniques to Handle Imbalance:**
-   **Resampling:** Oversampling the minority class or undersampling the majority class.
-   **SMOTE (Synthetic Minority Over-sampling Technique):** Creating synthetic samples of the minority class.

**b) What is the role of storytelling in data science, explain.**

Storytelling in data science is the ability to communicate the insights from data in a clear, concise, and compelling way. It's not just about presenting charts and numbers; it's about weaving a narrative that helps the audience understand the context, the findings, and the implications of the analysis.

**Role of Storytelling:**
1.  **Makes Insights Memorable:** A good story is easier to remember than a list of facts.
2.  **Drives Action:** It can persuade stakeholders to make data-driven decisions.
3.  **Provides Context:** It helps the audience understand the "why" behind the data.
4.  **Builds Trust:** A well-told story can build trust in the data and the analysis.
5.  **Simplifies Complexity:** It can make complex findings accessible to a non-technical audience.

**c) Discuss various data management activities used in ensuring data usability and quality.**

Data management is the practice of collecting, keeping, and using data securely, efficiently, and cost-effectively.

**Activities for Data Usability and Quality:**
1.  **Data Governance:** Establishing policies and procedures for managing data.
2.  **Data Quality Management:** Ensuring that data is accurate, complete, consistent, and timely. This includes data cleaning and validation.
3.  **Data Security:** Protecting data from unauthorized access and breaches.
4.  **Master Data Management (MDM):** Creating a single source of truth for critical data.
5.  **Data Warehousing:** Storing data from various sources in a central repository for analysis.
6.  **Data Documentation:** Creating metadata that describes the data and its context.

**d) Explain data pipeline and the stages involved in ETL.**

A data pipeline is a set of data processing elements connected in series, where the output of one element is the input of the next. It is a system for moving data from a source to a destination.

**ETL (Extract, Transform, Load) Stages:**
1.  **Extract:** The process of reading data from a source system. The data can come from various sources, such as databases, files, or APIs.
2.  **Transform:** The process of converting the extracted data from its original format into the format required for the destination system. This can include data cleaning, aggregation, and enrichment.
3.  **Load:** The process of writing the transformed data into the destination system, which can be a database, a data warehouse, or a data lake.

**e) Write a note on Seaborn and Tableau visualization tools.**

-   **Seaborn:** Seaborn is a Python data visualization library based on Matplotlib. It provides a high-level interface for drawing attractive and informative statistical graphics.
    -   **Features:** It is particularly well-suited for creating complex visualizations like heatmaps, violin plots, and pair plots. It integrates well with pandas DataFrames.
-   **Tableau:** Tableau is a powerful and popular data visualization tool used for business intelligence.
    -   **Features:** It allows users to create interactive and shareable dashboards. It can connect to a wide variety of data sources. It has a user-friendly drag-and-drop interface that makes it accessible to non-programmers. While Seaborn is code-based, Tableau is a GUI-based tool.

**f) Describe various data privacy and security considerations in data management practices.**

Data privacy and security are critical aspects of data management.

**Privacy Considerations:**
1.  **Anonymization and Pseudonymization:** Removing or encrypting personally identifiable information (PII).
2.  **Consent:** Obtaining clear consent from individuals before collecting and using their data.
3.  **Data Minimization:** Collecting only the data that is necessary for a specific purpose.
4.  **Compliance:** Adhering to data privacy regulations like GDPR and CCPA.

**Security Considerations:**
1.  **Access Control:** Limiting access to data to authorized individuals.
2.  **Encryption:** Encrypting data both in transit and at rest.
3.  **Data Backup and Recovery:** Regularly backing up data and having a plan for data recovery in case of a disaster.
4.  **Auditing and Monitoring:** Regularly monitoring for security threats and conducting security audits.

## Q4

**a) Write advantages of using NumPy Library for data science in Python.**

NumPy (Numerical Python) is a fundamental package for scientific computing in Python.

**Advantages:**
1.  **Performance:** NumPy arrays are much more efficient for storing and manipulating numerical data than Python's built-in lists. Many NumPy operations are implemented in C, making them very fast.
2.  **Functionality:** It provides a large collection of high-level mathematical functions to operate on these arrays.
3.  **Vectorization:** NumPy allows for vectorized operations, which means that you can perform operations on entire arrays without the need for explicit loops. This makes the code more concise and readable.
4.  **Integration:** It is the foundation of the scientific Python ecosystem and is used by many other libraries like pandas, Scikit-learn, and Matplotlib.

**b) Define Bias variance tradeoff in terms of Data Science.**

The bias-variance tradeoff is a fundamental concept in machine learning.
-   **Bias:** Bias is the error from erroneous assumptions in the learning algorithm. High bias can cause an algorithm to miss the relevant relations between features and target outputs (underfitting).
-   **Variance:** Variance is the error from sensitivity to small fluctuations in the training set. High variance can cause an algorithm to model the random noise in the training data, rather than the intended outputs (overfitting).

**Tradeoff:**
-   A simple model with few parameters will have high bias and low variance.
-   A complex model with many parameters will have low bias and high variance.
-   The goal is to find a balance between bias and variance that minimizes the total error of the model.

**c) What is AUC? How it can be used?**

AUC stands for **Area Under the Curve**. It is a performance measurement for classification problems at various threshold settings. The "curve" is the **Receiver Operating Characteristic (ROC) curve**.

-   **ROC Curve:** A plot of the true positive rate (TPR) against the false positive rate (FPR) at different classification thresholds.
-   **AUC:** The AUC represents the degree or measure of separability. It tells how much the model is capable of distinguishing between classes. A higher AUC (closer to 1) indicates a better model. An AUC of 0.5 suggests a model with no discrimination ability (like random guessing).

**How it is used:**
-   It is used to compare the performance of different classification models.
-   It is particularly useful for imbalanced datasets where accuracy can be misleading.

**d) What is dummification? Give example.**

Dummification is the process of converting categorical variables into a format that can be provided to machine learning algorithms to do a better job in prediction. This is done by creating binary variables (0 or 1) for each category.

**Example:**
Suppose you have a categorical feature "Color" with categories "Red," "Green," and "Blue."
Dummification would create three new binary features:
-   `Color_Red`: 1 if the color is Red, 0 otherwise.
-   `Color_Green`: 1 if the color is Green, 0 otherwise.
-   `Color_Blue`: 1 if the color is Blue, 0 otherwise.

If an observation has the color "Green", the new features would be: `Color_Red=0`, `Color_Green=1`, `Color_Blue=0`. This is also known as one-hot encoding.

**e) Describe application of simple linear regression in predictive modelling.**

Simple linear regression is a statistical method that allows us to summarize and study relationships between two continuous (quantitative) variables. One variable, denoted x, is regarded as the predictor, explanatory, or independent variable. The other variable, denoted y, is regarded as the response, outcome, or dependent variable.

**Application in Predictive Modeling:**
Simple linear regression is used to predict the value of a dependent variable based on the value of an independent variable.
-   **Example:** A real estate agent could use simple linear regression to predict the price of a house based on its size. The size of the house would be the independent variable (x), and the price would be the dependent variable (y). The model would learn a linear relationship between size and price from historical data and could then be used to predict the price of new houses.

**f) Write python program to draw line chart. Assume your own data.**

```python
import matplotlib.pyplot as plt

# Sample data
x_values = [1, 2, 3, 4, 5]
y_values = [2, 3, 5, 7, 11]

# Create a line chart
plt.plot(x_values, y_values)

# Add titles and labels
plt.title("Simple Line Chart")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")

# Show the plot
plt.show()
```
This program uses the `matplotlib.pyplot` library to create a simple line chart. It defines two lists of numbers, `x_values` and `y_values`, and then uses `plt.plot()` to create the chart. The `plt.title()`, `plt.xlabel()`, and `plt.ylabel()` functions are used to add a title and labels to the axes. Finally, `plt.show()` displays the chart.
