*******************************************************************
This code was developed for Lab 2: Movie Recommendations coursework
as part of CM50266 Applied Data Science module university of Bath
*******************************************************************

The code is seperated into 2 parts
1. identify highest rated film of each genre
2. top K movie recommendation 

########################################################
1. identify highest rated film of each genre
The code begin to separate each movie into each genre. 
Each rating of each movie in each genre are add up.
Then take the average by number of rating. 
########################################################

########################################################
2. top K movie recommendation 
First, the model consume all the available data and 
consider one movie at a time. The model ask for input of the user ID
that the wish to make recommendation. 
For movie i, the model create a list called “watchedlist” 
(the list of the users who have watched movie i)
Then, the cosine similarity is used to find k users from 
“watchedlist” that is similar to target user.
Again, the weighted average is used to predict the rating of target user.
Therefore, the rating will be predict to all the movie the user have not watch. 
Once all the rating are predicted, the algorithm neglect 
the movie that have rating lower than 4, sort the rating 
from maximum to minimum and select top K movies to recommend to users
where the value of K again will be input by the user. 

Detail of function
1.Matrix function : This function is used to convert user_data.csv 
to suitable format that contain number of row equal to number of user, 
each row (each user ) contain series of number for 1682 columns 
(represent each movie). If the number is 0 that mean the user 
never watch this movie before, otherwise the number represent 
the rating for that movie of that user. Each row is treated as vector. 

2. Similarity function : This function is to find which user 
is similar to the target user by using cosine similarity. 
The higher value of cosine similarity indicate the high similarity between the users. 

Hyper-parameter
21 neighbourhood is used in this model 
with prediction errors of (MAE : 0.8152 and RMSE : 1.021)
########################################################

Acknoledgement 
F. Maxwell Harper and Joseph A. Konstan. 2015. The MovieLens Datasets: 
History and Context. ACM Transactions on Interactive Intelligent 
Systems (TiiS) 5, 4, Article 19 (December 2015), 19 pages. 
DOI=http://dx.doi.org/10.1145/2827872 
 
 
 