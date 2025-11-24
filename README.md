# Used-Car-Fantasies-
A concise ML project analyzing a 426K-row used car dataset through cleaning, feature engineering, EDA, and Ridge regression to identify what drives used car prices.
Business Understanding:
The goal of this project is to understand what drives used car prices so dealers can price and stock inventory more effectively. From a data perspective, the task involves building a supervised regression model that predicts price from vehicle attributes such as age, mileage, manufacturer, type, drivetrain, fuel type, and condition, and then analyzing which features have the strongest influence on price.

Data Understanding:
I explored the dataset by reviewing its structure and datatypes, checking missing values across all fields, examining the distributions of key variables like price, year, odometer, and engineered age, and identifying extreme outliers such as multi-million-dollar prices and cars with 10-million-mile odometer readings.

Data Preparation:
The dataset was cleaned and prepared by removing extreme outliers in price and odometer, restricting the dataset to modern vehicles (year 1994 or newer, age 30 years or less), engineering age as a primary predictor, dropping features with heavy missingness or little predictive value (such as size and paint color), filling numeric missing values with medians and categorical missing values with the label “missing,” and encoding categorical variables with sparse one-hot encoding through a ColumnTransformer. This produced a clean and efficient dataset for modeling.

Modeling:
The cleaned dataset was split into training and testing subsets, and several regression models were trained, including basic Linear Regression and Ridge Regression with L2 regularization. Using sparse one-hot encoding for categoricals and numeric passthrough for continuous features, the Ridge model achieved the best results with an RMSE of approximately $11,700 and an R² of about 0.20.

Evaluation:
Even though the dataset is noisy and lacks detailed trim or condition-level features, the model successfully identifies major factors that influence used car prices. An R² around 0.20 is typical for publicly scraped used-car datasets. The model shows clear trends: newer vehicles, lower mileage, stronger manufacturers, SUVs and trucks, automatic transmissions, and clean titles are associated with higher prices. The model is reliable for insights, though not precise enough for exact price prediction.

Deployment:
The final findings for dealership users highlight that age, mileage, vehicle type, brand, drive type, and title or condition status are the main drivers of price. Dealers should focus on acquiring newer, lower-mileage SUVs and trucks from high-retention brands. The model can be used as a pricing reference tool and as support for inventory strategy decisions.
