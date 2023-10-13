# Movie Recommendation System

### Why Recommendation Systems are important?
- Personalization: They provide tailored content or products to users, enhancing their experience and satisfaction.
- Revenue boost: They increase sales and engagement by suggesting relevant items, leading to higher conversion rates.
- User retention: Effective recommendations keep users coming back, improving customer loyalty.
- Data utilization: They help organizations leverage their data to make informed decisions and optimize their offerings.
- Discovery: Recommendation systems aid users in discovering new, relevant items, expanding their interests.

### Applications of Recommendation systems
- Amazon - Utilizes recommendation systems for product suggestions.
- Netflix - Recommends movies and TV shows to users.
- LinkedIn - Suggests connections and job opportunities to its users.
- YouTube - Recommends videos based on user viewing history.
- TripAdvisor - Provides personalized travel and accommodation recommendations.

### Types of Recommendation Systems
- Content-Based Recommendation System: Recommends items based on the similarity between a user's preferences and the attributes of items.
- Collaborative Filtering: Suggests items to users by considering their past behavior and the behavior of similar users.
- Hybrid Content-Based + Collaborative Filtering: Combines both content-based and collaborative filtering approaches to enhance recommendation accuracy and coverage.
Our Recommendation System is build using Content Based Filtering Approach

### The better the recommendation system the probability of customer doing a purchase increases.

### Dataset Used
TMDB 5000 Movie Dataset
- tmdb_5000_credits.csv
- tmdb_5000_movies.csv

### Variables 
- movies_dataset: Budget, Genres, Homepage, Id(Tmdb ID), keywords, Original Language, Original Title, Overview, Popularity, Production Companies,
Release Date, Revenue, Runtime(in minutes), Spoken Languages, Status(Released or Not), Tagline, Title, Vote Average, Vote Count
- credits dataset: Movie Id, Title, Cast(Character: Actor Name), Crew

### Steps
- Merging Dataframes based on Title
- Keeping neccesarry columns : Genres, Movie Id, keywords, Title, Overview, Cast, Crew
- Creating a new dataframe from above with features as Movie Id, Title, Tags(Overview, Genres, keywords,  Cast, Crew)
- Preprocessing
	i. Removing the Null values i.e. 3 null values in Overview
	ii. Checking for Duplicate Values
	iii. Preprocessing Genres, Keywords, Cast(top 3 actor names), Crew(Extracting name of that dictionary where Job -> Director)
	iv. Removing spaces present in values of Genres, keywords,  Cast, Crew to make each value a single entity.
	v. Concating Overview, Genres, keywords,  Cast, Crew into List with variable name Tags.
	vi. Converting the variable Tags into a string from list.
- Lowering the characters, removing stop words and converting each tag into a vector using Bag Of Words Algorithm.
- Applying stemming(PorterStemmer()) from NLTK library and converting each tag into a vector using Bag Of Words Algorithm.
- Calculating Cosine Similarity between vectors. Cosine Distance(Angle between two vectors) is inversely proportional to Cosine similarity.
- Finding 10 similar movies if given a particular movie
- Creating  a pickle file to use it in our app.py
- Creating website page using streamlit and printing top 10 similar movie names and fetching their posters. 
- Final step is creating files named Procfile, setup.sh, .gitignore, requirements.txt to deploy the website on Heroku Platform.

### Conclusion
Movie Recommendation Sytem has been deployed on Heroku Platform which recommends top 10 similar movies based on the input movie name.


