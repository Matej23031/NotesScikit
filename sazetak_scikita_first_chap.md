#BatchLearning
	-learning from a stream of data
	-first supervised then unsupervised 
	-"offline learning"
	-when inputing new data you have to train it from scratch with new inputs !DAFUQ?
	- not a reactive solution
	- better option in given cases is to use algorithms that are capable of incremental learning
#online_learning
	-run and learn
	-feeding the system with 'mini batches'
	-e.g. stock prices
	-not dependant on already learned data
	- out-of-core learning the alrgorithm laod part of the dat, runs a trainign step on
	   that data and repeats the process until it has run on all of the data
	    synonym incremental learning
	- learning rate  (adaptibility to learning data)
	- noise in data (outliers)
	-e.g. using an anomaly detection algorithms to reduce false feeding
#instance_based_versus_model_based_learning
	- two main approaches to generalization (instance based learning, model based learning)
	- copy for code
	#instance_based 
		-the most trivial form of learning
		-system learning the examples by heart and then generalizes tto new cases by comparing them to the learned examples
		-using a similarity measure
		-fintess function (utility function)
		-linear regression fiting the line to best fit the given data
		-the algorithm find the optimal parameter values
		#k_nearest_neighbours_regression
			replacing the linear regression model with the k-nearest neihgbours regression 
			- if something else was needed we need to use polynomial regression model
			
		
```python
import sklearn.linear_model
model = sklearn.linera_model.LinearRegression()
(linear regression)
import sklearn.neighbours
model = sklearn.neighbors.KNeighborsRegressor(n_neighbors)
```

#main challenges of machine learning
	- bad(algorithm/data)
	#insufficient quantity of training data
		- "The Unreasonable Effectiveness of Data"
		- ambiguity of both simple and complex models related to data input and understanding (done on natural language disambiguation)
	#nonrepresentative_training_Data
		- SAMPLE NOISE - nonrepresentative data sa a result of chance 
			-[sampling bias check (1936. Landon against Roosevelt)
		-generalizing in machine learning is overfitting
		-constraining a model to make it simpler and reduce the risk of overfitting
			- its called "regularization"
			- **degrees of freedom** 
				- tweaking bothe the height and the slope
				=
		#UNDERFITTING
			- model too simple to learn underlying structure of the data 
			- selecting a more powerful model
			- feeding better features to the learning algorithm
			- reducing the constraints on the model
	#Hyperparameter_tunning_and_model_selection 
		- train both and see what swims 
			- compare how well they generalize
		- **holdout validation**
			- simply hold out part of the training set to evaluate several candidate models and select the best one 
			- **validaiton set**
				- dev set
				- you train several models on the validation set
				- afterward you train the best model on the full training set
				- generalization error on the last model
				- cross validation - using small validation sets
				- training time is multiplied by the number of validation sets
				