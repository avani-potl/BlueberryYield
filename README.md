# BlueberryYield
Optimizing blueberry cultivation using data analysis and machine learning techniques. Integrated diverse data sources (soil, weather, irrigation, pests) to boost yield, quality, and disease prevention.


1. Feature Separation
After loading the data, the features (input variables) and the target variable (crop yield) are separated. The X DataFrame contains all the feature columns except for the 'yield' column, which is extracted and stored in the y Series.

2. Feature Selection
Feature selection is a crucial step to choose the most relevant features that have the greatest impact on predicting the target variable. In this code, the SelectKBest method from the sklearn.feature_selection module is employed. It selects the top k features based on their correlation with the target variable using the f_regression scoring method.

3. Data Splitting
To evaluate the model's performance and prevent overfitting, the data is split into training and validation sets using the train_test_split function from sklearn.model_selection. The training set is used to train the model, while the validation set helps assess its performance on unseen data.

4. Random Forest Model Definition
A Random Forest Regressor model is defined using the RandomForestRegressor class from sklearn.ensemble. This model is a collection of decision trees that work together to make predictions. The initial model is created with default hyperparameters.

5. Hyperparameter Tuning
Hyperparameters are settings that influence a model's learning process. The RandomizedSearchCV class from sklearn.model_selection is utilized for hyperparameter tuning. It performs a randomized search over a predefined parameter grid (param_grid) to find the best combination of hyperparameters that minimizes the mean absolute error (MAE) on the validation set.

6. Model Evaluation
The performance of the best model found during hyperparameter tuning is evaluated on the validation set. Predictions are made using this model, and the mean absolute error (MAE) between the actual crop yields (y_val) and the predicted yields is calculated and printed. A lower MAE indicates better model performance.

7. Test Data Loading
The code loads a separate test dataset using the same CSV file reading technique. This dataset likely contains features similar to those in the training data but without the 'yield' column.

8. Feature Selection for Test Data
Similar to the training data, feature selection is performed on the test data using the same selector object created earlier. This ensures that the same selected features are used for making predictions on the test data.

9. Predictions
The best model from the hyperparameter tuning process is used to predict crop yields on the test data. The predict method of the model is applied to the selected test features (X_test_selected), generating a set of yield predictions.

10. Output Generation
A new DataFrame, output, is created to store the test data's IDs along with their corresponding yield predictions. This DataFrame will be used to generate the final CSV output.

**PREDICTIONS ATTACHED**
