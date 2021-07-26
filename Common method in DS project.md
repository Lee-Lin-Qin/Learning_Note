## Split Train/Test/Validation
https://towardsdatascience.com/how-to-split-data-into-three-sets-train-validation-and-test-and-why-e50d22d3e54c
Split randomly or Split by time with the code



https://www.kaggle.com/nextbigwhat/train-valid-test-split-instead-of-train-test-split

Split dataset into train/test/validation dataset with 
	1) Scikit learn

* Let's say we want to split the data in 80:10:10 for train:valid:test dataset
from sklearn.model_selection import train_test_split
train_size=0.8
X = df.drop(columns = ['SalePrice']).copy()
y = df['SalePrice']
** In the first step we will split the data in training and remaining dataset
X_train, X_rem, y_train, y_rem = train_test_split(X,y, train_size=0.8)
# Now since we want the valid and test size to be equal (10% each of overall data). 
# we have to define valid_size=0.5 (that is 50% of remaining data)
test_size = 0.5
X_valid, X_test, y_valid, y_test = train_test_split(X_rem,y_rem, test_size=0.5)



	2) from fast_ml.model_development import train_valid_test_split
	



import pandas as pd	
	df = pd.read_csv('/kaggle/input/bluebook-for-bulldozers/TrainAndValid.csv', parse_dates=['saledate'], low_memory=False)
	from fast_ml.model_development import train_valid_test_split
	X_train, y_train, X_valid, y_valid, X_test, y_test = train_valid_test_split(df, target = 'SalePrice', 
	train_size=0.8, valid_size=0.1, test_size=0.1)
	print(X_train.shape), print(y_train.shape)
	print(X_valid.shape), print(y_valid.shape)
	print(X_test.shape), print(y_test.shape)
![image](https://user-images.githubusercontent.com/58452489/126985020-c96e1d82-9026-43da-bb27-052084e7c636.png)
