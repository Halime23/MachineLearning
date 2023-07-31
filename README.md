# MachineLearning
Supervised learning and unsupervised learning on the data set.
                                                                 WINE QUALITY TEST
1.	Features: fixed acidity, volatile acidity, citric acid, residual sugar, chlorides, free sulfur dioxide, total sulfur dioxide, density, pH, sulphates, alcohol  
Output: quality

       https://www.kaggle.com/datasets/yasserh/wine-quality-dataset
  	
![image](https://github.com/Halime23/MachineLearning/assets/122736002/eabca6cd-b9a9-41c4-84c9-3cd086a17aff)


 
3.	Correlation: 
Here we try to find a high correlation between inputs and inputs then delete them from our dataset. If correlation is closer to ‘-1’ or ‘1’ this means a high correlation between inputs Also, we try to not delete one of the inputs that have higher correlation with output than the other inputs. We delete the one that has less correlation with output but high correlation with any other input.
            
 ![image](https://github.com/Halime23/MachineLearning/assets/122736002/99d21a4f-5879-4400-a06a-0bd470f35619)

                       If correlation between features >= 0.6 we show them as 1:
		       
 ![image](https://github.com/Halime23/MachineLearning/assets/122736002/351da477-f159-479e-bea6-229088a6f1b4)

So according to our correlation we drop out ‘free sulfur dioxide’ and ‘fixed acidity’ to get more accurate results.

We are going to use these features. (Non-High Correlation Left)

 ![image](https://github.com/Halime23/MachineLearning/assets/122736002/eb565ba3-8194-4727-8e36-3730901773dd)

3.	
a.	Multiple Linear Regression: This table showed us that our predictions were not accurate enough. They are extremely far from each other.
The lower the RMSE, the better a given model can “fit” a dataset 
	
MSE: 0.3476
RMSE: 0.58963
R-squared: 0.40067

You can see from the first table below that it is not linear. The second table shows the relationship between the predictions and the tests.

 ![image](https://github.com/Halime23/MachineLearning/assets/122736002/7172e6a4-adf3-4b9c-ac72-0f5e04c9738a)

 ![image](https://github.com/Halime23/MachineLearning/assets/122736002/cdd4239b-1acb-452b-849e-4297a57c2e91)


 
b.	Polynomial Regression (For 6th degree): We tested the degrees before we found Polynomial Regression. We continued by finding the best degree. We also used this degree for Polynomial Regression. Here are those values and the degree value we chose;
Results for degrees 1,2,3,4,5,6,7, respectively.

MAE		, 	MSE		, 	R2	, 		RMSE
[0.49593512550, 0.4065418896, 0.37337926065, 0.63760637513]
[0.47605689980, 0.3680268217, 0.43274421405, 0.60665214225]
[0.39605073987, 0.2692864501, 0.58493705376, 0.51892817434]
[0.23976114782, 0.1173985485, 0.81904849857, 0.34263471598]
[0.23558879214, 0.0964750063, 0.85129886654, 0.31060425997]
[0.20193675096, 0.0737676517, 0.88629870216, 0.27160200982]
[0.26638014520, 0.1302393048, 0.79925648117, 0.36088683102]

We see that the values begin to decrease for the 7th degree and beyond are starting to decrease and the best value is the 6th degree.

Now, Polynomial Regression: 
       MSE: 0.07377 
       RMSE: 0.27160
       R-squared: 0.88630 //Best one so far 
Our R-squared is high and MSE (Mean Squared Error) is low which means this 6th degree polynomial regression is tried for us.

  ![image](https://github.com/Halime23/MachineLearning/assets/122736002/819cb0e3-ebda-472a-b6f6-64beb2b03082)
  

We can think that Polynomial Regression is close to the correct answers by looking at the RMSE and R-Squared value we calculated and the graph we created. However, using higher order is not an exceptionally reliable way.
Why is higher order not reliable?
Increasing the degree of a polynomial will improve the in-sample fit up to a point. But when you have a data set with n observations, a polynomial of degree n−1 will pass through all of them exactly, and you cannot get any better than that.
However, a high-degree polynomial will do very badly at predicting values out-of-sample, and the terms are exceedingly difficult to interpret. You can try various feature selection or regularization methods, or you can just restrict your attention to quadratic terms unless you have some theory that suggests looking at higher-degree terms.

c.	Logistic Regression: Logistic Regression is not suitable for our dataset because RMSE is too high.
MSE: 0.45105
RMSE: 0.67160
R-squared: 0.22245

![image](https://github.com/Halime23/MachineLearning/assets/122736002/bc722c91-bda6-4af1-8984-f2edfe3ffea7)

 
d.	K-NN: K-NN is not suitable for our dataset because R2 is low and RMSE is too high.
MSE: 0.44337
RMSE: 0.66586
R-squared: 0.23570

![image](https://github.com/Halime23/MachineLearning/assets/122736002/b47d7104-2d38-42f5-9723-bcdd5126d64f)

 
e.	Naive Bayes: Naive Bayes is not suitable for our dataset because R2 is too low and RMSE is too high.
MSE: 0.56643
RMSE: 0.75262
R-squared: 0.02354

![image](https://github.com/Halime23/MachineLearning/assets/122736002/4a94f886-a865-44c9-ab51-933fa11e0fa6)

 
f.	Decision Trees:
MSE: 0.62937
RMSE: 0.79333
R-squared: -0.08495
Minus R-squared: Simply means that the chosen model (with its constraints) fits the data poorly.

 ![image](https://github.com/Halime23/MachineLearning/assets/122736002/1ab3333e-9449-40d3-a076-755b76317938)

g.	Random Forest: (Best one to use in our opinion)
MSE: 0.32263
RMSE: 0.56801 //
R-squared: 0.44382 //Best 0.45 (Random Forest Method gives random results every time)
(Approximate)

![image](https://github.com/Halime23/MachineLearning/assets/122736002/ca63af95-7dc1-48c0-a5db-a3e57c8ad3f3)

 
h.	Support Vector Machine: 
MSE:  0.51153
R-squared:  0.71522
RMSE:  0.11818

 ![image](https://github.com/Halime23/MachineLearning/assets/122736002/ac08d79a-6423-44bf-9354-0f1d9b02a20b)


We did not do Classify because Regression algorithms are used to predict the continuous values such as price, salary, age, etc. and Classification algorithms are used to predict/Classify the discrete values such as Male or Female, True or False etc.


In conclusion, we think random forest regression would be good to use rather than other regression methods because RMSE and R-squared results are better than other methods and more reliable than Polynomial Regression which has the best results. Using higher Polynomials for calculating is not the best choice for us.


4.	
       a. K-means clustering:
There is a sweet spot where the SSE curve starts to bend known as the elbow point. The x-value of this point is thought to be a reasonable trade-off between error and the number of clusters. In this example, the elbow is located at x=2 and x=3.
We had 11 features, but we needed to reduce them to 2 clusters. That is why we used PCA to reduce the number of features to 2 from 11.
Here we are using the elbow method to see how many clusters would be better to use for our dataset. We only did not include ‘Id.’
 ![image](https://github.com/Halime23/MachineLearning/assets/122736002/3b790793-02c4-4eba-b59a-ea54b8937370)
![image](https://github.com/Halime23/MachineLearning/assets/122736002/375fa125-1845-4a34-a410-6e16fb8ef1c4)


 
Silhouette score: 0.60490

 ![image](https://github.com/Halime23/MachineLearning/assets/122736002/c5345113-f0e5-4f0a-856b-63f45bc437d0)

Silhouette score: 0.53178

As a result, we applied K-means clustering for x=3 and x=2. Looking at the Silhouette Scores, we see that x=2 is the best value.

b. Hierarchical clustering:

 ![image](https://github.com/Halime23/MachineLearning/assets/122736002/13d1462a-bc0f-433c-97fb-2ff2178360ed)

 ![image](https://github.com/Halime23/MachineLearning/assets/122736002/2d0b8da1-4cc0-4167-ae3e-7986bf3ae631)

Silhouette score: 0.61882

Again, we create a model using 2 clusters. From the calculations, we can understand that K-means clustering, and Hierarchical clustering are giving us almost the same results.

Both Clustering models are almost the same, but we chose to use Hierarchical Clustering. Because the Silhouette score is slightly higher.
