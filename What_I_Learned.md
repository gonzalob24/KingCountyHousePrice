# Take aways to apply to other projects

-----------

This is a short summary of the biggest things I learned form doing this small project. 
	
	
<br> 


### Data Preprocessing
		
------

I first created a linear model without preprocsssing the data and the results were not as good as they could have been.

I then proprocessed the data by looking for nan values, categorical features, continous features and any noise like outliers that can affect the learning alogorithm.

To process nan values I have learned to use a simple imputer from sklearn. Categorical data can be processed with pandas using onehot encoding pd.get_dummies or from sklearn using Label Encoder or One Hot Encode. For continuous data, it can be scaled using a MinMaxScaler from sklearn.

Getting into the habbit of processing data is beneficial when building machine learnign algorithms. 

 

#####	xxxxxxx
			
	A.xxxxxxx