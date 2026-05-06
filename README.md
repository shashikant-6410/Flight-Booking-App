# ✈️ Flight Booking App – Microservices Backend

## 📌 Overview

Flight Booking App is a scalable **microservices-based backend system** designed to manage flight booking operations using modern backend engineering practices.

The project focuses on building a modular and production-oriented architecture with secure API communication, centralized request handling, asynchronous workflows, and service-level separation of concerns.

### Key Features

- API Gateway Pattern
- JWT-based Authentication & Authorization
- RESTful API Architecture
- Rate Limiting for API Protection
- Centralized Error Handling
- RabbitMQ-based Asynchronous Communication
- Email Notification System
- MVC Architecture within Services
- MySQL + Sequelize ORM Integration

The **API Gateway** acts as the central entry point for all client requests and is responsible for authentication, request validation, route protection, and forwarding requests to internal services.

---

# 🏗 System Architecture

The application follows a **microservices architecture** where services operate independently and communicate through HTTP-based REST APIs.

## 🔹 Services

### 1️⃣ API Gateway
Responsible for centralized request management.

#### Features
- JWT authentication & token validation
- Route-level authorization
- Request forwarding
- Rate limiting
- Centralized error handling
- Service routing

---

### 2️⃣ Flight Service
Handles flight-related operations and data management.

#### Responsibilities
- Flight CRUD operations
- Flight availability management
- Database interaction using Sequelize ORM
- MySQL integration

---

### 3️⃣ Booking Service
Manages booking workflows and business logic.

#### Responsibilities
- Booking creation & management
- Ticket processing
- Flight validation through service communication
- Booking-related business operations

---

### 4️⃣ Notification Service
Handles asynchronous notification workflows.

#### Features
- RabbitMQ-based message queue integration
- Email notification system using Nodemailer
- Booking confirmation notifications
- Decoupled asynchronous communication

---

# 🔄 Request Flow

1. Client sends request to the **API Gateway**
2. Gateway validates JWT token and applies middleware checks
3. Request is forwarded to the appropriate service
4. Service processes the request and performs database operations
5. Notification Service handles asynchronous events when required
6. Final response is returned to the client through the Gateway

---

## Example Routes

```bash
/api/v1/flights/*      → Flight Service
/api/v1/bookings/*    → Booking Service
```

---

# 🛠 Tech Stack

## Backend
- Node.js
- Express.js

## Database
- MySQL

## ORM
- Sequelize ORM

## Authentication & Security
- JWT (JSON Web Token)
- Custom Authentication Middleware
- Rate Limiting
- Centralized Error Handling

## Messaging & Notifications
- RabbitMQ
- Nodemailer

## Architecture & Design
- Microservices Architecture
- API Gateway Pattern
- MVC Pattern
- REST APIs

---

# 📂 Repository Structure

This repository acts as the centralized architecture overview for the complete system.

## 🔗 Service Repositories

| Service | Repository |
|---|---|
| API Gateway | https://github.com/shashikant-6410/API-Gateway |
| Flight Service | https://github.com/shashikant-6410/Flight-service |
| Booking Service | https://github.com/shashikant-6410/Flight-Booking-Service |
| Notification Service | https://github.com/shashikant-6410/Notification-service |

---

## Service Responsibilities

### API Gateway
- Handles authentication and route protection
- Applies rate limiting and middleware validation
- Routes requests to internal services

### Flight Service
- Manages flight-related operations
- Handles flight CRUD functionality
- Maintains flight availability data

### Booking Service
- Processes booking operations
- Handles booking workflows and validations
- Communicates with Flight Service

### Notification Service
- Consumes asynchronous events using RabbitMQ
- Sends booking confirmation emails using Nodemailer
- Handles decoupled notification workflows

---

# 🚀 Running the Project

## 1️⃣ Clone Repositories

Clone all required service repositories locally.

```bash
git clone <repository-url>
```

---

## 2️⃣ Install Dependencies

```bash
npm install
```

---

## ⚙️ RabbitMQ Setup

The Notification Service depends on **RabbitMQ** for asynchronous communication between the Booking Service and Notification Service.

Before starting the services, ensure RabbitMQ is installed and running locally or through Docker.

### RabbitMQ is required for:
- Booking event publishing
- Queue-based communication
- Email notification processing

The Booking Service publishes events to RabbitMQ, and the Notification Service consumes those events to send booking confirmation emails using Nodemailer.

Make sure the RabbitMQ server is active before running the Booking and Notification services.

## 3️⃣ Start Services

Start services individually:

- Flight Service
- Booking Service
- Notification Service
- API Gateway

---

## 4️⃣ Access APIs Through Gateway

All client requests should be routed through the API Gateway endpoints.

---

# 🔮 Future Enhancements

- Nginx Reverse Proxy Integration
- Docker-based Containerization
- Redis Caching Layer
- Swagger API Documentation
- Winston Logging System
- CI/CD Pipeline Integration
- Service Discovery Mechanism

---

# 🎯 Learning Outcomes

This project demonstrates practical understanding of:

- Scalable Backend System Design
- Microservices Architecture
- API Gateway Pattern
- Secure Authentication & Authorization
- Asynchronous Communication
- Modular Backend Development
- Production-Oriented Backend Practices

---

# ⭐ Project Highlights

- Designed modular backend services with clear separation of concerns
- Implemented secure API access using JWT authentication
- Integrated asynchronous notifications using RabbitMQ
- Applied scalable backend architecture principles
- Built production-oriented backend workflows using modern Node.js practices
