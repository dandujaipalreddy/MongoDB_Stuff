#Connection Pooling
A Connection Pool is a cache of database connections maintained by your driver so that connections can be re-used
when new connections to the database are required. 
When properly used, connection pools allow you to minimize the frequency and number of new connections to your database.

#Connection Churn
Used improperly however, or not at all, your application will likely open and close new database connections too often, resulting in what we call "connection churn". 
In a high-throughput application this can result in a constant flood of new connection requests to your database which will adversely affect the performance of your database and your application.

#MongoDb Connection Pooling
You should use a single Mongo object, so it will do pooling for you
You can create one Mongo Java instance and it will maintain an internal pool of connections (default size of 10 and is dependent on language) - to you it's hidden 
and you don't need to worry about it.
