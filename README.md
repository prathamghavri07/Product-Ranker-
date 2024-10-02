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
