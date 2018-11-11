## Pycon Canada 2018 (Toronto)


### Schedule

- 10:30:
  - St.Patrick (3rd floor) - Lessons learned migrating a large Python application

- 11:10:
  - Terrace (3rd floor) - An intelligent shopping list based on the application of partitioning and machine learning algos

- 11:50:
  - Terrace (3rd floor) -  How Mozilla uses Python to build and ship Firefox
  - St.Patrick (3rd floor) -  Guide to your own artificial intelligence application in 3 easy steps

#### 12:20 LUNCH

- 13:30:
  - St.Davis (3rd floor) - Kubernetes 101
  - St.Patrick (3rd floor) - Data Science from concept to production

- 13:45:
  - St.Davis (3rd floor) - Kubernetes 101
  - St.Patrick (3rd floor) -  Easy as ABC: A Quick Introduction to Bayesian A/B Testing in Python

- 14:00:
  - St.Davis (3rd floor) - Kubernetes 101

- 14:15:
  - Terrace (3rd floor) -  Accessible Algos
  - St.Davis (3rd floor) - DDDDD

- 14:55:
  - Ballroom (2nd Floor) -  WSGI for Web Developers
  - St.Davis (3rd floor) - DDDDD

#### 15:25 BREAK

- 15:45:
  - Ballroom (2nd Floor) -  How to Design and Build a Recommendation System Pipeline in Python
  - St. Patrick (3rd floor) - Software Design Simplified

- 16:25:
  - Terrace (3rd floor) -  API Evolution the Right Way


#### 17:00 KEYNOTE


## Notes
-----------------------------------------------------------------------------------------------------------------
### Keynote #1 - Data Science by Shopify speaker
-----------------------------------------------------------------------------------------------------------------
- data cleaning tools
- pmml
- oozie
- fraud prediction (do we have something like that at all??)

-----------------------------------------------------------------------------------------------------------------
### TALK 1: Lessons learned migrating a large Python application
-----------------------------------------------------------------------------------------------------------------
- suggestion to have 2.5 days per sprint to 1 person which is sort of oncall:
    - will answer all the questions other departments have
    - will NOT do any sprint related work
    - will work:
        - pair programming with team members
        - tech dept work
        - prototyping new things
        - refactoring some recent work
        - adding more testing into app
        - some other work related to the team
-----------------------------------------------------------------------------------------------------------------
### TALK 2: An intelligent shopping list based on the application of partitioning and machine learning algos
-----------------------------------------------------------------------------------------------------------------

An intelligent shopping list based on the application of partitioning and machine learning algos
tensorflow, ML, DS, keras, google

###### objective:
- predict which groceries the consumer will want to buy again or will try to buy the first time
- create a smart shopping list -> offer personalized weekly shopping list
- depending on user and U history (order: t-h:t)


###### data:
- user_id - usernumber
- order_id
- store_id
- distance
- product_id
- category_id (aisle_id)
- reorder: 1 if this product was ordered by this user in the past else 0
- special: discount percentage applied to the product price at the time of the purchase


###### Stores: 
 - add stores as products common between the stores

###### Distance:
 - Rayleigh distribution
 - the closer the shop to the user - the higher the promotion
 - calculate gas price from home to the store


###### Description of the learning model:
- the data divided into 2 groups (training and validation) with 90% and 10% of the data respectively
- the final model has 2 neural networks and a GBT classifier (Gradient Boosted Tree, Friedman)
- once trained it can be used to predict in real time what will be the next consumer basket based n the history of purchases and current promotions in close stores


###### Models (newural networks):
- RNN - recurrent neural networks
- Feedforward neural network


###### Conclusion:
- get all the existing dataset and train with the above network, the F1 would be higher
- divide data by timestamp (historical datasets instead of by users)


-----------------------------------------------------------------------------------------------------------------
### TALK 3: How Mozilla uses Python to build and ship Firefox
-----------------------------------------------------------------------------------------------------------------
- understanding release pipelines
    - circle and jenkins don't scale well with mozilla

-----------------------------------------------------------------------------------------------------------------
### TALK 4: Building Recommender Pipeline
-----------------------------------------------------------------------------------------------------------------
- User Preferences (Data)
    - explicit feedback
    - implicit feedback
- Recommender System

- Recommendations (predictions)


#### Approaches of models:
- Collaborative Filtering
    - Similar users like similar things
- COntent Based Filtering
    - looks at the content of movies and users
        - ages, sex... year produced, genre


#### Recommender Pipeline:
1. Pre-processing
    1. transoform data to dataframe (matrix) -> scipy.sparse.csr_matrix
    2. sparsity = count total number of ratings / total number of cells (#ratings / total # elements)
    3. Normalize data:
        - Optimists -> rate everything 4 or 5
        - Pessimists -> rate 1 or 2
        - Need to normalize ratings by accounting for user and item bias
        - Mean normalization

    4. Matrix Factorization
        - factorize the user-item matrix to get 2 latent factor matrices
            - user-factor matrix
            - item-factor matrix
        - missing ratings are predicted from 
        - algos that perform matrix factorizatoon
            - ALS (pick this)
            - SGD
            - SVD
    5. Pick an Evaluation Metric
        - of the top K (10) recommendations what proportion are relevant to the user ?!

2. Hyperparameter Tuning ()
    - Grid Search - sklearn.model_selection.GridSearchCV
    - Random Search - sklearn.model_selection.RandomizedSearchCV

3. Model Training
    - Sequential Model-Based Optimization
        - scikit-optimized
        - hyper-opt
        - emo-e



4. Post-processing
    - sort predicted ratings and get top N
    - Filter out items that a user has already watched etc
    - Item-item recommendations
        - use a similarity metric (cosine similarity)
        - Because you watched something .. etc

5. Evaluation
    - Traditional ML
        - split dataset in half:
            1. train set
            2. test set
    - Recommandation System
        - pretend that we don't know the rating but we actually do and see if the algo got the correct answer based on previous data

        - Precision@K
            - of the top K recommendations what proportion are actually relevant ?
        - Recall@K
            proportion of items that were found in the top K recommendations.


6. Considerations:
        - Interpretability
        - Efficiency and scalability
        - Diversity
        - Serendipity

