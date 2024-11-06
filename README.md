# Titanic - Machine Learning

Libraries and Setup:

You import essential libraries such as pandas, numpy, matplotlib, seaborn, and xgboost, along with sklearn for various machine learning tasks.
You suppress warnings to avoid cluttering the output.
The Google Colab drive is mounted to load the dataset.

Data Preprocessing:

Loading Data:
The Titanic train and test datasets are loaded into df_train and df_test respectively.
Missing Data Handling:

For df_train, missing 'Age' values are filled using the median age grouped by the 'Survived' feature.
For df_test, missing 'Age' is filled using the median of the 'Age' grouped by 'Sex'. Missing 'Fare' values are filled with the median.
Dropping Irrelevant Features:
Unnecessary columns such as Ticket, Cabin, Embarked, and Name are dropped as they are not needed for training.
Encoding Categorical Features:
The 'Sex' column is mapped to binary values (0 for male, 1 for female).

Data Exploration:

A boxplot of the Fare feature is created to check for outliers.
You define a function outliers_z_scrole to remove outliers in the Fare feature by applying a log transformation and a z-score filter.

Splitting Data:

The Survived column is separated from the features (X), and the data is split into training and validation sets (70% training and 30% validation).

Model Training and Evaluation:

You initialize and train an XGBClassifier model with specified hyperparameters.
The model is evaluated on the validation set using accuracy, classification report, and confusion matrix.

Final Model and Predictions:

The model is retrained on the full training data (df_train_clean) and predictions are made on the test set (df_test).
The predictions are saved into a new CSV file, Titanic_pred_xgb.csv, containing PassengerId and the predicted Survived values.

Points for Improvement or Customization:

Hyperparameter Tuning: You might want to explore hyperparameter optimization (using grid search or random search) to improve the model.
Feature Engineering: You could try creating new features (e.g., family size from SibSp and Parch) that might improve the model.
Validation Strategy: Instead of a single train/validation split, you could also use cross-validation for better model evaluation.
