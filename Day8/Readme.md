
# Date: 16/09/2024
### Session 8: Applications
-------------------------------------------------
### Topics: 	
	-Applications
	-Time series application
	-Recommendation systems
	-Hadoop
### Data Science applications:
----------------------------
    -Case study:
    1. Import the data
    2. Describe the data
    3. Check missing values
    4. Handle the missing values
    5. Perform EDA : generate some graphs to analyse the content in dataset.
    6. Perform preprocessing by applying standscalar
    7. Split data into train and test
    8. Apply the model : Logistic REgression, DT, RF, Ensemble learning
    9. Prediction
    10. Check accuracy of the model

### Time series applications:
--------------------------
    -A time series data is a sequence of data points recorded at specific time intervals.
    -Time series: Years, month day, week , quater, sec, minutes and hrs.
    
    -Components of time series data
    	-1.Trend: The long term movement in the data.
    	-2.Seasonality: Regular pattern recurring at specific period.
    	-3.Cyclical:Long term fluctuation due to economic cycles.
    	-4.Irregulation/Noise:Random variations due to economic cycles.
	
### Types of Time series:
	-1. Univariate : A single variable recorded over time.
	-2. Multivariate: Multiple variable recorded over time.
	
### Time series Smoothing:
	-Smoothing techniques help in identifying trends by reducing noise.
	
### Time Series Model:
    -ARIMA Model:
    	-ARIMA (AutoRegressive Itegrated Moving Average)
    	-It is one of the most popular models for time series forecasting.
    			AR			 +		 	I 			+ 		MA
    		AR(Autoregressive)		I (Integrated)		MA(Moving Average)

### Model Evaluation:
	-MAE: MEan Absolute Error
	-MSE: Mean Squared Error
	-RMSE : Root Mean Squared Error
	-MAPE : Mean Absolute Percentage Error
		
		
    Forecasting:Once model is built and validated, it can be used for forecasting future values.

		
		
### Recommender Systems:
--------------------
    -A recommender system is a type of information filtering system that predicts and suggest items(or products such as movies, music, or article) that a user might prefer or find useful.
    
    Purpose: To assist users in finding items that are relavant to their interst and preferences, ehancing their experience by making personalized suggestions.
    
    Applications:
    -E-commerce
    -Streming services
    -Social media
    -News website

### Types of Recommender system:
------------------------------
    1.Collaborative Filtering:
    	-Concept: Predicts user preference based on the preferences of other users.
    	-Types: 
    		-a.User based collaborative Filtering
    			-1.Find similarity betwen user and the target user.
    			-2.Predict missing rating using weighted average based on rating from similar user.
    			
    		-b.Item-based collaborative Filtering
    			-1.Calculate item-to-item similarity.
    			-2. Predict ratings based on the weighted sum of rating of similar items previously rated by the user.
    
    
    2.Content based Filtering:
    	-Concept: Recommends items similar to those a user has liked based on item attributes.
    	-Steps:
    		1. Represent items and user in a feature space
    		2.Compute similarity using dot product or other similarity measures.
    		3.Make recommendations based on the highest similarity scores.
    
    
    3. Hybrid systems:
    	-concepts: combines collaborative ans content based methods for more accurate recommendations
    
    Working principle:
    --------------------
    -USer profile
    -Item products
    -Algorithms
    -Prediction and Ranking

### Importance of Recommendation system:
-------------------------------------
    1. Enhancing user experience
    2. Increase user engagement
    3. Improve the decision-making
    4. Boosted revenue


# Hadoop:
-------
    -Hadoop is an open-source framework designed for distributed storage and processing of large data sets acros  clusters of computers using simple programming methods.
    -It allows for scalable and fault-tolerant processing of data by utilizing a cluster of machines to work on data in parallel.


### Key features:
-------------
    1.scalability: Easily scale from a single server to thousands of nodes.
    2.Fault tolerance: Replicates the data across multiple nodes to ensure availability.
    3.Cost-effective: Utilizes commodity harware to reduce costs.
    4.Distributed programming: Processing data in parallel, enhancing speed and efficiency.

### Hadoop Framework:
-----------------
    A.Core Module:
    	1.Hadoop common:
    		-Provides the common utilities and libraries needed by other Hadoop module.
    		-Includes utilities for managing file systems, serialization, and Hadoop commands.
    		-Ensures interoperability among different Hadoop componenets.
    		
    	2. HAdoop YARN(Yet Another Resource Negotiater):
    		-Manages and schedules resources in the HAdoop cluster.
    		-Componenets
    			-ResourceManager: Manages cluster resources and job scheduling
    			-NodeManager:Manages resources and runs taks on individual nodes.
    			-ApplicationManager:Manages the execution of individual applications.
    		-Function: allocates resources dynamically, optimizes resource usage.
    
    	3.Hadoop Distributed File System (HDFS):
    		-A distributed file system designed to store large files across multiple nodes.
    		-Components
    			-NameNode:Manages the file system namespace and metadata.
    			-DataNode:Stores the actual data blocks.
    		-Function :Provide high throughput access to application data, ensures fault tolerance by replicating data
    		
    	4.Hadoop MApReduce:
    		-A programming model and processing engine for parallel computation of large datasets.
    		-Componenets
    			-Map: Processes input data into intermediate key-value pair.
    			-Reduce: Aggregate and process intermediate data to produce final results.
    		-Function: Enables distributed data processing by dividing tasks into smaller chunks.
    
    
    B. Architecture:
    -Master-Slave Architecture:
    	-MasterNode: Handles management and coordination tasks.
    	-SlaveNode: Performs the actual data processing and storage.
    	
    C. Environmental setup:
    	1.Installation:
    		-Download Hadoop binaries fromthe Apache website
    		-Extract the binaries and configure environment variable
    		-Configure core-site.xml, hdfs-site.xml,..
    		
    	2.Configurations:
    		-Core site configuration
    		-HDFS Confguration
    		-MapReduce Configurations
    		-YARN Configuration
    		
    	3.Start services:
    		-use command start-dfs.sh and start-yarn.sh 
    		
    
    D:Operation Modes:
    	-Local Mode
    	-Pseudo Mode
    	-Cluster mode
    	
    
