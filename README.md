# mongoDB-setup-and-queries
## Web Dev Spring24 Assignment 3

The goal of this project is to set up MongoDB Atlas and run queries on a sample database using the Compass UI.

### Setup
I went through 6 steps to set up MongoDB Atlas using MongoDB official documentation as a guide.
1. Sign up for an account
2. Create a free cluster
3. Add a database user
4. Configure a network connection

   *I did the setup at home and the queries on campus so I had to reconfigure the network connection*
5. Load sample data
6. Get connection string
   
After setting up MongoDB Atlas I installed MongoDB for macOS and the Compass UI using [this link](https://www.mongodb.com/try/download/community). In Compass, I connected to the Atlas cluster I made in step 2 using the connection string from step 6.

### Queries
I ran these queries in the MongoDB Shell on the movies collection in the sample_mflix database.
#### Query 1
###### Prompt
Find all movies with runtime greater than 200 minutes in year 1983. The result should include a list of objects sorted by runtime increasing, and each object only has three fields: runtime, title, year. 
###### Query
db.movies.find({runtime: {$gt: 200}, year: 1983}, {runtime: 1, title: 1, year: 1, _id: 0}).sort({runtime: 1});
###### Result
<img width="895" alt="Screenshot 2024-03-25 at 10 34 05 AM" src="https://github.com/junkshark8/mongoDB-setup-and-queries/assets/152639308/243b5166-f34d-4a2e-8043-a15d319050c7">

#### Query 2
###### Prompt
Find all movies after year 2014 with imdb rating greater than 9. *I specified 3 fields (title, year, imdb.rating) to match the example screenshot from the assignment.*
###### Query
db.movies.find({year: {$gt: 2014}, "imdb.rating": {$gt: 9}}, {title: 1, year: 1, "imdb.rating": 1, _id: 0});
###### Result
<img width="878" alt="Screenshot 2024-03-25 at 10 44 13 AM" src="https://github.com/junkshark8/mongoDB-setup-and-queries/assets/152639308/e099bc23-c294-4389-80c1-6a8d52cc7e1c">

