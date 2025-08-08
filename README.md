# AI & ML INTERNSHIP - Task 3: Linear Regression

This repository contains the solution for Task 3 of the AI & ML internship. The project focuses on implementing a multiple linear regression model to predict house prices, following a structured machine learning workflow.

---

## 1. Objective

The objective of this task was to implement and understand linear regression. This involves:
* Preprocessing a raw dataset with a mix of numerical and categorical features.
* Splitting the data into training and testing sets.
* Training a linear regression model using scikit-learn.
* Evaluating the model's performance using standard metrics like MAE, MSE, and R².
* Interpreting the model's coefficients and visualizing its predictive power.

---

## 2. Dataset

* **Dataset Name:** House Price Prediction Dataset
* **Source:** The dataset was downloaded programmatically using `kagglehub`.
* **File:** `Housing.csv`

---

## 3. Tools & Libraries

* **Pandas:** Used for data manipulation, loading, and preprocessing.
* **NumPy:** Used for numerical operations.
* **Scikit-learn:** The primary tool for implementing machine learning, including data splitting (`train_test_split`), model training (`LinearRegression`), and evaluation metrics (`mean_absolute_error`, `mean_squared_error`, `r2_score`).
* **Matplotlib & Seaborn:** Employed for data visualization.

---

## 4. Project Workflow

The following steps were performed to build and evaluate the multiple linear regression model.

### 4.1. Data Preprocessing

* The dataset was loaded, and an initial inspection confirmed there were **no missing values**.
* **Categorical features** (e.g., `mainroad`, `furnishingstatus`) were identified and converted into numerical format.
    * **Binary columns** (`mainroad`, `guestroom`, `basement`, `hotwaterheating`, `airconditioning`, `prefarea`) were mapped from 'yes'/'no' to `1`/`0`.
    * The **multi-category column** (`furnishingstatus`) was converted using One-Hot Encoding via `pd.get_dummies()`.

### 4.2. Model Training and Evaluation

* The preprocessed data was split into **training (80%) and testing (20%) sets**.
* A **multiple linear regression model** was initialized and trained on the training data.
* The model's performance on the test set was evaluated using key metrics:
    * **Mean Absolute Error (MAE):** `970043.40`
    * **Mean Squared Error (MSE):** `1754318687330.66`
    * **R-squared (R²):** `0.65`

### 4.3. Model Interpretation and Visualization

* **Coefficients:** The coefficients for each feature were extracted from the trained model.
    * The coefficients show the change in price for a one-unit increase in a given feature (e.g., `area` has a coefficient of `235.97`, meaning a 1-unit increase in area is associated with a `₹235.97` increase in price).
    * **Negative coefficients** for `furnishingstatus_semi-furnished` and `furnishingstatus_unfurnished` indicate that these statuses correlate with a lower price compared to a 'furnished' house.
* **Visualization:** A scatter plot of **Actual vs. Predicted Prices** was generated to visually assess the model's accuracy. The points on the plot show a cluster around the ideal fit line, visually confirming the R-squared score of 0.65.

<br>
<br>

---

## 5. Key Learnings and Insights

* **Preprocessing is Key:** Categorical data must be converted to numerical format for a linear regression model.
* **Model Evaluation:** The R² score provides a powerful way to understand a model's predictive power. An R² of 0.65 means the model explains 65% of the variance in house prices based on the given features.
* **Model Interpretation:** The coefficients allow for a direct understanding of how each feature influences the target variable, making the model's decisions transparent.
* **Real-World Limitations:** The R² score of 0.65, while good, suggests that other unmeasured factors (like location, age of the house, etc.) also play a significant role in determining a house's price.
