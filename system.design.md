⸻

🧠 Key Concepts in System Design

⸻

1. ⚙️ Scalability

Definition: The ability of a system to handle increased load (traffic, data, users) without compromising performance.
	•	Horizontal Scaling: Add more machines (e.g., more web servers).
	•	Vertical Scaling: Add more power (CPU/RAM) to existing machines.

Example: Twitter scaling their backend to handle millions of tweets per minute.

⸻

2. 📦 Load Balancing

Definition: Distributes incoming network traffic across multiple servers to prevent overloading a single server.
	•	Ensures high availability and fault tolerance.
	•	Common tools: Nginx, HAProxy, AWS ELB.

Example:

User → Load Balancer → [Server 1, Server 2, Server 3]


⸻

3. 🧰 Caching

Definition: Temporarily storing frequently accessed data to reduce load and latency.
	•	Client-side, Server-side, or CDN-based caching.
	•	Tools: Redis, Memcached, Varnish.

Example: Caching user profile data so you don’t hit the database every time.

⸻

4. 🛢️ Database Design

Definition: Designing a schema and choosing the right type of database for the data.
	•	Relational (SQL): PostgreSQL, MySQL (for structured data).
	•	NoSQL: MongoDB, Cassandra (for unstructured, flexible data).
	•	Concepts: Normalization, Sharding, Replication, Indexes.

Example: Using MongoDB to store chat messages in a messaging app.

⸻

5. 📤 API Design

Definition: Designing interfaces for components to communicate (REST, GraphQL, gRPC).
	•	Concise, versioned, well-documented APIs.
	•	REST uses HTTP verbs (GET, POST, PUT, etc.).

Example: GET /users/123 → fetches user data.

⸻

6. 📊 Data Partitioning (Sharding)

Definition: Splitting a large database into smaller parts to improve performance.
	•	Horizontal Sharding: Divide rows across DBs.
	•	Vertical Sharding: Divide tables across DBs.

Example: Splitting user data across databases based on user region (US, EU, Asia).

⸻

7. 🔄 Replication

Definition: Copying data from one database server to another for redundancy and availability.
	•	Master-slave or multi-master setups.

Example: Reading from replicas to reduce load on the master database.

⸻

8. 🧱 Microservices

Definition: Breaking down a large application into smaller, independent services that communicate over APIs.
	•	Easier to deploy, scale, and develop independently.
	•	Each service has its own database and logic.

Example:
	•	Auth Service
	•	Payment Service
	•	User Profile Service

⸻

9. ⚠️ Rate Limiting

Definition: Restricting the number of requests a user/system can make in a time period.
	•	Prevents abuse and overload.

Example: Only allow 100 API calls per hour per user.

⸻

10. 🔐 Security

Definition: Protecting the system against attacks and data breaches.
	•	Use HTTPS, authentication (OAuth, JWT), encryption, input validation, firewalls.

Example: OAuth 2.0 for Google login.

⸻

11. 📉 Monitoring and Logging

Definition: Tracking the system’s performance, usage, and errors.
	•	Tools: Prometheus, Grafana, ELK Stack, Datadog, Sentry

Example: Alerting when CPU usage exceeds 90%.

⸻

12. ⏱️ Latency and Throughput
	•	Latency: Time taken to respond to a request.
	•	Throughput: Number of requests processed per second.

Goal: Keep latency low, throughput high

⸻

🚀 Real-World Example: URL Shortener (e.g., Bitly)

Key Design Elements:
	•	High write & read throughput
	•	Database with fast lookups (e.g., Redis or NoSQL)
	•	Unique ID generation (e.g., Base62)
	•	Caching popular URLs
	•	Load balancer for traffic
