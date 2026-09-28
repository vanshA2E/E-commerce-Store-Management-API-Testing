# 🛒 Project #4 – E-commerce Store Management API Testing

This Postman project includes end-to-end testing for two mock API backends representing an e-commerce system:

1. **Fake Store API** (`store_url`) for products, carts, orders, and user management  
2. **JSONPlaceholder** (`base_url`) for posts, comments, and placeholder user data

---

## 📄 Project Overview

The collection is divided into **eight test modules** covering CRUD, validation, performance, error handling, and data-driven scenarios:

1. **User Management** – `/users` CRUD tests  
2. **Product Management** – `/products` with filters and validations  
3. **Cart Management** – Add/view carts  
4. **Orders & Auth** – Auth/login endpoint and token storage  
5. **JSONPlaceholder** – Testing typical blog-like data (`/users`, `/posts`, `/comments`)  
6. **Error & Edge Case Handling** – Invalid payloads, missing fields  
7. **Performance Testing** – Validate response time < 500ms  
8. **Data-Driven Testing** – Driven by CSV-based `userId` lookups

---

## 🧰 Tools & Technologies

- 🧪 Postman (v10+)
- 📜 JavaScript for scripting (`pm` API)
- 🧾 JSON Schema (where applicable)
- 📂 CSV files for data-driven tests
- 🔐 Token-based authentication
- 🌐 RESTful principles

---

## 🌐 Environment Setup

Import the `Development.postman_environment.json` file. It includes:

| Variable       | Example Value                           | Description                                      |
|----------------|------------------------------------------|--------------------------------------------------|
| `store_url`    | `https://fakestoreapi.com`               | Base URL for fake-store endpoints                |
| `base_url`     | `https://jsonplaceholder.typicode.com`   | Base URL for JSONPlaceholder                     |
| `user_id`      | `1`                                      | Used for static user test cases                  |
| `userId`       | `1`                                      | Dynamic lookup for CSV iteration                 |
| `product_id`   | `1`                                      | Sample product ID                                |
| `cart_id`      | `1`                                      | Sample cart ID                                   |
| `post_id`      | `1`                                      | Post-related operations                          |
| `store_id`     | `1`                                      | Optional store identifier                        |
| `auth_token`   | *(set at runtime)*                       | Auth token from login request                    |
| `random_email` | *(auto generated)*                       | Set via pre-request script                       |
| `random_name`  | *(auto generated)*                       | Set via script                                   |
| `timestamp`    | *(auto generated)*                       | Used for uniqueness                             |

> ℹ️ Clear collection variables before running to avoid stale data issues.

---

## 📦 Collection Modules

| Module                     | Endpoint(s)                                      | Key Tests                                           |
|----------------------------|--------------------------------------------------|-----------------------------------------------------|
| **1. User Management**     | `{{store_url}}/users`                            | Status code, body validation, existence checks      |
| **2. Product Management**  | `{{store_url}}/products`                         | CRUD flow, filter validation, JSON checks           |
| **3. Cart Management**     | `{{store_url}}/carts`                            | Add/view carts, extract `cart_id`                   |
| **4. Orders & Auth**       | `{{store_url}}/auth/login`                      | Login flow, save `auth_token` in env                |
| **5. JSONPlaceholder**     | `{{base_url}}/users/posts/comments`             | Verify structure, filter by `userId`, data format   |
| **6. Error Handling**      | Invalid IDs, bad payloads                        | Expect 400/404/422 errors, missing keys             |
| **7. Performance Checks**  | `/users`, `/posts`                               | Ensure `< 500ms` response time                      |
| **8. Data-Driven Testing** | `GET /users/u{{userId}}`                         | Iterates userId from CSV and validates response     |

---

## 🚀 How to Run

1. **Import Files**
   - Collection: `E-commerce Store Management.postman_collection.json`
   - Environment: `Development.postman_environment.json`

2. **Set Up**
   - Select `Development` environment.
   - Set global variables `store_url` and `base_url` if not set.

3. **Execute**
   - Run folders individually or via **Collection Runner**
   - Use CSV (`userId, expectedName, expectedEmail`) for data-driven folder

4. **Review**
   - Test tab for pass/fail
   - Console for dynamic values/logs

---

## 📊 Test Execution Results

This project was executed using **Newman CLI** with HTML Extra Reporter. Here's a snapshot of the latest run:

### 📈 Dashboard Screenshot

![Newman Run Dashboard](Newman/ecommerce-newman-report.png)

---

## 🔧 Running via Newman CLI

You can also run this collection from your terminal:

```bash
  newman run "E-commerce Store Management.postman_collection.json" \
  --environment "Development.postman_environment.json" \
  --reporters cli,htmlextra
```

- Install the Newman Extra Reporter if needed:
```bash
  npm install -g newman-reporter-htmlextra

```

## ✅ Suggestions for Improvement

- 🔍 Add schema validation for `products`, `users`, and `carts`
- 🔁 Add looped tests or iterative runs via Newman
- 🛡️ Implement auth/permissions negative testing
- 🔧 CI/CD integration with Newman + GitHub Actions
- 📊 Export test reports via HTML reporter
- ⚠️ Security checks (XSS, SQL-injection patterns)

---

## 📄 License

MIT License — For educational and personal learning use.

---

## 👨‍💻 Author

**Chirag Rathava**  
Postman Student Expert Candidate  
📧 [rathavachirag921@gmail.com](mailto:rathavachirag921@gmail.com)

---

Happy Testing! 🚀
