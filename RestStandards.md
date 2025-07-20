## ✅ **REST API Naming Best Practices**

### 1. **Use Nouns for Resources (not Verbs)**

**Correct:**

```
GET /users      → Get list of users  
GET /users/123  → Get user with ID 123  
```

❌ **Incorrect (uses verbs):**

```
GET /getUsers  
GET /fetchUser/123  
```

---

### 2. **Use Plural Nouns**

Consistency helps — always use plurals.

✅ **Examples:**

```
/books  
/authors  
/orders  
```

---

### 3. **Use HTTP Methods for Actions**

| **Method** | **Description**         | **Example**          |
| ---------- | ----------------------- | -------------------- |
| GET        | Read data               | `GET /products`      |
| POST       | Create new resource     | `POST /products`     |
| PUT        | Update entire resource  | `PUT /products/1`    |
| PATCH      | Update part of resource | `PATCH /products/1`  |
| DELETE     | Delete a resource       | `DELETE /products/1` |

---

### 4. **Sub-resources for Hierarchy**

✅ Example:

```
GET /users/123/orders → Get orders of user 123
```

---

### 5. **Use Query Parameters for Filtering, Sorting, Pagination**

✅ Example:

```
GET /products?category=books&sort=price&page=2
```

---

### 6. **Use Hyphens (-) not underscores (\_) in URLs**

✅ `GET /user-profiles`
❌ `GET /user_profiles`

---

### 7. **Versioning in the URL**

✅ `GET /api/v1/users`
→ Helps manage breaking changes in future.

---

## ⚠️ Edge Cases and Tips

### 📌 **1. Actions Not Covered by HTTP Verbs**

Use **action names** as sub-resources if necessary:

✅ Examples:

```
POST /users/123/activate  
POST /accounts/456/transfer
```

*Don't make them verbs like `/activateUser`.*

---

### 📌 **2. Non-ID Identifiers (like usernames, slugs)**

✅ Example:

```
GET /users/by-username/john_doe
GET /articles/by-slug/clean-code-guide
```

*Use clear context (e.g., `by-username`) to avoid confusion with IDs.*

---

### 📌 **3. Bulk Operations**

✅ Example:

```
POST /orders/bulk  
DELETE /products?ids=1,2,3
```

→ Use query params or batch endpoints for multiple resources.

---

### 📌 **4. File Uploads or Downloads**

✅ Example:

```
POST /users/123/profile-picture (upload)
GET  /users/123/profile-picture (download)
```

---

### 📌 **5. Soft Deletes / Archives**

If you're not actually deleting:

✅ Example:

```
POST /users/123/archive  
POST /users/123/restore
```

→ Keep DELETE for hard deletes only.

---

## ✅ Summary Cheat Sheet

| Action         | Endpoint               | Method    |
| -------------- | ---------------------- | --------- |
| Get all users  | `/users`               | GET       |
| Get user by ID | `/users/{id}`          | GET       |
| Create user    | `/users`               | POST      |
| Update user    | `/users/{id}`          | PUT/PATCH |
| Delete user    | `/users/{id}`          | DELETE    |
| Activate user  | `/users/{id}/activate` | POST      |

---
