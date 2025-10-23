# E-commerce Customer Purchase Prediction

## 1. Project Overview

This project analyzes an e-commerce dataset to understand the key factors that drive customer purchases. The final goal is to build and evaluate a machine learning model capable of accurately predicting whether a customer will make a purchase (`Will_Buy`).

The analysis is conducted in a Jupyter Notebook and follows a standard data science workflow:
* Data Cleaning and Preparation
* Exploratory Data Analysis (EDA)
* Correlation Analysis
* Feature Engineering (if needed)
* Model Building, Comparison, and Evaluation

## 2. Dataset

The dataset used includes the following columns:
* `Order_ID`
* `Customer_ID`
* `Gender`
* `Age`
* `City`
* `Product_Category`
* `Price`
* `Time_Spent` (e.g., minutes on site)
* `Payment_Method`
* `Past_Purchases` (e.g., number of previous orders)
* `Discount_Available` (True/False)
* `Order_Date`
* `Will_Buy` (The target variable: 1 for Yes, 0 for No)

## 3. Exploratory Data Analysis (EDA) & Key Insights

The EDA process revealed several critical insights into customer behavior:

* **Insight 1: Time Spent is a Key Predictor:**
    There is a strong positive correlation between `Time_Spent` on the platform and the `Will_Buy` variable. Customers who spend more than [e.g., 5.5 minutes] are significantly more likely to make a purchase.

* **Insight 2: Discount Availability Drives Conversion:**
    The `Discount_Available` feature was one of the most powerful influencers. Customers who were offered a discount were [e.g., 40%] more likely to complete a purchase compared to those who were not.

* **Insight 3: Past Behavior Predicts Future Behavior:**
    The `Past_Purchases` variable is a strong indicator of loyalty and future sales. Customers with [e.g., 3 or more] past purchases have a much higher conversion rate than new customers.

* **Insight 4: Demographic & Product-Specific Trends:**
    * The `Age` group [e.g., 25-34] showed the highest purchase frequency.
    * `Product_Category` analysis showed that [e.g., 'Electronics'] had the highest average `Price` but `Will_Buy` was highest for [e.g., 'Apparel'], suggesting price sensitivity in certain categories.
    * `Payment_Method` [e.g., 'Credit Card'] was the most common method, but [e.g., 'PayPal'] users had a slightly higher conversion rate.

## 4. Modeling and Results

The goal was to predict the binary outcome `Will_Buy`. I trained and compared two different classification models.

#### Model 1: Logistic Regression
* **Purpose:** Served as a baseline model to understand the linear relationships in the data.
* **Result:** The model achieved an accuracy of **[e.g., 68%]**. This was considered low, suggesting that the decision boundary is not purely linear.

#### Model 2: K-Nearest Neighbors (KNN)
* **Purpose:** To build a non-linear model that might better capture the complex relationships between customer features.
* **Result:** After scaling the features and tuning the number of neighbors (k), the KNN model achieved a superior accuracy of **[e.g., 82%]** on the test set.

**Conclusion:** The KNN model was selected as the final, recommended model for predicting customer purchase intent due to its higher accuracy.

## 5. Tools Used

* **Python 3**
* **Jupyter Notebook**
* **Pandas:** For data manipulation and analysis.
* **Matplotlib / Seaborn:** For data visualization.
* **Scikit-learn (sklearn):** For building and evaluating machine learning models (LogisticRegression, KNeighborsClassifier, train_test_split, accuracy_score).
