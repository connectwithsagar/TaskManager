
# Task Manager Application

[![Java](https://img.shields.io/badge/Java-17-blue)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.1.0-green)](https://spring.io/projects/spring-boot)
[![MySQL](https://img.shields.io/badge/MySQL-8.0-orange)](https://www.mysql.com/)
[![License](https://img.shields.io/badge/License-MIT-lightgrey)](LICENSE)

## Overview

Task Manager is a backend application built with **Java** and **Spring Boot** that allows users to manage tasks efficiently through a RESTful API. The application uses **MySQL** for persistence and **JPA/Hibernate** for database interaction, ensuring optimized queries and data integrity. The project follows the **MVC architecture**, providing modularity, scalability, and maintainability.

## Features

- Complete CRUD operations for tasks: Create, Read, Update, Delete
- JWT-based authentication for secure endpoints
- Database integration with MySQL using JPA/Hibernate
- Structured with MVC architecture for clean code and maintainability
- RESTful API design for seamless integration

## Technologies Used

- **Java 17**
- **Spring Boot 3**
- **MySQL 8**
- **JPA/Hibernate**
- **JWT Authentication**
- **Maven** for build and dependency management

## Getting Started

### Prerequisites

- Java JDK 17 or higher
- MySQL database
- Maven installed

### Installation

1. **Clone the repository**

```bash
git clone https://github.com/connectwithsagar/TaskManager.git
cd TaskManager/taskmanager
```

2. **Configure the database**

- Create a new MySQL database.
- Update `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/your_database_name
spring.datasource.username=your_username
spring.datasource.password=your_password
```

3. **Build and run the application**

```bash
mvn clean install
mvn spring-boot:run
```

The application will run at [http://localhost:8080](http://localhost:8080).

## API Endpoints

| Method | Endpoint          | Description            |
|--------|-----------------|-----------------------|
| GET    | /api/tasks       | Get all tasks          |
| POST   | /api/tasks       | Create a new task      |
| GET    | /api/tasks/{id}  | Get task by ID         |
| PUT    | /api/tasks/{id}  | Update task by ID      |
| DELETE | /api/tasks/{id}  | Delete task by ID      |

## Authentication

Endpoints are secured with JWT tokens:

1. **Login**: POST `/api/auth/login` with username and password.
2. **Receive Token**: Get JWT token upon successful authentication.
3. **Access Protected Routes**: Include `Authorization: Bearer <token>` in request headers.

## Testing APIs with Postman

### 1. Get All Tasks

- **Method**: GET
- **URL**: `http://localhost:8080/api/tasks`
- **Headers**: 
  - Authorization: `Bearer <your_token>`

### 2. Create a New Task

- **Method**: POST
- **URL**: `http://localhost:8080/api/tasks`
- **Headers**: 
  - Content-Type: application/json
  - Authorization: `Bearer <your_token>`
- **Body (raw JSON)**:

```json
{
  "title": "Complete README",
  "description": "Write full README.md for GitHub",
  "status": "PENDING"
}
```

### 3. Get Task by ID

- **Method**: GET
- **URL**: `http://localhost:8080/api/tasks/1`
- **Headers**: 
  - Authorization: `Bearer <your_token>`

### 4. Update Task

- **Method**: PUT
- **URL**: `http://localhost:8080/api/tasks/1`
- **Headers**: 
  - Content-Type: application/json
  - Authorization: `Bearer <your_token>`
- **Body (raw JSON)**:

```json
{
  "title": "Complete README",
  "description": "Update README.md content",
  "status": "COMPLETED"
}
```

### 5. Delete Task

- **Method**: DELETE
- **URL**: `http://localhost:8080/api/tasks/1`
- **Headers**: 
  - Authorization: `Bearer <your_token>`

## License

This project is licensed under the **MIT License**.
