# Machine-learning-Linear-Logistic


**Abstract** 

<p align="justify">
In this project, we aim to implement linear and logistic regression for 2 UCI datasets including the Energy Efficiency dataset and the Qualitative Bankruptcy dataset. The first data set aims to predict both heating and cooling load with linear regression and the second dataset focuses on predicting bankruptcy based on different categorical factors. For the first data set the data cleaning and feature selection process has been implemented and the linear regression with a closed-form solution was designed to predict two predictive variables with the R-squared score of 0.89 and 0.85 for Heating and Cooling load respectively. Moreover, the mini-batch stochastic gradient descent with different sizes of batch (8, 16, 32, 64, 128) with different learning rates (0.01, 0.001, 0.0001) has been investigated and the results showed that the minibatch of 32 with learning rate 0.01 had the closest weights to the closed-form solution and was the best in terms of speed of convergence and the MSE . The second dataset was used to predict bankruptcy and the 6 explanatory variables were categorical. After preprocessing the data, the logistic regression with GD  and mini-batch stochastic GD has been implemented with different sizes of batches (8, 16, 32, 64, 128) with different learning rates (0.001, 0.01, 0.05, 0.1). According to the confusion matrix, the accuracy of the GD logistic regression is 0.98 and the best result of the SGD based on the confusion matrix measurement is a learning rate of 0.05 with a mini-batch size of 16. 

**1.	Introduction**

<p align="justify">
This study investigates the implementation of linear and logistic regression on two data sets with two numerical and one binary variable, respectively. The first data set entitled “Energy Efficiency” has 8 explanatory variables and two dependent variables to be predicted, cooling and heating load. In this project, the aim is to compare the linear regression’s closed-form solution with the stochastic mini-batch gradient descent linear regression and compare the performance and weights to reach the accurate prediction of the response variable, regarding different batch sizes and learning rates. The data set has been introduced by Tsanas and Xifara 2012 [1], to compare a classical linear regression approach with a nonlinear non-parametric method, random forests, to estimate Heating and cooling load. In 2022, Senarathne et al. [2] used Bayesian Network to recognize the most important factors affecting HL (heating load) and CL (cooling load). They used the Bayesian network structure; Based on their results, the Tabu search performed best and they found that a decrease in building height results in the high energy efficiency. Using the naïve Bayes classifier, Prasetiyo and Muslim [3] found the top four features affecting heating and cooling load which are overall height, relative compactness, wall area, and glazing area. In this study correlation and threshold analysis with consideration of univariate k-best algorithms are implemented to find the best features; both a closed-form and mini-batch gradient descent linear regression are utilized and compared to predict HL and CL and find the optimized weights. To better understand the model and select the best optimization parameters, a set of batch sizes and learning rates are tested and compared. 
The second dataset entitled “Qualitative Bankruptcy” has 6 features with a binary target to predict if the company goes bankrupt or nonbankrupt based on those six risk factors [4]. In this project, we would like to use logistic regression with gradient descent in the different learning rates, Mini-batch stochastic logistic regression. Aruldoss in 2014 demonstrated that in Bankruptcy the most proposed method is neural networks. On the same dataset, they illustrate how to find the relationship between risk factors, and they evaluate the model by measuring the t-test and F-test. Recent research on the same dataset was proposed by Uthayakumar in 2020. They applied Swarm intelligence which outperforms previous classifiers namely Logistic Regression, Multilayer Perceptron, and Random Forest in terms of various performance analysis factors [5]. 

**2.	Datasets and Preprocessing**


**2-1 First dataset: Energy Efficiency Dataset**

<p align="justify">
This dataset was created by Angeliki Xifara, a Civil Engineer, and was later developed by Athanasios Tsanas from the Oxford Centre for Industrial and Applied Mathematics, University of Oxford, UK. Energy efficiency analysis was conducted on 12 different building shapes that have been simulated in Ecotect. The buildings differ according to different attributes. They vary with respect to the overall height of the building, the glazing area, the surface area, and orientation, among other things. This dataset houses a total of 768 observations and 8 features (X1 Relative Compactness, X2 Surface Area, X3 Wall Area, X4 Roof Area, X5 Overall Height, X6 Orientation, X7 Glazing Area, X8 Glazing Area Distribution, with the goal of predicting two numerical response variables (Y1 Heating Load, Y2 Cooling Load).
