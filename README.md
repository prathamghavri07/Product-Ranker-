## Understanding the Problem statement 
We need to build a CTR ranker , which ranks based on search term and city level from the data set. The User collection process is multiple users search a query and based on it data is stored in data lakes of Zepto containing CTR , cosine similarity ,Product name and much more .

Query ---> Predicted category & subcategory ---->Product shown & Data --> CTR & is-clicked.

The target variable is “is_clicked” as mentioned in document

## Libraries 
●	Pandas 
●	Matplotlib
●	Seaborn
●	Plotly
●	Sklearn(xgb,train_test_split,metrics)

## Data Loading 
●	Set up is on Google Collab
●	Uploading the csv file

## Data Cleaning
- Null values (less than 20% missing) are imputed, and duplicates are checked and removed.
- Checking for duplicates
- Replacing Null categorical values with others or None , as the missing values are very low in percentage wrt to the data ,hence we impute it and using other as tag justifies as the feature specification is not known.
- Imputed_columns =’brand_name, category_name, subcategory_name, Product_name’

## EDA (Insights)
- Combo ,Zepto and much are the top searched items
- Munchies ,Sweet Craving and home essential categories are most searched categories
- Click through rate on the platform is very low averaging near .1 for most features assigned,CTR of last 30 days (PQC) lies near 0 and above 1 % only 32 searches for that query in given cities exist
- CTR (PxQxC) for 30 days and 7 days are correlated positively
- Popular queries ,product suggestions are clicked more often than tail query type

Data Preprocessing
Using Data Transformations (Normalizing & Encoding Categorical variables) , Feature engineering and Feature Selection 

Dropping Leaky Feature
We need to drop these features as they contain information about the target variable 
●	Total_clicks is a leaky feature as it directly predicts is_clicked column
●	Query_products_clicks_last_30_days also suggest about is_clicked

Dropping highly correlated features
●	Plotting correlation matrix between numerical columns and then identifying corr_val>.7 
●	When columns are highly correlated issues like Multicollinearity , Redundancies come into account

Standardizing Numerical Columns 
●	Using Standard Scaler to normalizing the numerical columns 
●	The StandardScaler is used to standardize features by removing the mean and scaling to unit variance

Encoding for Categorical Variables
We had options of One hot encoding , Target encoding , label encoding and many more
●	One hot encoding (Rejected) - High dimensionality is the main issue which will lead to high computational power and high ram requirement 
●	Label Encoding(Rejected) - The values when label encoded will suggest for example search_query_1> search_query_2 where as this might not be true 
●	Target encoding(accepted) -It reduces dimensionality of the data ,It is highly Cardinal feature as it summarizes one statistical value making it more informative
