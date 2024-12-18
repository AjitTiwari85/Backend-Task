# Task API Project

## Description

This project is a RESTful API for managing tasks, built using Node.js, Express, and MongoDB. It includes authentication features with JWT for secure access and CRUD operations for tasks.

---

## Features

- User authentication (register and login) using JWT.
- Secure access to task-related endpoints.
- Create, read, update, and delete (CRUD) tasks.
- MongoDB for database storage.

---

## Prerequisites

Before running the project, ensure you have the following installed:

- [Node.js](https://nodejs.org/) (version 14 or higher)
- [MongoDB](https://www.mongodb.com/)

---

## Project Structure

```
Task
├── task-api
│   ├── config
│   │   └── db.js                # MongoDB connection setup
│   ├── controllers
│   │   ├── authController.js   # User authentication logic
│   │   └── taskController.js   # Task management logic
│   ├── middlewares
│   │   └── authMiddleware.js   # JWT authentication middleware
│   ├── models
│   │   ├── task.js             # Task model
│   │   └── user.js             # User model
│   ├── routes
│   │   ├── authRoutes.js       # Routes for authentication
│   │   └── taskRoutes.js       # Routes for task operations
│   ├── server.js               # Entry point of the application
│   ├── .env                    # Environment variables (excluded from version control)
│   ├── package.json            # Dependencies and scripts
│   └── README.md               # Documentation
```

---

## Setup

### 1. Clone the repository:

```bash
git clone <repository_url>
cd Task/task-api
```

### 2. Install dependencies:

```bash
npm install
```

### 3. Configure environment variables:

Create a `.env` file in the `task-api` directory with the following variables:

```
MONGO_URI=<your_mongo_connection_string>
JWT_SECRET=<your_jwt_secret>
PORT=5000
```

### 4. Start the server:

```bash
node server.js
```

The server will run on the specified port (default: `5000`).

---

## API Endpoints

### Authentication Routes

| Method | Endpoint             | Description               |
| ------ | -------------------- | ------------------------- |
| POST   | `/api/auth/register` | Register a new user       |
| POST   | `/api/auth/login`    | Login and get a JWT token |

### Task Routes

| Method | Endpoint                | Description                     |
| ------ | ----------------------- | ------------------------------- |
| GET    | `/api/tasks`            | Get all tasks (protected)       |
| POST   | `/api/tasks/createTask` | Create a new task (protected)   |
| GET    | `/api/tasks/:id`        | Get a task by ID (protected)    |
| PUT    | `/api/tasks/:id`        | Update a task by ID (protected) |
| DELETE | `/api/tasks/:id`        | Delete a task by ID (protected) |

---

## Usage

### 1. Register a new user

**Endpoint:** `POST /api/auth/register`

```json
{
  "name": "example",
  "email":"ex22@gmail.com"
  "password": "password123"
}
```

### 2. Login and get a token

**Endpoint:** `POST /api/auth/login`

```json
{
  "email": "ex22@gmail.com",
  "password": "password123"
}
```

Response:

```json
{
  "token": "your_jwt_token"
}
```

### 3. Access protected routes

Include the token in the `Authorization` header as:

```
Authorization: Bearer <your_jwt_token>
```

---

## Dependencies

- Express
- Mongoose
- dotenv
- bcryptjs
- jsonwebtoken
- nodemon (for development)

---
