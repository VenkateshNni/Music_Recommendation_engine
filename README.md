1. Music Recommendation System
This project demonstrates a Music Recommendation System built using the Million Song Dataset. It uses three primary types of recommender systems:

Popularity-based

Item similarity (Collaborative filtering)

Content-based (word-based similarity)

2. Dataset Information
This system uses two files:

triplets_file.csv: Contains user_id, song_id, and listen count.

song_data.csv: Contains song_id, title, release, artist_name, and year.

3. Objective
To recommend songs to users based on:

4.What is popular overall.

What is similar to songs they’ve listened to.

What has related content based on song titles or artists.

🛠️ Technologies Used
Python (pandas, numpy)

Custom Recommenders module for algorithm implementation

5. Project Structure
Copy
Edit
music-recommendation/
│
├── triplets_file.csv
├── song_data.csv
├── Recommenders.py
├── music_recommender.ipynb / .py
└── README.md
6. How to Run
Clone the repo or download the files.

Make sure you have the following installed:

bash
Copy
Edit
pip install pandas numpy
Ensure Recommenders.py exists in your working directory and contains:

popularity_recommender_py

item_similarity_recommender_py

Run the notebook or script to generate recommendations.

7. Data Preprocessing
Combined both datasets using song_id.

Created a song column as title - artist_name.

Filtered top 900k samples for quick experimentation.

8.Recommendation Systems
1. Popularity-Based Recommender
Recommends songs based on total listen count across all users.

python
Copy
Edit
pr = Recommenders.popularity_recommender_py()
pr.create(song_df, 'user_id', 'song')
pr.recommend(user_id)
2. Item Similarity (Collaborative Filtering)
Recommends songs similar to what the user has previously listened to using co-occurrence matrix.

python
Copy
Edit
ir = Recommenders.item_similarity_recommender_py()
ir.create(song_df, 'user_id', 'song')
ir.recommend(user_id)
Also supports:

python
Copy
Edit
ir.get_similar_items(['Song 1', 'Song 2'])
9. Example Outputs
Popularity-Based
plaintext
Copy
Edit
Sehr kosmisch - Harmonia
Undo - Björk
Dog Days Are Over - Florence + The Machine
Item Similarity
Recommends songs based on 45 songs the user listened to like:

plaintext
Copy
Edit
The Cove - Jack Johnson
Stronger - Kanye West
Learn To Fly - Foo Fighters
10. Next Improvements
Implement content-based filtering using NLP on song titles and metadata.

Add matrix factorization or deep learning models.

Include real-time user feedback to improve recommendations.

11. References
Million Song Dataset

Recommender System Concepts

 Author
Venkatesh Manupati

