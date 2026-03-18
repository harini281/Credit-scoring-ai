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



   
