# Spring Boot Project
This repository contains the backend project for the CSYE6225 Cloud Computing course.

## Prerequisites for project

Before building and deploying the application locally, ensure you have the following prerequisites:

- Java Development Kit (JDK) 17
- Maven

## Health Check Controller

The `HealthController` It manages health check requests to confirm the database connection status. It offers endpoint for verifying the database connection, handling unsupported HTTP methods, and managing unknown URLs

# Features
### `GET /healthz`

This endpoint checks the application's connectivity to the database and returns an appropriate HTTP status code based on the result.

- **200 OK** – if the database connection is successful.
- **503 Service Unavailable** – if the database connection fails.
- **405 Method Not Allowed** – for unsupported HTTP methods.
- **400 Bad Request** – if any payload is provided in the request.

---

## User Management Endpoints

### `POST /v1/user`
- Creates a new user account.

### `GET /v1/user/self`
- Retrieves authenticated user's information.

---

## Security & Performance Features

### Secure Password Handling
- Passwords are hashed using **bcrypt** before being stored in the database, ensuring secure authentication.

### No Caching
- API responses include the following headers to prevent caching:
  - `Cache-Control: no-cache`
  - `Pragma: no-cache`

## Configuration

The project configuration file (`application.properties`) to manage database connectivity

## Commands to call Health Endpoint
### Success
curl -vvvv http://localhost:8080/healthz

### Failue
curl -vvvv http://localhost:8080/healthz

### 405 Method Not Allowed
curl -vvvv -XPUT http://localhost:8080/healthz


1. Clone the repository.
2. Configure the `application.properties` file with your database settings.
3. Build the project using Maven: mvn clean install.
4. Run the application.


