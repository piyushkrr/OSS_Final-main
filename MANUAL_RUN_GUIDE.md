# How to Run the Online Shopping System Manually

Follow these steps to start all backend services and the frontend application.

## Prerequisites

- **Java 17** or higher
- **Node.js** and **npm**
- **Maven**
- **MySQL Server**

## 1. Database Configuration

Ensure your MySQL server is running with the following settings:

- **Database**: `Training`
- **User**: `root`
- **Password**: `Root123$`

You can create the database using the following SQL command:

```sql
CREATE DATABASE IF NOT EXISTS Training;
```

## 2. Start Backend Infrastructure

Infrastructure services must be started first for discovery and routing.

### Eureka Server (Service Discovery)

- **Directory**: `oss-backend/eureka-server`
- **Command**: `mvn spring-boot:run`
- **Port**: 8761

### API Gateway (Routing)

- **Directory**: `oss-backend/api-gateway`
- **Command**: `mvn spring-boot:run`
- **Port**: 9090

## 3. Start Microservices

Run each of these in a separate terminal window.

### User Service

- **Directory**: `oss-backend/user-service`
- **Command**: `mvn spring-boot:run`
- **Port**: 8089

### Product Catalog

- **Directory**: `oss-backend/product-catalog`
- **Command**: `mvn spring-boot:run`
- **Port**: 8082

### Cart Service

- **Directory**: `oss-backend/cart-service`
- **Command**: `mvn spring-boot:run`
- **Port**: 8085

### Order Management

- **Directory**: `oss-backend/order-management-master`
- **Command**: `mvn spring-boot:run`
- **Port**: 8084

### Payment Processing

- **Directory**: `oss-backend/payment-processing-service-master`
- **Command**: `mvn spring-boot:run`
- **Port**: 8765

## 4. Start the Frontend

- **Directory**: `oss-frontend`
- **Command**: `npm start`
- **URL**: <http://localhost:4200>

## Verification

1. **Eureka Dashboard**: Access [http://localhost:8761](http://localhost:8761) to see all services registered and "UP".
2. **Frontend**: Access [http://localhost:4200](http://localhost:4200) to start using the application.

## Troubleshooting

If you encounter "Port already in use" errors:

- **Linux**: `fuser -k <PORT>/tcp`
- **Windows**: `taskkill /F /PID $(netstat -ano | findstr :<PORT> | awk '{print $5}')`
