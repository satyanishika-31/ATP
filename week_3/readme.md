

**Project Overview**
- **Description:** Simple Node.js + Express backend providing user and product REST APIs. Two nearly-identical modules live in separate folders (for testing/examples).
- **Port:** 8088
- **Runtime:** Node.js (ES modules; `type: "module"` in package.json)

**Repository Structure**
- **API Module:** server.js, package.json
- **API Sources:** user_API.js, product_API.js
- **Second Module (duplicate/example):** server.js, package.json
- **Second Module Sources:** user_API.js, product_API.js

**How it works**
- The main server registers two router apps:
  - Base path `/user-api` forwards to the user router.
  - Base path `/product-api` forwards to the product router.
- Simple in-memory arrays (`users`, `product`) are used to store data (no DB).

**Endpoints (examples)**
- User APIs (base `/user-api`)
  - GET `/user-api/users` — list all users
  - GET `/user-api/users/:id` — get a user by id
  - POST `/user-api/users` — create a user (JSON body)
  - PUT `/user-api/users/:id` — update a user (JSON body)
  - DELETE `/user-api/users/:id` — delete a user
- Product APIs (base `/product-api`)
  - GET `/product-api/product` — list products
  - POST `/product-api/product` — add product (JSON body)
  - PUT `/product-api/product/:id` — update product
  - DELETE `/product-api/product/:id` — delete product

**Request / Payload examples**
- Create user (POST `/user-api/users`)
  - Body:
    ```
    {
      "id": 1,
      "name": "Alice",
      "email": "alice@example.com"
    }
    ```
- Create product (POST `/product-api/product`)
  - Body:
    ```
    {
      "id": 101,
      "name": "Widget",
      "brand": "Acme",
      "price": 9.99
    }
    ```

**Run locally**
- Install Node.js (supports modern Node with ES modules).
- From the module folder (e.g., `api/`) run:
  ```
  npm install
  node server.js
  ```
- Server starts on port 8088 (access e.g., `http://localhost:8088/user-api/users`).
