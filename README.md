# Recommendation-System

https://blog.cambridgespark.com/tutorial-practical-introduction-to-recommender-systems-dbe22848392b

1.) We have an n X m matrix consisting of the ratings of n users and m items. Each element of the matrix (i, j) represents how user i rated item j. Since we are working with movie ratings, each rating can be expected to be an integer from 1-5 (reflecting one-star ratings to five-star ratings) if user i has rated movie j, and 0 if the user has not rated that particular movie.

2.) For each user, we want to recommend a set of movies that they have not seen yet (the movie rating is 0). To do this, we will effectively use an approach that is similar to weighted K-Nearest Neighbors.

3.) For each movie j user i has not seen yet, we find the set of users U who are similar to user i and have seen movie j.
For each similar user u, we take u‘s rating of movie j and multiply it by the cosine similarity of user i and user u. Sum up these weighted ratings, divide by the number of users in U, and we get a weighted average rating for the movie j.

4.) Finally, we sort the movies by their weighted average rankings. These average rankings serve as an estimate for what the user will rate each movie. Movies with higher average rankings are more likely to be favored by the user, so we will recommend the movies with the highest average rankings to the user.
