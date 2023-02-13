# Bayesian-Statistics-Project

The idea behind this project was to analyse some rewiews previously classified as positive and negative 
and extract as much information as possible thanks to our bayesian tools, with the aim to construct a model able to classify new reviews. 
As a first approach we focused on dimensionality reduction and building a regression model. 
Then we moved our attention to the implementation of the Latent Dirichlet allocation in different ways 
and finally we made use of these models called 'Gaussian Process Topic Models', 
more specifically with 'Bayesian Gaussian Process Latent Variables Models', and combining our knowledge about GP and LDA.

Folders:

-Dataset: contains all the datasets used in the various files on the project. 

-Dataset Creation: starting from the reviews construct a dataset useful for performs numerical analysis such as regression.

-Fetaure Selection: since our corpus has more than 17000 unique words we tried multiple approach to reduce its dimensionality

-Logistic Regression: with the selected dataset reduction we have performed some bayesian logistic regression model

-LDA: we have performed Latent Dirichlet Allocation on our dataset both using the STAN model and the GENSIM library

-Gaussian Processes: make a reasonable model to classify our reviews as positive or negative using Gaussian Processes, Gaussian Process Topic Models
and Gaussian Process Latent Variable Model

Conclusions:
At the end of our work and attempts, we can say that modelling this kind of data with bayesian methods is quite hard and computationally heavy. 
In particular, we went through several problems and failures when using LDA in STAN, which is often very slow and expensive. 
Therefore, regression models and Gaussian Process Topic Models are maybe the more suitable in the case of our review data. 
More precisely, we had the best prediction results with regression models, and specially with the one with a less informative prior. 
From this we can state that using the bayesian approach does not improve the  of the regression models. 
About dimensionality reduction instead, as expected, we saw that using LDA for this target produces an error accumulation which leads to a bad classification accuracy, 
probably because the topics extracted by the model do not capture the sentiment of the revision; 
more precisely it tends to classify as positive the majority of the reviews. 
On the other hand, using Bayesian Gaussian Process Latent Variable Models, 
we obtained a classificator that can learn much better how to distinguish between positive and negative reviews, although, if used on a test set, 
is still very poor, probably because of overfitting the data.

