Here's an example of implementing Linear Regression using Python with scikit-learn, which is commonly used for machine learning tasks.

Steps:

1. Import the necessary libraries.


2. Prepare a dataset (split into training and testing sets).


3. Train the Linear Regression model.


4. Make predictions and evaluate the model.



Example Code:

# Step 1: Import necessary libraries
import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error, r2_score

# Step 2: Prepare a simple dataset
# For this example, we'll create a small dataset
# X represents years of experience, and y represents salary

data = {
    'Experience': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
    'Salary': [30000, 35000, 40000, 45000, 50000, 55000, 60000, 65000, 70000, 75000]
}

df = pd.DataFrame(data)

# Step 3: Split dataset into features (X) and target (y)
X = df[['Experience']]  # Feature: Experience
y = df['Salary']        # Target: Salary

# Step 4: Split the dataset into training and testing sets (80% train, 20% test)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Step 5: Train the Linear Regression model
model = LinearRegression()
model.fit(X_train, y_train)

# Step 6: Make predictions on the testing set
y_pred = model.predict(X_test)

# Step 7: Evaluate the model
mse = mean_squared_error(y_test, y_pred)
r2 = r2_score(y_test, y_pred)

print(f"Mean Squared Error: {mse}")
print(f"R-squared: {r2}")

# Optional: Print model coefficients (slope and intercept)
print(f"Model Coefficient (Slope): {model.coef_[0]}")
print(f"Model Intercept: {model.intercept_}")

# Step 8: Predict a salary for someone with 12 years of experience
years_of_experience = np.array([[12]])
predicted_salary = model.predict(years_of_experience)
print(f"Predicted Salary for 12 years of experience: {predicted_salary[0]}")

Breakdown:

X: Years of experience (independent variable).

y: Salary (dependent variable).

The dataset is split into training and testing sets (80% training, 20% testing).

The LinearRegression() model is trained using the training data.

Predictions are made on the test data, and the model is evaluated using metrics like Mean Squared Error (MSE) and R-squared.


This is a simple way to implement Linear Regression in Python for machine learning purposes.
