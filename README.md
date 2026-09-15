"# Multiple-Linear-Regression" 
# Problem Statement:
# The dataset contains information about advertising budgets and sales.
# We want to predict the sales based on the advertising budgets for TV, Radio, and Newspaper.

# Column description:
# - TV: Advertising budget for TV in thousands of dollars
# - Radio: Advertising budget for Radio in thousands of dollars
# - Newspaper: Advertising budget for Newspaper in thousands of dollars
# - Sales: Sales in thousands of units

# Algorithm:
# We will use Multiple Linear Regression to predict the sales based on the advertising budgets for TV, Radio, and Newspaper.
# We will use Scikit-Learn's LinearRegression model for this purpose.
# Equation:
# Sales = c + m1*TV + m2*Radio + m3*Newspaper

# Broad Steps to Solve the Problem:
# 1. Import necessary libraries
# 2. Load the dataset
# 3. Explore the dataset ( to see if there are any missing values, outliers, etc., and also to check if there is linear relationship between the features and the target variable)
# 4. Encoding categorical variables (if any)
# 5. Separate the independent variables (features) to X and dependent variable (target) to y
# 6. Split the dataset into training and testing sets
# 7. Scale the independent variables (if necessary). You will not scale the dependent variable.
# 8. Modeling - apply the Multiple Linear Regression algorithm or any other algorithm of your choice
# 9. Make predictions on the test set
# 10. Evaluate the model performance using appropriate metrics (e.g., R-squared, Mean Absolute Error, etc.)
# 11. Visualize the results (if necessary)
# 12. Save the model (if necessary)
# 13. Document the findings and conclusions
# 14. Share the results with stakeholders (if necessary)
# 15. Deploy the model (if necessary)