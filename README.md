# MongoDB-Homework
MongoDB Homework

Introduction
MongoDB is a cross-platform document-oriented database program. Classified as a NoSQL database program, MongoDB uses JSON-like documents with schema. MongoDB is developed by MongoDB Inc. and licensed under the Server Side Public License. MongoDB’s document model is simple for developers to learn and use, while still providing all the capabilities needed to meet the most complex requirements at any scale [Wikipedia]. In this homework, we will implement NoSQL queries over from MongoDB document database in the MongoDB Atlas framework. MongoDB Atlas is a fully-managed cloud database developed by the same people that build MongoDB. Atlas handles all the complexity of deploying, managing, and healing your deployments on the cloud service provider of your choice (AWS, Azure, and GCP) [MongoDB Atlas].
Setup MongoDB Atlas:
You have to create a user account in the MongoDB Atlas for implementing required queries to retrieve relevant results for the following tasks. We are going to use a movie database, called the sample_mflix database. It contains data on movies and movie theaters. The database also contains collections for certain metadata, including users and comments on specific movies. Please access the following link to familiarize yourself with the database:
https://docs.atlas.mongodb.com/sample-data/sample-mflix/

Test Login:
mongo "mongodb+srv://cluster0-wz1ef.gcp.mongodb.net/test"  --username mamin17
Password: Test_999.com
 

MongoDB Queries
Switch to Mflix database. Write relevant queries to perform following tasks

1)	Show dbs 
2)	Use sample_mflix
3)	Show collections
4)	db.movies ().pretty()
 

Movies Collection
General Queries
1.	Write a MongoDB query to display the total number of documents in the collection movies.
Db.movies.count () = 23539

2.	Write a MongoDB query to display any 5 documents using pretty format in the collection movies. 
db.movies.find().pretty().limit(5);

     db.testData.find().limit(3);
     db.collection.find().pretty()

          db.movies.find().sort({title:1}).limit(5);

3.	Write a MongoDB query to display 5 documents sorted by “title” using pretty format in the collection movies. 

4.	Write a MongoDB query to display 5 documents (display only title and awards) sorted by “title” using pretty format in the collection movies. 

5.	Write a MongoDB query to display 5 documents (display only title and awards) sorted by “title” in descending order using pretty format in the collection movies. 


6.	Write a MongoDB query to display movies (display only title and awards) with most awards (number of awards in descending order). 

7.	Write a MongoDB query to display the details of the movie that won most awards 

$AND/$ALL Operation
1.	Write a MongoDB query to display any 5 movies with both the genres: “Adventure” and “Movie” in collection movies (use $all)

2.	Write a MongoDB query to display any 5 movies with both the condition: genres “Adventure” and cast “Tom Hanks”.

Aggregation
1.	Write a MongoDB query to display average number of awards won by a movie (use aggregate function with $avg operator). 
2.	Write a MongoDB query to display most awards won by a movie (use aggregate function with $max operator). 
Comments Collection
General Queries
1.	Write a MongoDB query to display the total number of documents in the collection movies.
2.	Write a MongoDB query to display the total number of users by name (use db.collection.distinct(field, query, options)  and length) in the collection movies.
3.	Write a MongoDB query to display any 5 documents using pretty format in the collection comments.
4.	Write a MongoDB query to display 5 documents sorted by name using pretty format in the collection comments.
5.	Write a MongoDB query to display 5 latest comments (documents sorted by date in descending order) from "Megan Richards" using pretty format in the collection comments.

Aggregation
1.	Write a MongoDB query to display the total number of comments posted by a user (use aggregate function on name) in the collection comments.
2.	Write a MongoDB query to display the maximum number of comments posted by a user (use aggregate function on name with $sum operator and then use $sort) in the collection comments.
Join Movies and Comments
●	Write a MongoDB query to join comments with movies that results in embedding movie information to the comments (using movie_id of comments and _id of movies)

Nested Query
●	Write a MongoDB query to find all movies that won greater than or equal to ($gte) the 3rd most awards winning movie. This query will have two parts. The nested query will first find the number of awards for 3rd most award winning movie. The outer query will find all movies that has more or equal awards than the 3rd most awards count return by the nested query. 
You can also solve in a different way. Use a var to store the 3rd most awards count as returned by a query. Use the var to find all movies that has more or equal awards than var using $gte operator.
 
