# Predicting House Prices in King County Washington State

-----------

I started working on Predicting King County House prices to gain experience
by working on a real world dataset. I have also been reading Hands-On Machine 
Learning with Scikit-Learn and TensorFlow. Chapter 2 along with Appendix B 
offer great starting points on how to start a project from start to finish. 
	
This README.md file will contain my personal notes, techniques I used, where
I struggled and the lessons learned at the end.
	
I started the project during Spring semester of 2020.
	
	
<br> 


### Machine Learning Project Checklist
		
------

The following are general steps that I feel can help with any ML project. 

#####	1. Think about the big picture as you frame the problem
			
	A. Describe the objective of the project. If needed in business terms.
	B. How will my model/program be used?
	C. Are there any current solutions?
	D. When framing, think about what will work best, supervised, unsupervised, 
	   online/offline
	E. Very important, how will the performance of the model be measured?
	F. Does the performance measure align with the objective described above? 
	G. Define the worst case performance that is tolerated.
	H. Scale down the problem, and think about ways that you can solve the 
	   problem manually.

#####	2. Download the data and always work with a copy of it.
	A. List the amount of data needed.
	B. Document where the data came from.
	C. Do you need permission to use the data? If so, ask for access.
	D. Download the data
	E. If needed convert the data to a format that makes it easy to work with.
	   For example, DataFrame using Pandas or NumPy array, matrices. The objective
	   is not to change the data but make it easier to work with.
	F. If there is personal or sensitive information, block it or delete it.
	G. Take a look at the type of data and the size.
	I. Make a test set and set a copy aside in case you need it.
		
##### 3. Take a look at the data and the different attributes
	C. Use the copy of the data to explore it. 
	D. As you explore it, Jupyter Notebooks are a great tool to keep track of the
	   data you are looking at. 
	E. Make sure to look at every attribute in the data and some basic statistics
	   		
	   		For example:
							- Type(integer, decimal, strings, categorical)
							- Keep track of missing data
							- Look for noisy data (outliers, rounding errors, stochastic) 
							- What can be useful for the model?
							- What features may not work?
							- Look for the type of distribution (uniform, gaussian)
	F. Plot the data, visualize it with histograms, catplot, bar charts, use seaborn
	   or matplotlib
	G. Look for correlations between any of the attributes and see if maybe we can
	   combine them into one to reduce the complexity or dimensions of the model.
	H. Are there attributes that you don't understand? 
	I. Document my finding. What did I learn about the data.

	
#####	4. Prepare the data before applying a ML algorithm
	A. Once I have identified if I am going to transform any of the attributes
	   write functions that will do that form me or use NumPy.
	  	- Function make it easy to transform new data.
	  	- It makes the program look clean
	  	- Faster preparation of new instances
	B. Clean the data. Remove outliers, missing values with zero, mean, or drop them.
	C. Select the features for the model.
	D. May need to do some feature engineering.
		
			For example:
							- Discretize continuous features
							- Decompose features like categorical, data and time
							- Transform features, log, sqrt, ^2
							- Combine features if possible
	E. Feature scaling: Standardize or normalize features 
	
#####	5. Try different models and pick the best ones
	A. Try smaller training sets to use different types of model. Keep in mind that
	   Large neural nets or random forests my not give good results due to their
	   complexity.
	B. Try to automate the selection as much as possible
	C. Compare their performance using N-fold cross-validation and compute the mean
	   standard deviation of the performance measure on the N folds.
	D. Look at the variables that are most significant to the model.
	E. Does the model make any errors? If so why and can they be improved?
	F. Try different attributes.
	G. Do these steps until you have identified the best model and best attributes.
	I. Select the best performing models, top 5 that make different types of errors. 
	
#####	6. Continue to fine tune the models, add documentation 
	A. Fine tune the hyperparameters using cross-validation.
		- The attributes that I transformed earlier, treat them as hyperparameters. 
		- What happens when I replace missing values, or drop them.
		- If training takes a long time try a Bayesian optimization approach
	B. Try using an ensemble method. Combing model is sometimes better than running 
	   them individually. 
	C. Once I feel that my model is doing good. Measure the performance on the test 
	   set to estimate the generalization error (out of sample error).
	
#####	7. Make it easy for people to use or learn from your work
	A. Make sure do add great documentation. 
	B. Make the program easy to execute and have user interaction.

#####	8. Present my solution. Jupyter Notebook or a small paper. 
	A. Document every step of the way
	B. Create a presentation or small paper. Highlight the big picture.
	C. Explain why my solution achieves the objective described in step 1.
	D. Describe what worked, what didn't, are there any limitation to the mode?
	E. Use easy to memorize language or visuals in presentation. 


#####	Difficulties and Lessons Learned
	This project did not present too many difficulties. There was no missing
	data, I did not have any null values. However, the model did not do a
	good job of predicting the more expensive homes, as can been seen from
	the price distribution in the box plot. There are a lot of black dots
	outside of the whiskers which is the noise. 
	
	Something that I confirmed from doing this project was the importance of
	scaling the data. I did not scale the first linear model I built and the
	r_square and RMSE confirmed that the model was not given great results.
	I then used a MinMaxScaler and a StandardScaler and model showed a 
	significant improvement, by almost 20%. 

	For future projects make sure to try different methods to scale the data
	if needed and make sure to transform the selected feautures to reduce 
	complexity in the model and improve on the RMSE and r_squared values.
	For example, for this project I encode categorical data that couldn't be
	compared to each other like zip codes.
  
