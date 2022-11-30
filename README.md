# Project-4---Group 4-

=======
## Treat-Yo-Self (Honeymoon in Mexico Edition)


### Description:
<p>Machine learning was utilized to predict the restaurant ratings an individual wounld give based on the individual's profile data. For instance, some features that were included in the dataset were transport, food_rating, service_rating, and more. </p>

### Our Tableau Presentation
<a href= "https://public.tableau.com/shared/8DDGDS9TD?:display_count=n&:origin=viz_share_link">Click Me To View Our Visuals</a>

### Detailed Slide Presentation
<a href= "https://docs.google.com/presentation/d/1MEKdM_I7KAya3GF9uhGG0RFmMDSZZikAc9Or7CqyWWE/edit?usp=sharing">Click Me To View Our Presentation</a>


### Group Members:

* <a href="https://github.com/elqban753">Michael Damas</a>
* <a href="https://github.com/akpatell">Ami Patel</a>
* <a href="https://github.com/bobpickerel">Bob Pickerel</a>
* <a href="https://github.com/GigiSchulte">Gina Schulte</a>
* <a href="https://github.com/askorb97">Austin Skorb</a>
* <a href="https://github.com/Cett6">Connor Starrett</a>
* <a href="https://github.com/ChloeStitik">Chloe Stitik</a>
* <a href="https://github.com/prv5021">Preethi Vontela</a>


### Datasets Used in Analysis:

* <a href="https://www.kaggle.com/datasets/uciml/restaurant-data-with-consumer-ratings?select=usercuisine.csv">Kaggle Dataset - User Cuisine</a>
* <a href="https://www.kaggle.com/datasets/uciml/restaurant-data-with-consumer-ratings?select=userprofile.csv">Kaggle Dataset - User Profile</a>
* <a href="https://www.kaggle.com/datasets/uciml/restaurant-data-with-consumer-ratings?select=chefmozcuisine.csv">Kaggle Dataset - Chef Moz Cuisine</a>
* <a href="https://www.kaggle.com/datasets/uciml/restaurant-data-with-consumer-ratings?select=rating_final.csv">Kaggle Dataset - Final Ratings</a>
* <a href="https://www.kaggle.com/datasets/uciml/restaurant-data-with-consumer-ratings?select=geoplaces2.csv">Kaggle Datatset - Geoplaces2</a>


### Order of Operations:

* Import and Combine Data Using SQL
* Clean Data Using Pandas
* Machine Learning Using Supervised Learning
* Front End Visuals Using Slides and Tableau


### How to load data into SQL

* Run query to create 5 tables: chefmozcuisine, geoplaces2, rating_final, usercuisine, and userprofile_table
* Import the CSV file pertinent to each of the tables 
* Run second query to combine the tables into finalcombouser and geocuisine, and load the data


### Cleaning Data in Pandas

Steps taken to clean dataset:
* Imported dependencies
* Connected to postgres
* Dropped null values and question marks in original dataset


### Machine Learning

Attempt 1:
* Dropped unused features (color, user_id, latitude, longitude, placeid)
* Determined the number of unique values per feature
* Interrogated the cuisine feature and decided to drop it due to the large number of values
* Ran get_dummies to convert features to numeric values
* Assigned Rating as the target and dropped Rating from the features
* Split Data to Test and Train and ran StandardScaler
* Created RandomForestClassifier and fit it with the data
* Testing Score was 0.93711 and Training Score of 0.86189
* Determined the features that had the most impact on the score

Attempt 2:
* The most impactful features from Attempt 1 were the service_rating and the food_rating.  We figured that was a kind of cheating so we dropped those features. Dropped unused features (food_rating, service_rating)
* We reran the RandomForestClassifier and got passing results again
* Training Score was 0.83682 and the Test Score was 0.78668
* Most impactful features were hijos_kids, hijos_independent,and personality_hunter_ostentatious

Optimization:
* We took the data preparation from Attempt 2 
* Used RandomForestRegressor library to run the Optimization
* Created variables with n_estimators, max_features and random_state
* Fit the data with the Optimizer and waiting 8 minutes for it to run
* The Best Parameters were: 

Random grid:  {'n_estimators': [20, 50, 100, 200, 300, 500, 700, 900, 1000], 'max_features': ['auto', 'sqrt'], 'random_state': [1, 2, 4, 8, 10]} 

Best Parameters:  {'random_state': 1, 'n_estimators': 300, 'max_features': 'sqrt'} 


### Tableau Findings
* The area of Mexico we will be sending Connor and his fiancee to for their honeymoon is central Mexico, where the foodies go. 
* The majority of our reviewers are millennials with the top year of birth being 1991.
* Our reviewers are primarily students who take public transportation to their favorite restaurants.
* These reviewers consider themselves casual drinker or non-drinkers.
* Our reviewers are mostly single, catholics with a medium budget.
* Our reviewers with a high budget seem to be young professionals without kids.