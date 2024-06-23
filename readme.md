# Worko Project

Worko backend is a Node.js application that manages user data with endpoints to create, read, update, and delete user information. This project includes authorization.

I made this project for an internship assignment which is to be reviewed by a hiring manager (pls give me the job bro 🙏).

You are free to use this project as a template for your projects or tests.

## Technologies Used

Below are the technologies and tools used in the development of Workotwerko:

- **Node.js** - JavaScript runtime environment
- **Express.js** - Web application framework for Node.js
- **MySQL** - Relational database management system
- **Joi** - Object schema validation library for JavaScript
- **bcryptjs** - Library for hashing passwords
- **dotenv** - Zero-dependency module that loads environment variables
- **Jest** - JavaScript testing framework
- **node-mocks-http** - Mocking library for Node.js HTTP server responses
- **Webpack** - Module bundler for JavaScript applications
- **ESLint** - JavaScript linting utility
- **Babel** - JavaScript compiler
- **Postman** or **curl** - API testing tools
- **VSCode** - IDE

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Building the Project](#building-the-project)
- [Running the Project](#running-the-project)
- [API Endpoints](#api-endpoints)
- [Authorization](#authorization)
- [Sample Requests](#sample-requests)
- [Running Unit Tests](#running-unit-tests)
- [Environment Variables](#environment-variables)
- [Notes](#notes)

## Prerequisites

Before you begin, ensure you have the following installed on your machine:

- Node.js (version 14 or higher)
- npm (version 6 or higher)

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/kvkcodes/worko-backend.git
    cd workotwerko
    ```

2. Install the dependencies:

    ```bash
    npm install
    ```

## Building the Project

To build the project using Webpack, run:

```bash
npm run build
```

This will bundle the application into a single file located in the `dist` directory.

## Running the Project

1. Start the application:

    ```bash
    npm start
    ```

2. The application will be running on `http://localhost:3000`.

## API Endpoints

- **List Users**
  - **GET** `/api/worko/user`
- **Get User by ID**
  - **GET** `/api/worko/user/:userId`
- **Create User**
  - **POST** `/api/worko/user`
- **Update User**
  - **PUT** `/api/worko/user/:userId`
- **Partial Update User**
  - **PATCH** `/api/worko/user/:userId`
- **Delete User**
  - **DELETE** `/api/worko/user/:userId`

## Authorization

All endpoints require Basic Authentication. Use `authuser:authpass` in the request headers.

If you are using Postman, navigate to 'Authorization' section in your request window and select type as 'Basic Auth'.
    * Set Username as 'authuser'
    * Set Password as 'authpass'

## Sample curl requests

### List Users

```bash
curl -u authuser:authpass -X GET http://localhost:3000/api/worko/user
```

### Get User by ID

```bash
curl -u authuser:authpass -X GET http://localhost:3000/api/worko/user/1
```

### Create User

```bash
curl -u authuser:authpass -X POST http://localhost:3000/api/worko/user -H "Content-Type: application/json" -d '{"email": "john@example.com", "name": "John Doe", "age": 30, "city": "NY", "zipCode": "10001"}'
```

### Update User

```bash
curl -u authuser:authpass -X PUT http://localhost:3000/api/worko/user/1 -H "Content-Type: application/json" -d '{"email": "john@example.com", "name": "John Doe", "age": 31, "city": "NY", "zipCode": "10001"}'
```

### Partial Update User

```bash
curl -u authuser:authpass -X PATCH http://localhost:3000/api/worko/user/1 -H "Content-Type: application/json" -d '{"age": 32}'
```

### Delete User

```bash
curl -u authuser:authpass -X DELETE http://localhost:3000/api/worko/user/1
```

## Running Unit Tests

To run the unit tests, use the following command:

```bash
npm test
```

This will execute the tests located in the `tests` folder and provide coverage information.

## Environment Variables

Create a `.env` file in the root directory of the project and add the following environment variables:

```env
DB_HOST=your_db_host
DB_USER=your_db_user
DB_PASSWORD=your_db_password
DB_NAME=your_db_name
AUTH_USER=authuser
AUTH_PASS=authpass
```

Replace the placeholder values with your actual database credentials and desired authentication credentials.

## Notes

- Ensure your MySQL database is running and configured correctly, and that you have set the necessary environment variables in a `.env` file in the root of your project.
- Follow .env.example

---

Thank you for reviewing the worko project. If you have any questions, please feel free to reach out.
