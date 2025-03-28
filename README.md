# 🔐 Auth Service

# Description
Auth Service is a microservice dedicated exclusively to user authentication and authorization, providing a secure and scalable system based on good authentication and authorization practices.

## Technologies
* **Language:** Java 21+
* **Framework:** Spring Boot 3+
* **Authentication and Authorization:** Spring Security & OAuth2 with JWT
* **Persistence:** JPA/Hibernate with PostgreSQL
* **Caching and Token Handling:** Redis
* **Resilience Patterns:** Resilience4J for Circuit Breaker
* **Architecture:** Hexagonal (Ports & Adapters)
* **Service Exposure:** RESTful APIs and GraphQL

## Project Architecture
The system is designed following the principles of hexagonal architecture to decouple business logic from frameworks and infrastructure.

### Key components
+ **Domain:** Contains pure business logic (domain entities, rules, and services).
+ **Application:** Defines use cases and exposes ports for interacting with the infrastructure layer.
+ **Infrastructure:** Implements adapters for the database, cache, APIs, and other external integrations.

## Endpoints
### Authentication and Authorization
+ `POST /auth/login` - Log in and obtain a JWT token.
+ `POST /auth/logout` - Invalidate the user's session.
+ `POST /auth/refresh` - Refresh an expired JWT token.
+ `POST /auth/register` - Register a new user.

### User and Role Management
+ `GET /users/{id}` - Get user information.
+ `POST /users - Create` a new user.
+ `PUT /users/{id}` - Update a user.
+ `DELETE /users/{id}` - Delete a user.
+ `GET /roles` - List available roles and permissions.

## Installation and Setup
To run the project locally with Docker and set up PostgreSQL and Redis.

### Prerequisites
+ JDK 21+
+ Maven
+ Docker installed on your system (for PostgreSQL and Redis)
+ Docker Compose installed (often included with Docker Desktop)

## Steps
+ ### Clone the Repository
    ```
    https://github.com/john-almaraz/auth-service.git
    ```
+ ### Database Configuration
  To setup PostgreSQL and Redis with Docker services using the provided file: `docker-compose.yml`
    ```
    docker-compose up -d
    ```
+ ### Verify Data Bases is Running
  + Ensure the PostgreSQL and Redis is running by checking the Docker containers:
   ```
    docker ps
   ```
  + You should see containers named PostgreSQL and Redis.

## Security and Resilience
+ **Spring Security:** manages user authentication and authorization.
+ **JWT:** is used to secure API access.
+ **Redis:** stores active sessions and tokens to improve security and performance.
+ **Resilience4J:** implements fault-tolerant patterns such as Circuit Breaker, Retry, and Rate Limiter.