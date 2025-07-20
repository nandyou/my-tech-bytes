
📌 1. What is GraphQL?

GraphQL is a query language for APIs and a runtime for executing queries. It lets clients request only the data they need.

⸻

🔑 Core Concepts:

1. Schema

Defines the types and structure of data available in the API.

type Book {
  id: ID
  title: String
  author: Author
}

2. Query

Used to fetch data.

query {
  book(id: "1") {
    title
    author {
      name
    }
  }
}

3. Mutation

Used to modify data (create, update, delete).

mutation {
  addBook(title: "1984", authorId: "5") {
    id
    title
  }
}

4. Subscription

Used for real-time updates via WebSockets.

subscription {
  bookAdded {
    id
    title
  }
}

5. Resolvers

Functions that handle fetching or modifying the actual data behind each field.

6. Types
	•	Scalar: Basic types (String, Int, Boolean, etc.)
	•	Object: Custom data types (e.g., Book, Author)
	•	Enum, Union, Interface, Input: Advanced type helpers.

7. Arguments

Passed to queries/mutations to filter or customize results.

query {
  books(genre: "Sci-Fi") {
    title
  }
}

8. Fragments

Reusable pieces of query logic.

fragment BookDetails on Book {
  title
  author {
    name
  }
}

