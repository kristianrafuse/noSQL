noSQL and MongoDB
-------
In this example, I use PyMongo and MongoDB to interact with noSQL databases. Here, I'm using food hygiene rating databases from various establishments across the United Kingdom. The goal is to evaluate some of the ratings data in order to help the editors of a food magazine decide where to focus future articles.

Part 1: Database and Jupyter Notebook:
-------
* mongoimport command text correctly drops any existing establishments collection before importing establishments.json into MongoDB
* Correctly imports PyMongo, creates an instance of the Mongo Client
* Lists the databases in Mongo, lists the collection(s), use find_one() and pprint to display documents.

Part 2: Update the Database and noSQL Queries
-------
* A query is performed to find the BusinessTypeID for "Restaurant/Cafe/Canteen" and returns only the BusinessTypeID and BusinessType fields.
* A query is correctly performed to delete all the documents in the collection where "Dover Local Authority" is the value for LocalAuthorityName.
* A count_documents() check is performed before and after the removal of the Dover documents to ensure the documents were removed.
* An update_many() query is performed to convert the latitude and longitude fields from strings to decimal numbers and RatingValue to integers.

Part 3: Exploratory Analysis Queries and Aggregation Pipeline
-------
* A query is correctly performed to find the establishments with a hygiene score of 20.
* count_documents() is used to list the correct number of documents.
* A query is correctly performed to find the establishments in London with a RatingValue greater than or equal to 4.
* The query uses the $regex operator to locate the London establishments.
* A query is correctly performed to find the establishments within 0.01 degree of the "Penang Flavours" restaurant.
* The query also limits the results to establishments with a RatingValue of 5.
* The query uses the sort() method in PyMongo to sort in ascending order on the hygiene score.
* The query uses the limit() method in PyMongo to limit the results to 5.
* An aggregation pipeline is built to include a match query, group, and sort.
* The group step of the pipeline is grouped on LocalAuthorityName and counts the number of documents.
* The sort step of the pipeline sorts the count of the documents in descending order.
