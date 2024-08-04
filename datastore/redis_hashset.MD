The database should make it trivial to store and display the leaderboard data. The relational database or NoSQL data store can meet the requirements. The relational database is an optimal choice when the dataset is small. The relational database can be a suboptimal solution for the real-time leaderboard because of the scalability limitations for a million players due to the following reasons3, 7:

 - computing the rank of a player requires the recomputation of the ranking of every player through a full table scan
 - caching the read queries on the relational database for performance might result in stale leaderboard data
 - query time can be slow when the count of players is in millions
 - different tables should be joined based on the player ID to display the leaderboard on a normalized data schema
 - a relational database that is not in memory will provide suboptimal performance for real-time updates on a large-scale list of records sorted by score due to disk seeks
 - The computation of the rank of a player requires a nested query in the relational database making the time complexity quadratic. The relational database can take on an average of 10 seconds to execute the query to compute the rank of a player on a table with 10 million records even with database indexes. The creation of database indexes on player_id and created_at columns will improve the read operations but slow down the write operations4. Besides, the result cannot be easily cached as the scores are constantly changing.

As long as the number of concurrent players in the game remains low to moderate (below 100 thousand), the relational database can provide sufficient leaderboard functionality. However, as the concurrent game access increases, the relational data schema becomes non-trivial to scale. The batch mode generation and result caching of the leaderboard reduce recurring computation impact at the expense of user experience6.

An in-memory database such as Redis can be used to build a scalable and performant real-time leaderboard. The sorted set data type in Redis offers in-memory and responsive access to the requirements of the leaderboard in logarithmic time complexity, O(log(n)), where n is the number of elements in the sorted set 8. The sorted set data type in Redis contains a set of items (players) with associated scores, which are used to rank the items in ascending order.

The sorted set data type in Redis automatically sorts the item based on the score during the upsert operations. The queries are significantly faster due to the presorting of items. On the contrary, the relational database sorts the items during the query time resulting in latency and adding further computational burden to the database. In summary, the Redis sorted sets can offer significant performance gains and also be a cost-efficient solution. 
The following are the benefits of using Redis for building the leaderboard6:

 - frees up database resources to handle other types of requests
 - supports a data structure optimized to handle leaderboard use cases

The metadata of the player such as the name of the player is required to display the leaderboard. The player ID is available in the sorted sets and the metadata of the player can be fetched from the relational database. The hash data type in Redis can cache the metadata of players for quick access to the metadata. The hash data type can hold multiple name-value pairs that are associated with a key. The drawback of the hash data type is that the hash consumes memory. Alternatively, the read replicas of the relational database can be queried to fetch the metadata.

A relational database such as PostgreSQL can be used for the persistent storage of the leaderboard data to support complex analytical queries. The profile images of the players can be stored in a managed object storage such as AWS S3.


## Here's a summary of the text in pointer format:

- **Database Choices for Leaderboards**:
  - Both relational databases and NoSQL data stores can be used to store and display leaderboard data.
  - Relational databases are optimal for small datasets but struggle with scalability for large player counts (e.g., millions).

- **Limitations of Relational Databases**:
  - Ranking computation requires full table scans, leading to inefficiencies.
  - Caching read queries can produce stale leaderboard data.
  - Query times increase significantly with millions of players.
  - Normalized schemas require multiple table joins.
  - Disk seeks lead to suboptimal performance for real-time updates.
  - Nested queries result in quadratic time complexity for rank computation.
  - Average query time can be around 10 seconds for large datasets.

- **Concurrency Issues**:
  - Relational databases work well with low to moderate concurrent players (below 100,000).
  - Increased concurrent access complicates scaling.

- **Benefits of In-Memory Databases (e.g., Redis)**:
  - Supports scalable and performant real-time leaderboards.
  - Uses sorted sets for logarithmic time complexity (O(log(n))) for rank access.
  - Automatically sorts items during upsert operations, reducing query latency.

- **Redis Advantages**:
  - Frees up resources for other database requests.
  - Optimized data structure for leaderboard use cases.
  - Can cache player metadata using hash data types for quick access.
  - Hash data types hold multiple name-value pairs but consume memory.

- **Persistent Storage Options**:
  - PostgreSQL can be used for persistent leaderboard data to support complex analytical queries.
  - Player profile images can be stored in managed object storage like AWS S3.

This structure summarizes the main points while retaining the critical information from the original text.


![Big O](https://github.com/nandyou/my-tech-bytes/blob/main/datastore/images/Redis_HashSet_TimeComplexity.png?raw=true)
