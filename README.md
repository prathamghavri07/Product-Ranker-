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

