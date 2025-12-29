# API Endpoints Reference

All microservices are accessible via the **API Gateway** on port `9090`.

## 👤 User Service

**Port:** `8089` | **Gateway Base Path:** `/auth`, `/users`

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/auth/register` | Register a new user |
| `POST` | `/auth/login` | User login |
| `POST` | `/auth/mfa/send` | Send MFA OTP |
| `POST` | `/auth/mfa/verify` | Verify MFA OTP |
| `POST` | `/auth/password/reset` | Request password reset |
| `POST` | `/auth/set-password` | Set new password |
| `GET` | `/auth/user/{userId}` | Get user account info |
| `PUT` | `/users/{userId}/profile` | Update profile (Name, Avatar) |
| `GET` | `/users/{userId}/addresses` | List saved addresses |
| `POST` | `/users/{userId}/addresses` | Add new shipping address |
| `DELETE` | `/users/{userId}/addresses/{id}` | Delete shipping address |
| `GET` | `/users/{userId}/payments` | List saved payment methods |
| `POST` | `/users/{userId}/payments` | Save new payment method |
| `DELETE` | `/users/{userId}/payments/{id}` | Delete payment method |
| `GET` | `/users/{userId}/wishlist` | View wishlist items |
| `POST` | `/users/{userId}/wishlist` | Add product to wishlist |
| `DELETE` | `/users/{userId}/wishlist/{productId}`| Remove from wishlist |
| `GET` | `/users/{userId}/orders` | User order history |

---

## 📦 Product Catalog

**Port:** `8082` | **Gateway Base Path:** `/api/products`

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/api/products` | List all products |
| `GET` | `/api/products/{id}` | Get product details |
| `POST` | `/api/products` | Create product (Admin) |
| `POST` | `/api/products/{id}/image` | Upload product image |
| `GET` | `/api/products/image/{imageId}` | Retrieve product image |
| `PUT` | `/api/products/{id}/reduce-stock` | Decrease inventory stock |
| `GET` | `/api/products/{id}/check-stock` | Check stock availability |
| `POST` | `/api/products/{pid}/reviews` | Submit product review |
| `GET` | `/api/products/{pid}/reviews` | List product reviews |
| `GET` | `/api/products/{pid}/reviews/avg` | Average product rating |
| `GET` | `/api/products/{pid}/reviews/count` | Total review count |

---

## 🛒 Cart Service

**Port:** `8085` | **Gateway Base Path:** `/cart`, `/checkout`

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/cart/{userId}` | Get user's cart |
| `POST` | `/cart/{userId}/items` | Add item to cart |
| `PUT` | `/cart/{userId}/items/{itemId}` | Update item quantity |
| `DELETE` | `/cart/{userId}/items/{itemId}` | Remove item from cart |
| `GET` | `/cart/{userId}/price` | Cart pricing breakdown |
| `POST` | `/checkout` | Process checkout workflow |

---

## 📋 Order Management

**Port:** `8084` | **Gateway Base Path:** `/api/orders`

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/api/orders/` | Place a new order |
| `GET` | `/api/orders/{orderId}` | Get order details |
| `GET` | `/api/orders/user/{userId}` | List user's orders |
| `PUT` | `/api/orders/{orderId}` | Update order status |
| `DELETE` | `/api/orders/{orderId}` | Cancel an order |
| `GET` | `/api/orders/{orderId}/track` | Track order delivery status |

---

## 💳 Payment Service

**Port:** `8765` | **Gateway Base Path:** `/api/payments`

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/api/payments` | Process order payment |
