# Data-analysis-pandas-
Adult Income Prediction analyzes the Adult dataset to predict if a person earns over $50K. Includes EDA, handling missing values, duplicates, and bivariate analysis. Uses Pandas, NumPy, Seaborn, and Matplotlib. Titanic Survival Analysis explores survival rates based on class, age, and gender with similar EDA techniques.

#Database
- <a href="https://github.com/aryansohani/Data-analysis-pandas-/blob/main/adult.csv">Adult raw data</a>
- <a href="https://github.com/aryansohani/Data-analysis-pandas-/blob/main/train.csv">Titanic dataset</a>

#Questions-
Questions and Answers
1️⃣ How many rows and columns are in the dataset?
Answer: The dataset has data.shape[0] rows and data.shape[1] columns.

2️⃣ What are the data types of each column?
Answer:

data.info() provides an overview of column data types.

Most columns are categorical, while some are numerical.

3️⃣ Are there missing values in the dataset?
Answer: Yes, data.isnull().sum() shows missing values in workclass, occupation, and native-country.

4️⃣ How did we handle missing values?
Answer:

Replaced "?" with NaN using replace().

Dropped missing values using dropna().

5️⃣ Are there duplicate rows?
Answer:

Checked with data.duplicated().any().

Removed duplicates using data.drop_duplicates(inplace=True).

6️⃣ What is the distribution of age?
Answer:

Summary: data['age'].describe().

Visualization: data['age'].hist().

7️⃣ How many people have age between 17 and 48?
Answer:

sum(data['age'].between(17,48)) gives the count.

8️⃣ What is the most common workclass?
Answer:

data['workclass'].value_counts() shows "Private" is the most common.

Visualized with sns.countplot(x='workclass', data=data).

9️⃣ How many people have a Bachelor's or Master's degree?
Answer:

sum(data['education'].isin(['Bachelors','Masters'])) gives the count.

🔟 What is the relationship between income and age?
Answer:

Boxplot: sns.boxplot(x='income', y='age', data=data).

Older individuals tend to earn more.

1️⃣1️⃣ What is the income distribution?
Answer:

sns.countplot(x='income', data=data).

Majority of people earn <=50K.

1️⃣2️⃣ Replaced categorical income values
Answer:

data.replace(to_replace=['<=50K', '>50K'], value=[0,1], inplace=True).
