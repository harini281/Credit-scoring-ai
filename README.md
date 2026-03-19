# Credit-scoring-ai
A machine learning project to predict the likelihood of loan default using credit data. Includes data preprocessing, model training with Random Forest, evaluation metrics, and visualizations. Designed for financial risk analysis and credit decision support.

1)Import Libraries
First, I import the necessary libraries:

    Pandas: I use it for data manipulation and analysis.

    NumPy: I use it for numerical operations and handling arrays.

2)Load Dataset
I use a real dataset called investment_survey.csv (uploaded in the GitHub repository). To load the data, I use:

    df = pd.read_csv("investment_survey.csv")

Here, df stores the dataset as a DataFrame.

3)Explore Data

    I use df.head() to display the first 5 rows and check that the data is loaded correctly.

    I use df.info() to get details about the dataset, such as column names, data types, and non-null     counts.

4)Check for Missing Values
      I check for missing values using:

         df.isnull().sum()

         This shows the number of missing values in each column.

5)Drop Unnecessary Columns

    If a column is undefined or not needed, I remove it using:

    df.drop(columns=["column_name"], inplace=True)

6)Handle Categorical Data

    I store categorical columns in an array for processing.

    I apply One-Hot Encoding to convert categorical values into binary values (0 and 1).
    Example: For a column with values x, y, z:

x → [1, 0, 0]

y → [0, 1, 0]

z → [0, 0, 1]

-----To avoid redundancy, I use drop_first=True in pd.get_dummies().

7)Verify Encoding

         I use df.head() again to check that the categorical columns are correctly converted to               binary format.

     
     
![images](https://github.com/user-attachments/assets/912a3049-1c76-46bb-97db-fcb3703c86ed)

8)Split Features and Target

    I separate the dataset into features (X) and target (y).

    I check which columns exist in the dataset using df.columns.

    I assume the target column is Annual Income. I drop this column from X to use it only in y.

    I verify the number of columns in X using X.shape.

9)Train-Test Split

    I split the data into training and testing sets using train_test_split from scikit-learn:

     from sklearn.model_selection import train_test_split
     X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

10) I use 80% of the data for training and 20% for testing.

11)Create the Model

       I use a Random Forest Regressor to predict Annual Income:

     from sklearn.ensemble import RandomForestRegressor
      model = RandomForestRegressor(n_estimators=100, random_state=42)

    n_estimators=100 defines the number of trees in the forest.

    random_state=42 ensures reproducibility.

12)Train the Model

    I train the model to learn patterns in the data using:

    model.fit(X_train, y_train)

13)Make Predictions

    I predict the target for the test set using:

    y_pred = model.predict(X_test)

14)Evaluate the Model

    I evaluate the model using several metrics:

Mean Absolute Error (MAE) – average absolute difference between predicted and actual values.

Mean Squared Error (MSE) – penalizes larger errors more heavily.

R² Score – explains how much variation in the target is explained by the model.

My model achieved an R² of 0.62, meaning it explains 62% of the variation in Annual Income.
   
