# User Management API

This project is a simple User ABM (Add, Browse, Modify) API built with Node.js and Express.js.

## Prerequisites

- Node.js (which includes npm) installed on your system.

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```
2. Navigate to the project directory:
   ```bash
   cd <project-directory>
   ```
3. Install the dependencies:
   ```bash
   npm install
   ```

## Running the Server

To start the server, run the following command from the project directory:

```bash
npm start
```

The server will start and listen on `http://localhost:3000`.

## API Endpoints

The API provides the following endpoints for managing users:

### Create a new user

- **URL:** `/users`
- **Method:** `POST`
- **Body (JSON):**
  ```json
  {
    "name": "John Doe",
    "email": "john.doe@example.com"
  }
  ```
- **Success Response (201):**
  ```json
  {
    "id": 1,
    "name": "John Doe",
    "email": "john.doe@example.com"
  }
  ```
- **Error Response (400 - Bad Request if name or email is missing):**
  ```json
  {
    "message": "Name and email are required"
  }
  ```

### Read all users

- **URL:** `/users`
- **Method:** `GET`
- **Success Response (200):**
  ```json
  [
    {
      "id": 1,
      "name": "John Doe",
      "email": "john.doe@example.com"
    },
    {
      "id": 2,
      "name": "Jane Smith",
      "email": "jane.smith@example.com"
    }
  ]
  ```

### Read a single user by ID

- **URL:** `/users/:id`
- **Method:** `GET`
- **Success Response (200):**
  ```json
  {
    "id": 1,
    "name": "John Doe",
    "email": "john.doe@example.com"
  }
  ```
- **Error Response (404 - Not Found if user does not exist):**
  ```json
  {
    "message": "User not found"
  }
  ```

### Update a user by ID

- **URL:** `/users/:id`
- **Method:** `PUT`
- **Body (JSON - include only fields to update):**
  ```json
  {
    "name": "Johnathan Doe",
    "email": "john.doe.updated@example.com"
  }
  ```
- **Success Response (200):**
  ```json
  {
    "id": 1,
    "name": "Johnathan Doe",
    "email": "john.doe.updated@example.com"
  }
  ```
- **Error Response (404 - Not Found if user does not exist):**
  ```json
  {
    "message": "User not found"
  }
  ```

### Delete a user by ID

- **URL:** `/users/:id`
- **Method:** `DELETE`
- **Success Response (204 - No Content)**
- **Error Response (404 - Not Found if user does not exist):**
  ```json
  {
    "message": "User not found"
  }
  ```

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.
