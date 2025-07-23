# Lab 4: Regression Analysis with Regularization Techniques

## Course Information
- **Course**: Advanced Big Data and Data Mining
- **Assignment**: Lab 4 - Regression Analysis with Regularization Techniques
- **Dataset**: Diabetes Dataset (scikit-learn)

## Purpose

This lab explores various regression techniques and their performance on the diabetes dataset, with a focus on understanding the effects of regularization. The primary objectives include:

1. **Compare different regression approaches**: Simple linear, multiple linear, and polynomial regression
2. **Analyze regularization effects**: Implement Ridge and Lasso regression with various regularization parameters
3. **Evaluate model performance**: Use multiple metrics (MAE, MSE, RMSE, R²) to assess and compare models
4. **Understand overfitting**: Observe how polynomial complexity and regularization affect model generalization

## Dataset Overview

- **Samples**: 442 diabetes patients
- **Features**: 10 baseline variables (age, sex, BMI, blood pressure, 6 blood serum measurements)
- **Target**: Quantitative measure of disease progression one year after baseline
- **Range**: Target values from 25.00 to 346.00

## Methods Implemented

### 1. Simple Linear Regression
- Used single best feature (BMI) with highest correlation to target (0.586)
- Baseline model for comparison

### 2. Multiple Linear Regression
- Utilized all 10 features
- Significant improvement over simple linear regression

### 3. Polynomial Regression
- Tested degrees 1-4 to explore non-linear relationships
- Monitored for overfitting at higher degrees

### 4. Regularized Regression
- **Ridge Regression**: L2 regularization with α values [0.1, 1.0, 10.0, 100.0, 1000.0]
- **Lasso Regression**: L1 regularization with same α values
- Features standardized using StandardScaler


### Key Findings

1. **Best Performing Model**: Lasso regression with α=1.0 achieved the highest R² score (0.467) and lowest RMSE (53.142)

2. **Overfitting in Polynomial Regression**: 
   - Degree 2: Reasonable performance (R² = 0.416)
   - Degrees 3-4: Severe overfitting with negative R² scores (-14.561, -26.728)

3. **Regularization Benefits**:
   - Ridge regression maintained stable performance across different α values
   - Lasso regression showed feature selection properties (some coefficients → 0)
   - Both techniques prevented overfitting better than high-degree polynomials

4. **Feature Importance**: Most significant features based on coefficients:
   - s1 (serum measurement): -931.489
   - s5 (serum measurement): 736.199
   - BMI: 542.429

5. **Dataset Characteristics**:
   - Moderate linear relationships (best single feature correlation: 0.586)
   - Multiple features provide substantially better predictions than single features
   - Benefits from regularization despite moderate dataset size

## Challenges and Decisions

### Challenges Faced

1. **Polynomial Overfitting**: High-degree polynomials showed extreme overfitting, requiring careful analysis of the bias-variance tradeoff

2. **Feature Scaling**: Had to implement StandardScaler for regularized models to ensure fair coefficient comparison

3. **Alpha Selection**: Choosing appropriate regularization parameters required testing multiple values and analyzing the regularization path

### Key Decisions Made

1. **Feature Selection for Simple Regression**: Chose BMI as it had the highest correlation with the target variable (0.586)

2. **Regularization Parameter Range**: Selected logarithmic scale (0.1 to 1000.0) to observe diverse regularization effects

3. **Performance Metrics**: Used multiple metrics (MAE, MSE, RMSE, R²) to get comprehensive model evaluation

4. **Visualization Strategy**: Created correlation heatmaps and performance comparison charts to better understand data relationships and model behavior

## Technical Implementation

### Libraries Used
- **NumPy & Pandas**: Data manipulation and analysis
- **Scikit-learn**: Machine learning algorithms and metrics
- **Matplotlib & Seaborn**: Data visualization
- **Warnings**: Clean output presentation

### Code Structure
- Data preparation and exploration
- Sequential implementation of regression techniques
- Comprehensive performance evaluation
- Visual comparisons and analysis


## Conclusion

This lab successfully demonstrated the importance of regularization in regression analysis. While simple linear regression provided a baseline, multiple linear regression showed significant improvement. Polynomial regression revealed the dangers of overfitting, while Ridge and Lasso regression provided the best balance between bias and variance, with Lasso achieving the optimal performance on this dataset.
