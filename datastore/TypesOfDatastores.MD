# Databases are foundational building blocks of System Design used to store, manage and retrieve data efficiently.


In this article, we'll explore 15 common types of databases and discuss when to use them, along with examples.

## Relational Databases (RDBMS)
Relational databases structure data into one or more tables of rows and columns, with a unique key identifying each row. Rows in a table can be linked to rows in other tables through foreign keys, establishing a relationship between them.
This structure allows relational databases to handle large amounts of structured data, enforce data integrity, and support complex queries and ACID transactions.
They use Structured Query Language (SQL) for defining, manipulating, and querying data, making them highly versatile and widely used in various applications.

#### Use-cases:
 - Enterprise Applications
 - E-commerce Platforms
 - Banking and Financial Services
Examples: MySQL, PostgreSQL, Oracle Database.

## Key-Value Store
Key-value stores are NoSQL databases that store data as key-value pairs providing fast retrieval of values based on unique keys.
They are primarily used when the data model is based on key-value pairs and requires high scalability, availability and throughput.
However, they may not be the best fit for applications that require complex querying, data relationships, or strong consistency guarantees.

#### Use-cases:
 - Session Storage
 - Caching
 - Real-time data processing
Examples: Redis, DynamoDB.

##  Document Databases
Document databases, a subset of the broader NoSQL family, are designed to store, manage, and retrieve document-oriented information.
These databases handle data in a semi-structured format, typically JSON, XML, or BSON, allowing for a more flexible schema than traditional relational databases.
Document databases are particularly useful in scenarios where the data model evolves frequently, and where fast read and write performance is critical.
However, they may not be the best fit for highly structured data or complex transactions spanning multiple documents or collections.

#### Use-cases:
 - E-commerce Platforms: 
 - Content Management Systems (CMS): 
 - Real-Time Analytics and IoT: 
Examples: MongoDB, Couchbase, and Apache CouchDB

##  Graph Databases
Graph databases are a type of NoSQL database that specialize in storing, managing, and querying complex networks of interconnected data.
They represent data as graphs, consisting of nodes (entities), edges (relationships between entities), and properties (information associated with nodes and edges).
By leveraging the graph structure, graph databases enable efficient traversal, querying, and analysis of interconnected data.
They are very useful in applications like social networks and recommendation engines.

#### Use-cases:
 - Social Networks: 
 - Recommendation Systems: 
 - Knowledge Graphs: 
Examples: Neo4j, Amazon Neptune.

##  Wide-Column Stores
Wide-Column Stores represent a type of NoSQL database optimized for storing and querying large amounts of data across many machines.
They organize data into tables with a flexible and dynamic column structure. They are designed to handle large-scale, distributed data storage and provide high scalability and performance.
Their column-oriented architecture, flexible schema, and eventual consistency model make them well-suited for applications that require high write throughput and real-time data processing.
However, they may not be the best fit for use cases that require complex joins, strong consistency, or strict ACID transactions.

#### Use-Cases:
 - Web analytics and user tracking
 - Real-Time Analytics
Examples: Apache Cassandra, Apache HBase, Google Bigtable.

## In-Memory Databases
In-Memory Databases store data directly in the main memory (RAM) of the computer, as opposed to disk-based storage.
They are designed to provide extremely fast data access and low latency by eliminating the need for disk I/O operations.
In-memory databases are particularly well-suited for applications that require real-time processing, high-speed transactions, and low-latency data access such as caching, real-time analytics, high-frequency trading.
However, they are costly and the main memory may lack sufficient capacity to store the entire dataset.

#### Use-Cases:
 - Online Gaming
 - High-Frequency Trading
Examples: Redis, Memcached.

## Time-Series Databases
Time-Series Databases (TSDBs) specialize in storing, retrieving, and managing time-stamped or time-series data.
Time-series data is a sequence of data points collected over time intervals.
TSDBs are commonly used in applications that generate and process time-series data, such as monitoring systems, sensor networks, financial trading platforms, and IoT (Internet of Things) devices.
They provide the necessary performance, scalability, and specialized features to handle the unique characteristics of time-series data.

#### Use-Cases:
 - Financial Trading Platforms
 - IoT and Sensor Data Management
 - Performance Monitoring
Examples: InfluxDB, TimescaleDB, Prometheus.

## Object-Oriented Databases
Object-oriented databases (OODB) are databases that store and manipulate data as objects.
These objects are instances of classes, which can encapsulate both data (attributes) and behaviors (methods), mirroring the structure and concepts of object-oriented programming languages like Java, C++, or Python.
OODBs are particularly well-suited for applications where complex data models are necessary, or the application logic heavily relies on object-oriented principles.
By allowing developers to work directly with objects in the database, OODBs can simplify the development process and provide a more natural and efficient way to manage complex data structures and relationships.

#### Use-Cases:
 - Object-Oriented Applications
 - Multimedia Databases
Examples: ObjectDB, db4o

## Text Search Databases
Text Search Databases are specialized systems designed for efficient storage, indexing, and retrieval of large volumes of unstructured or semi-structured text data.
They provide fast and scalable search capabilities, enabling users to query and find relevant information from vast collections of documents, web pages, or other text-based content.

#### Use-Cases:
 - E-commerce
 - Web search
 - Log analysis
Examples: Elasticsearch, Apache Solr, Sphinx.

## Spatial Databases
Spatial databases are designed to store, manage, and analyze data that represents geographical or spatial information. They extend traditional database capabilities to handle complex spatial data types, such as points, lines, polygons, and other geometric shapes, along with their associated attributes and relationships.
Spatial databases employ efficient indexing techniques, such as R-trees or quadtrees, to optimize spatial queries and improve performance.
They are used heavily in services that are based on the user's location, such as mapping routes, finding nearby restaurants, or tracking vehicle movements in real-time.

#### Use-Cases:
 - Geographic Information Systems (GIS)
 - Location-Based Services (LBS)
 - Logistics and transportation
Examples: PostGIS (extension for PostgreSQL), Oracle Spatial.

## Blob Datastore
Blob (Binary Large Object) datastores are designed for storing, managing, and retrieving large blocks of unstructured data, such as images, audio files, videos, and documents.
Unlike traditional databases that handle structured data with well-defined fields and records, blob datastores are optimized for large, complex blobs of data that do not fit neatly into standard database schemas.
They provide a scalable, highly available, durable and cost-effective solution for managing massive amounts of unstructured data.

#### Use-Cases:
 - Content Delivery Networks (CDNs)
 - Big data storage
 - Backup and archival
Examples: Amazon S3, Azure Blob Storage, HDFS.

## Ledger Databases
Credit: https://aws.amazon.com/qldb/
Ledger databases also known as blockchain databases are designed to provide an immutable, append-only record of transactions.
They are engineered to ensure that once a transaction is recorded, it cannot be altered or deleted, providing a verifiable and tamper-evident history of all changes over time.
Ledger databases are particularly suitable for applications that require a high level of trust, transparency, and immutability.

#### Use-Cases:
- Supply chain management
- Healthcare
- Voting systems
Examples: Amazon Quantum Ledger Database (QLDB), Hyperledger Fabric.

## Hierarchical Databases
Hierarchical databases organize data into a tree-like structure where data is stored in records, and each record has a single parent record but can have a multiple children, establishing a one-to-many relationship between records.
Hierarchical databases were popular in the early days of computing, particularly in mainframe systems. They were commonly used for file systems, where directories and files naturally fit into a hierarchical structure.
However, they have largely been replaced by other database models, such as relational databases and NoSQL databases, which offer more flexibility and better support for complex relationships.

#### Use-Cases:
- Organizational Structures
- File Systems

Examples: IBM IMS, Windows Registry

## Vector Databases
Vector databases are specialized databases designed for storing and searching vectors which are arrays of numbers representing data in high-dimensional spaces.
They are optimized for similarity search and nearest neighbor queries enabling fast retrieval of similar items based on their vector representations.
These databases are particularly relevant in the field of machine learning and artificial intelligence (AI), where vector representations are commonly used to encode the features of various types of data, including text, images, and audio.

#### Use-Cases:
 - Image and Video Search
 - Recommendation Systems
 - Anomaly detection
Examples: Faiss, Milvus, Pinecone.

## Embedded Databases
Embedded databases are specialized databases designed to be tightly integrated into software applications. Unlike traditional client-server databases that run as separate processes, embedded databases are linked and run as part of the application itself.
By being tightly integrated into the application process, they offer fast data access, small footprint, and simplified deployment.
Embedded databases are particularly useful in resource-constrained environments where a full-fledged client-server database is not necessary or practical.

#### Use-Cases:
- Gaming: 
- Desktop Applications: 
Examples: SQLite, RocksDB, Berkeley DB.
