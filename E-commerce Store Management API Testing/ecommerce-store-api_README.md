# 🛒 E-commerce Store Management API Testing

A Postman-based API testing project covering user management, products, carts, authentication, error handling, performance testing, and data-driven testing using mock REST APIs.

## 📌 Project Overview

This project contains **8 testing modules** implemented using Postman and JavaScript test scripts.

The project uses two mock APIs:

- **Fake Store API** – users, products, carts, and authentication
- **JSONPlaceholder** – users, posts, and comments

> ⚠️ The Fake Store API was unavailable during the latest execution and returned HTTP `523 Origin Is Unreachable`. Therefore, the Fake Store API-dependent tests could not be fully executed during the final validation.

---

## 🧰 Tools & Technologies

- Postman
- Newman CLI
- JavaScript (`pm` API)
- REST APIs
- JSON
- CSV Data-Driven Testing
- HTML Extra Reporter
- Git & GitHub
- Node.js / npm

---

## 📂 Project Structure

```text
E-commerce Store Management API Testing/
│
├── Development.postman_environment.json
├── E-commerce Store Management.postman_collection.json
├── ecommerce-store-api_README.md
├── user_data.csv
├── package.json
├── package-lock.json
│
└── Newman/
    ├── Collection8-DataDriven-Report.html
    ├── E-commerce Store Management.html
    └── ecommerce-newman-report.png