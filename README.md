# ✈️ Flight Booking App – Microservices Backend

## 📌 Overview

This project is a **microservices-based backend system** for managing flight booking operations.

It follows industry-standard backend practices including:

- API Gateway Pattern
- JWT-based Authentication
- Rate Limiting
- Centralized Error Handling
- RESTful API Design
- MVC Architecture (within each service)

The **API Gateway acts as the single entry point** for all client requests and is responsible for authentication, authorization, and routing requests to internal services.

The system is designed to be modular, scalable, and production-oriented.

---

## 🏗 Architecture

The application is divided into independent services communicating via HTTP REST APIs.

### 🔹 Services

#### 1️⃣ API Gateway
- Entry point for all client requests
- Handles JWT authentication & token validation
- Implements route-level authorization
- Applies rate limiting
- Performs centralized error handling
- Forwards validated requests to respective services

#### 2️⃣ Flight Service
- Manages flight data and availability
- Handles flight CRUD operations
- Uses Sequelize ORM with MySQL

#### 3️⃣ Booking Service
- Manages booking creation and ticket operations
- Communicates with Flight Service for validation
- Handles booking-related business logic

#### 4️⃣ Notification Service (Planned)
- Will handle booking confirmations and alerts
- Designed as an independent service
- Planned for email/SMS notifications
- Will integrate asynchronously with Booking Service

---

## 🔄 Request Flow

1. Client sends request to **API Gateway**
2. Gateway:
   - Validates JWT token
   - Applies rate limiting
   - Checks route authorization
3. Request is forwarded to the respective microservice
4. Service processes request and returns response
5. Gateway sends final response back to client

### Example Routes
  ```
    /api/v1/flights/ → Flight Service
 ```
 ```
    /api/v1/bookings/ → Booking Service
```


---

## 🛠 Tech Stack

### Backend
- Node.js
- Express.js

### Database
- MySQL

### ORM
- Sequelize

### Authentication & Security
- JWT (JSON Web Token)
- Custom authentication middleware
- Rate Limiting
- Centralized error handling

### Architecture & Design
- Microservices Architecture
- API Gateway Pattern
- MVC Pattern
- REST APIs

---

## 📂 Repository Structure

This repository provides the architecture overview and system coordination.

### 🔗 Individual Service Repositories

- API Gateway → https://github.com/shashikant-6410/API-Gateway 
- Flight Service → https://github.com/shashikant-6410/Flight-service 
- Booking Service → https://github.com/shashikant-6410/Flight-Booking-Service 

Each service:
- Runs independently
- Follows MVC structure
- Exposes RESTful APIs
- Communicates through HTTP-based service calls

---

## 🚀 Running the Project (Development)

1. Clone all service repositories  
2. Install dependencies using:
```
   npm install
```

3. Start Flight and Booking services  
4. Start API Gateway  
5. Send all requests through the Gateway endpoints  

---

## 🔮 Future Enhancements

- Nginx for reverse proxy & load balancing
- Docker containerization
- Notification Service integration
- API documentation using Swagger
- Logging system (Winston)
- Caching layer (Redis)
- CI/CD pipeline integration

---

## 🎯 Learning Focus

This project demonstrates:

- Practical implementation of Microservices Architecture  
- API Gateway-based authentication strategy  
- Backend security best practices  
- Modular and scalable backend design  
- Production-oriented development mindset  

---

⭐ This project reflects hands-on experience in designing secure and scalable backend systems using modern development practices.
