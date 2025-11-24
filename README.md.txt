Business Understanding (Brief)
The business goal is to understand what drives used car prices so dealers can price and stock inventory more effectively.
As a data task, this becomes building a supervised regression model that predicts price from vehicle attributes (age, mileage, manufacturer, type, drivetrain, fuel, condition, etc.) and using model outputs to quantify which features most strongly influence price.

Data Understanding (Brief)
To assess our dataset, we:
•	Inspected structure and types (df.info(), df.describe()).
•	Checked missingness across fields and identified highly incomplete columns.
•	Examined distributions for price, year, odometer, and engineered age.
•	Detected major outliers (multi-million prices, 10M-mile odometers).

Data Preparation (Brief)
We prepared the dataset by:
•	Removing extreme outliers in price and odometer.
•	Restricting to modern vehicles (year ≥ 1994, age ≤ 30).
•	Engineering age as a clearer predictor than year.
•	Dropping low-value or high-missing features (e.g., size, paint_color).
•	Filling missing numeric values with medians and categorical values with "missing".
•	Encoding categoricals with sparse one-hot encoding using a ColumnTransformer.
This produced a clean, memory-efficient dataset suitable for regression modeling.

Modeling (Brief)
We split the data into training and testing sets and trained several regression models, including baseline Linear Regression and Ridge Regression with L2 regularization.
Using sparse one-hot encoding and numeric passthrough, we tuned Ridge and evaluated models with RMSE and R².
The best model achieved RMSE ≈ $11.7k and R² ≈ 0.20.

Evaluation (Brief)
Although the dataset is noisy and lacks detailed condition/trim data, the model meaningfully captures major price drivers.
An R² of ~0.20 is consistent with expectations for open used-car listings.
The model reveals clear patterns: newer cars, lower mileage, strong manufacturers, SUVs/trucks, automatic transmission, and clean titles all increase predicted price.
The model is sufficiently accurate to provide insight, though not to set precise prices.

Deployment (Brief)
For dealership use, we summarize the key findings:
•	Price is primarily driven by age, mileage, vehicle type, brand, drive type, and condition/title status.
•	Dealers should prioritize newer, lower-mileage, SUV/truck inventory from high-retention brands.
•	The model can serve as a pricing reference and help guide inventory strategy.
