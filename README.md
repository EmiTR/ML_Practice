# ML_Practice
To demonstrate how I use machine learning (ML) and advanced analytics to solve business challenges.

# Car Price Prediction – Linear Regression

## 🎯 Goal of the Workbook
The primary objective of this project was to **refresh and deepen my machine learning skills**, which I originally learned in 2022.  
Using **Linear Regression** as the core algorithm, I revisited the complete ML workflow — from data processing and feature engineering to model training, evaluation, and interpretation.  

This notebook aims to both reinforce theory and demonstrate practical implementation of regression analysis step by step.

---

## 🧱 Structure of the Workbook
1. **Data Loading and Exploration**  
   Inspect dataset structure, identify missing values, check distributions, and understand correlations between key features.

2. **Feature Engineering and Preprocessing**  
   - Derived new features such as `age` from `year`  
   - Grouped brands (`make`) into top categories plus “Other”  
   - Transformed fuel types into 5 generalized categories  
   - Filled missing `engine_hp` values by vehicle size  
   - One-hot encoded categorical features and dropped irrelevant or high-cardinality columns  

3. **Model Training and Evaluation**  
   - Target variable: `msrp` (Manufacturer’s Suggested Retail Price)  
   - Log-transformed as `log1p(msrp)` to stabilize variance  
   - Split data into train, validation, and test sets  
   - Trained a Linear Regression model and evaluated performance using **MSE**, **RMSE**, **MAE**, and **R²** both in log-space and in real price scale  

4. **Results Interpretation**  
   - Examined coefficients and feature impact  
   - Analyzed error magnitudes and residual distributions  
   - Interpreted the model’s ability to generalize

5. **Reflection and Lessons Learned**  
   - Summarized what worked well and identified areas for improvement  

---

## 🚗 The Data
The dataset contains car listings with features such as:
- `make`, `model`, `year`, `engine_hp`, `engine_fuel_type`
- `vehicle_size`, `vehicle_style`, `driven_wheels`, `number_of_doors`
- `city_mpg`, `highway_mpg`, and other descriptors  

The target variable is **`msrp`** (price).  
To make the relationship between features and price more linear, the target was log-transformed before training.

Feature engineering steps included:
- Calculating **vehicle age**  
- Grouping **brands** and **styles** into top categories  
- Imputing missing values with median or mode logic  
- One-hot encoding categorical features for model compatibility  

---

## 📈 Results Interpretation
### Performance in Log-space  
- **R²:** ~0.805 — model explains ~80% of log-price variance  
- **RMSE (log):** 0.49 → predictions typically within a factor of ~1.6 of true price  

### Performance in Real Price Scale  
- **R²:** 0.562  
- **RMSE:** ~€43,995  
- **MAE:** ~€14,503  

**Interpretation:**  
The model captures relative price differences well in log-space, but when unlogged, absolute prediction errors grow with price magnitude.  
This is expected for linear regression on highly skewed price data — expensive cars dominate total variance.

---

## 🧭 Lessons Learned
- **Data processing matters most.**  
  It took significantly more time than modelling but had the biggest impact on performance.  

- **Reusable preprocessing function helps.**  
  Creating a `data_input()` function made experimentation much cleaner and reproducible. For future projects I plan to build a proper **`Pipeline`** using `sklearn.pipeline.Pipeline` and `ColumnTransformer` to ensure consistent preprocessing across train/validation/test splits.

- **Technical debt:**  
  Manually implementing LinearRegression

- **Model limitation:**  
  Linear Regression performs well for general trends but struggles with non-linear relationships. Should experiment with other models.


---

**Repository:** [ML_Practice – Predicting Car Price (Linear Regression)](https://github.com/EmiTR/ML_Practice/blob/main/PredictingPrice_LinearRegression.ipynb)
