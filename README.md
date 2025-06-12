Music Recommendation System
This repository contains a music recommendation system built using the Million Song Dataset. The system supports two types of recommendation models:

Popularity-Based Recommendation

Item Similarity-Based Recommendation (Collaborative Filtering)

The project demonstrates how to build recommendation systems from scratch using Python, pandas, and numpy.

Dataset Description
The system uses two CSV files:

triplets_file.csv: Contains the user listening data with columns user_id, song_id, and listen_count.

song_data.csv: Contains song metadata with columns song_id, title, release, artist_name, and year.

Objective
To provide personalized song recommendations for users by leveraging:

Global popularity trends

Collaborative filtering based on user-song interactions

Technologies Used
Python 3.x

pandas

numpy

Project Structure
bash
Copy
Edit
music-recommender/
├── triplets_file.csv         # Listening history
├── song_data.csv             # Metadata of songs
├── recommenders.py           # Custom recommender classes
├── music_recommender.ipynb   # Implementation notebook
└── README.md                 # Project documentation


Data Preprocessing
Load and merge both datasets on song_id.

Create a new column song combining title and artist_name.

Clean and filter data for efficient processing.

Group songs based on listen count to identify popular tracks.

Recommendation Models
1. Popularity-Based Recommendation
Recommends songs that are most popular across all users.

Implementation:

python
Copy
Edit
from recommenders import popularity_recommender_py

pr = popularity_recommender_py()
pr.create(train_data=song_df, user_id='user_id', item_id='song')
recommendations = pr.recommend(user_id='some_user_id')
2. Item Similarity-Based Recommendation
Recommends songs similar to those a user has previously listened to using a co-occurrence matrix and Jaccard similarity.

Implementation:

python
Copy
Edit
from recommenders import item_similarity_recommender_py

ir = item_similarity_recommender_py()
ir.create(train_data=song_df, user_id='user_id', item_id='song')
recommendations = ir.recommend(user='some_user_id')
To find songs similar to specific tracks:

python
Copy
Edit
ir.get_similar_items(['Song Title - Artist Name', 'Another Song - Artist'])
Example Output
Popularity-Based Recommendations:

user_id	song	score	rank
user1	Sehr kosmisch - Harmonia	3762	1
user1	Undo - Björk	3214	2
...	...	...	...

Item Similarity Recommendations:

user_id	song	score	rank
user2	Come Back To Bed - John Mayer	0.73	1
user2	Trani - Kings Of Leon	0.65	2

Future Improvements
Add content-based recommendations using NLP on song titles and metadata.

Implement matrix factorization (e.g., SVD).

Integrate real-time user feedback and session data.

Deploy the model as a web API or interactive dashboard.

License
This project is licensed for educational use. Please ensure you have the right to use the Million Song Dataset under its terms of service.

Author
Venkatesh Manupati
Feel free to connect on GitHub or raise an issue or pull request.



