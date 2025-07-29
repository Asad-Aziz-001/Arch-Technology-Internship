# Arch-Technology-Internship
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# **Task 1: California House prediction**

**📌 1️⃣ Data Preparation**
You loaded the California housing test dataset from CSV.

Then you selected features:

longitude and latitude (as a rough proxy for location)

total_rooms (as a measure of house size)

population (as a measure of neighborhood density)

The target is median_house_value.

Next, you split the data into training and testing sets to evaluate how well the models generalize to unseen data.

**📌 2️⃣ Random Forest Regression**
Random Forest builds many decision trees on random subsets of your data and then averages their results.

This makes it robust to overfitting and generally works well on tabular data.

Random Forest captures non-linear patterns, such as:

“houses with many rooms tend to have higher prices, but only up to a certain population threshold.”
which linear regression cannot model directly.

fit the Random Forest on your training data

predicted house prices on the test data

evaluated it using:

RMSE (measures prediction error; lower is better)

R² (explains how much variance is captured; closer to 1 is better)

**📌 3️⃣ Linear Regression**
Linear Regression tries to fit a single straight plane across your data:

It is simpler, faster, but less flexible if relationships are more complex.

fit the Linear Regression model on the same training data

predicted house prices on the test data

evaluated the same metrics (RMSE, R²)

**📌 4️⃣ Comparison**
You compared both models using:

✅ RMSE:

Random Forest error was much lower (≈63k vs 90k)
→ better prediction accuracy

✅ R²:

Random Forest explained 68% of the variation

Linear Regression explained only 36%
→ better fit to the data

**📌 5️⃣ Visualization**
A side-by-side scatter plot showed:

points closer to the diagonal line (better predictions) for Random Forest

more scatter and larger errors for Linear Regression

A bar graph compared their RMSE and R² side by side, making the difference more obvious.

Another bar graph compared:

Random Forest feature importances (nonlinear contribution)

Linear Regression coefficients (linear weights)
so you could see which features each model values more.

📌 Why Random Forest wins here?
👉 Random Forest:

handles non-linear relationships

is robust to irrelevant or weakly correlated features

works well even with unscaled data

👉 Linear Regression:

assumes a perfectly linear relationship

cannot handle feature interactions or thresholds
(like “more rooms help, but only in medium-populated areas”)

**✅ In simple words**

You trained two different models

Compared their errors and explained variance

Visualized their results

Random Forest did a better job on your chosen features

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# **Task 2: Iris Flower Classification🌸**

**📁 1. Data Preparation and Loading**

A ZIP file containing the Iris dataset CSV (IRIS.csv) was uploaded to Google Colab.

It was extracted and inspected to confirm that the file was successfully loaded.

The data was loaded into a DataFrame for analysis.

**🔍 2. Data Inspection**

Preview of the dataset showed 5 columns:

sepal_length, sepal_width, petal_length, petal_width (numerical)

species (categorical target)

Missing values check confirmed that the dataset has no nulls.

Column inspection ensured all necessary features are available.

**🧹 3. Preprocessing**

If an unnecessary column like Id was present, it would be dropped.

The target column species (which had flower names like Iris-setosa) was label-encoded into integers (0, 1, 2) for machine learning compatibility.

**📊 4. Exploratory Data Analysis (EDA)**

A correlation heatmap was created to visualize the relationships among features like sepal and petal measurements.

It helps identify which features are strongly related.

**🌳 5. Model 1: Random Forest Classifier**

A Random Forest model was trained:

It uses an ensemble of decision trees to make predictions.

It's good at handling complex patterns and doesn't need much feature scaling.

The data was split into training and testing sets.

The model was trained and tested.

Performance was evaluated using:

Accuracy Score

Classification Report (precision, recall, f1-score)

Confusion Matrix

Result: Accuracy was around 90%.

**📈 6. Model 2: Logistic Regression**

A Logistic Regression model was also trained for comparison:

It's a linear model that performs best when data is linearly separable.

The same training/testing procedure was followed.

Evaluation was done using the same metrics.

Result: Accuracy was around 97%, better than Random Forest on this dataset.

**🎯 7. Training vs. Testing Accuracy**

Training accuracy and testing accuracy were compared to check for overfitting or underfitting.

**📐 8. Decision Boundary Visualization**

For both models, decision boundaries were plotted using only 2 features:

petal length and petal width

This visual comparison shows:

Logistic Regression creates linear decision boundaries.

Random Forest produces nonlinear, complex boundaries, capturing more variance.

**📊 9. Accuracy Comparison**

Both models' accuracies were displayed side-by-side in a bar chart:

Logistic Regression: ~97%

Random Forest: ~90%

**✅ Summary of Insights**

| Aspect                  | Logistic Regression          | Random Forest                    |
| ----------------------- | ---------------------------- | -------------------------------- |
| Accuracy (on this task) | Higher (\~97%)               | Lower (\~90%)                    |
| Decision Boundary       | Linear                       | Nonlinear                        |
| Interpretability        | Easy (based on coefficients) | Harder                           |
| Suitable For            | Simple, linearly separable   | Complex, nonlinear relationships |
