# Microservices Backend System

This project presents a **scalable and event-driven microservices architecture** designed to support the core functionalities of an e-commerce platform. Each service operates independently with its own database and communicates asynchronously through **Apache Kafka**. A **GraphQL API Gateway** provides a unified interface for querying data across the system.  

The architecture is optimized for **high performance, flexibility, and reliability**, with integrated **Redis caching**, **JWT-based security**, **priority-driven notifications**, and comprehensive observability using **Prometheus** and **Grafana**. All services are fully **containerized** to ensure reproducible deployments and simplified management.

***

## Core Components

- **Microservices Architecture**  
  Independent services including User, Product, Order, Notification, and Recommendation, each responsible for a distinct domain and backed by its own MongoDB database.

- **GraphQL API Gateway**  
  A unified endpoint providing efficient and flexible data access across all services with support for aggregation and optimized queries.

- **Event-Driven Messaging**  
  Services communicate asynchronously using Kafka for improved scalability, system decoupling, and real-time data propagation.

- **Caching Layer**  
  Redis is utilized to cache frequently accessed data, reduce query latency, and increase response speed under high traffic.

- **Authentication and Authorization**  
  User authentication is secured using JWT tokens. Role-based access control ensures data protection and controlled access.

- **Monitoring and Observability**  
  Prometheus collects operational metrics, while Grafana offers customizable dashboards for system analytics and performance tracking.

- **Containerized Deployment**  
  All services are encapsulated within Docker containers, orchestrated through Docker Compose, facilitating ease of deployment and environment portability.

***

## Functional Modules

### User Management
Handles user registration, authentication, and profile operations using JWT-secured endpoints and encrypted storage.

### **Product Catalog**
- Endpoints for creating, updating, and managing product details.
- Real-time inventory tracking and updates.

### **Order Processing**
- Real-time order placement.
- Inventory reservation system to prevent overselling and ensure consistency.

### **Event-Driven Architecture**
- Kafka-driven real-time communication between services.
- Dead Letter Queues (DLQs) for error handling and message recovery.
- Enhanced resilience and fault tolerance.

### **GraphQL API**
- Consolidated API for querying data across services with flexibility and efficiency.
- Integrated caching of GraphQL responses in Redis for improved query performance.

### **Response Caching**
- Frequently accessed data (e.g., product listings, recommendations) cached in Redis.
- Intelligent cache invalidation for inventory updates and recommendation updates.
- Optimized caching for high-demand scenarios.

### **Notification System**
- Automated email notifications for **transactional**, **promotional**, and **recommendation-based** messages.
- Priority-based queues:
  - **Critical Queue**: For high-priority notifications like order updates and security alerts.
  - **Standard Queue**: For lower-priority notifications like promotional emails.
- Cron jobs for scheduled or bulk notifications to improve efficiency.
- Event-driven triggers for sending notifications seamlessly.

### Recommendation Engine
Generates tailored product recommendations using historical order data and user activity patterns.  
Implements Redis caching to minimize computation overhead and deliver instant responses.

### **Monitoring & Observability**
- **Prometheus** for real-time metrics collection and monitoring.
- **Grafana** dashboards for visualizing system health, performance, and analytics.
- Centralized logging for improved debugging and auditing.

### **Containerization**
- Fully containerized system using **Docker** for seamless deployment.
- Orchestration with **Docker Compose** to run all services together or individually for debugging.

## Tech Stack

### Backend Services
| Component | Technology |
|------------|-------------|
| Core APIs | Node.js (Express.js) |
| API Gateway | GraphQL |
| Event Stream | Apache Kafka |
| Caching | Redis |
| Database | MongoDB |
| Email Delivery | Nodemailer |

### Infrastructure and DevOps
| Component | Purpose |
|------------|----------|
| Docker & Docker Compose | Containerization and orchestration |
| Prometheus | Metrics collection and system monitoring |
| Grafana | Visualization and performance dashboards |

***

## Local Deployment Instructions

The system is fully containerized and can be deployed locally using Docker Compose.

### Run All Services
Execute the following command from the project root:
```bash
docker-compose up --build
```
- To run a specific service, navigate to its directory and follow the steps to install dependencies and start it individually.
